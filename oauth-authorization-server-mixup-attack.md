---
tags:
  - oauth
  - security
---
>[!warning]
>this type of attacks can't happen if application uses only one "hardcoded" Authorization Server

This attack can happen when one of [[oauth-roles#Authorization Server|Authorization Servers(AS)]] is compromised by attacker. 
When [[oauth-roles#User|clients]] use attacker's AS, it starts its own authorization flow by redirecting to a legitimate AS. 
In a [[oauth-pkce|PKCE flow]] client will obtain [[oauth-authorization-code|authorization code]] to exchange for [[oauth-access-token|access_token]]. [[oauth-roles#Application|Client]] redeems this code to attacker's AS. Attacker's AS exchange `code` for `access_token` using the legitimate AS

 [[oauth-authorization-server-issuer-identifier]] solves the issue