---
tags:
  - server_administration
---

# Upload/download files on remote

Prefer the `scp` command if you can establish a direct SSH connection with the remote machine.
However, sometimes—for example, when working under a virtual machine—you don't have your clipboard connected. Adding an SSH public key is a tedious task, and lowering your privacy by allowing password usage is not a trade-off you're willing to make. Still, you need a piece of information to be retrieved or sent. In this case, you can spin up a small web server that will handle transferring data in conjunction with `curl` or `wget`.

Example using [transfer.sh](https://hub.docker.com/r/dutchcoders/transfer.sh/) and Docker:
You need to spin up a web server on a machine with a public IP address and a port that the web server can listen to on the internet-facing interface:

```sh
docker run -p 8080:8080 -v /home/user/tmp:/tmp  dutchcoders/transfer.sh:latest --provider local --basedir /tmp/
```

Upload:

```sh
curl --upload-file ./hello.txt https://<webserver_public_ip>:8080/hello.txt
```

Download:

```sh
curl https://<webserver_public_ip>:8080/1lDau/test.txt > /tmp/hello.txt
```
