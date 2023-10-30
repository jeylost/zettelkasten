---
tags:
  - oauth
  - security
---
Authorization code injection is type of attack where an attacker can steal [[oauth-authorization-code|authorization code]] sent by [[oauth-roles#Authorization Server|OAuth Server]] to the [[oauth-roles#Application|client]] or send attacker's legit authorization code to the user's browser. 

The problem is that client can't identify which [[oauth-roles#User Agent|browser]] session initialised this login request. Therefore redirect URL with authorization code will be valid for any user agent. This resolved by [[oauth-pkce|PKCE]]