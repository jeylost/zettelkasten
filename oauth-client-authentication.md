[[oauth-roles#Application|Clients]] use `client_secret`(just a string) to authenticate against [[oauth-roles#Authorization Server|Authorization Server]] 
It's fine as far as connection is protected by [[tls|TLS]]. 

But in order to enhance security next option can be used as well:
- [[tls-mutual-tls|mutual TLS]]
-  [[oauth-client-authentification-with-jwt-profile|Private Key JWT]]