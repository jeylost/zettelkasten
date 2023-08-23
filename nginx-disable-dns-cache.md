#nginx #issue 
Nginx by default caches all DNS resolved hosts

## Use Cases
- Nginx stands before AWS ALB and uses its private DNS name for upstreams. AWS can change the IP address for ALB at any time, and Nginx will continue to use the old IP address, which causes errors.

## Solution
```nginx
server {
    ...
    resolver 127.0.0.1; 
    set $backend "http://<example.com>:<port>";
    proxy_pass $backend;
    ...
}
```

`resolver 127.0.0.11 ipv6=off;`  - for Docker

`resolver 169.254.169.253;` - for AWS [VPC](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html#vpc-dns-limits)

>[!info]
If config should also resolves public DNS names use seperately resolver for public names. Example:
`resolver 8.8.8.8 8.8.4.4 208.67.222.222 208.67.220.220 valid=300s;`


