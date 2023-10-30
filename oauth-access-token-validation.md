---
tags:
  - oauth
  - security
---
[[oauth-access-token]] validation is required for [[oauth-roles#API Resource|APIs]] but doesn't make sense for [[oauth-roles#Application|applications]]  

There are several ways to validate `access_token` with their pros and cons

# Remote introspection endpoint
A request from API to [[oauth-roles#Authorization Server|oAuth server's]] token introspection endpoint(RFC7662 OAuth 2.0. Token introspection)

### Pros
- prevent of using token that [[oauth-token-invalidation-before-expiration|invalidated before expiration]]

### Cons
- add additional latency(network request is slower than local validation)
- load network with additional requests

#  Local Token validation
 Local Token validation uses public key exposed by [[oauth-roles#Authorization Server|oAuth Server]] to validate tokens

### Pros
- doesn't add additional latency 
- doesn't add additional network requests

### Cons
- doesn't cover forced token invalidation

# Hybrid
Hybrid is a combination of [[oauth-access-token-validation#Remote introspection endpoint|remote validation]] and [[oauth-access-token-validation#Local Token validation|local validation]]

The idea is to use local validation for all request to roughly drop expired or completely invalid tokens. And use the introspection endpoint for sensitive data for security reason