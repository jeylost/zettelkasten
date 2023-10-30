---
tags:
  - oauth
---
Authorization code - is a code to exchange for [[oauth-access-token|access_token]]. 
This code is used in order to prevent sending `access_token` directly to [[oauth-roles#Application|client]], because of [[oauth-front-channel-insecure|redirect insecurity]].

It's highly recommended to use the [[oauth-pkce|PKCE extension]]

