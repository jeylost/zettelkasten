#http #security 
HTTP Signature is a way to add integrity and authenticity to [[http-request|http request]]. 
Currently applications rely on [[tls|TLS]]. But TLS doesn't resolve everything. Often APIs don't listen request directly. Some kind of proxy is listening to users requests. This proxies do [[tls-termination|TLS termination]]. And in this case application can never be sure that someone isn't interfering requests.

At the moment(July 2023) it's just a draft for the future

https://oauth.net/http-signatures/