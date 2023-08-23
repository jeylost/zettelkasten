#oauth #security 
Mechanism to bind [[oauth-access-token|access_token]] to [[oauth-roles#User Agent|user agent]] from which [[oauth-roles#Application|client]] issued the token.
This mechanism resolves issue of stolen [[oauth-bearer-token|Bearer tokens]]

## [[tls-mutual-tls|Mutual TLS]]
Working on [[tls]] level

Pros:
- doesn't require a lot of development team efforts

Cons:
- hard to deploy
- requires [[oauth-roles#User|users]] to select certificate to use

## [DPoP](https://oauth.net/2/dpop/)
- working on application level

Pros:
- easy to deploy

Cons:
- requires development team efforts to implement