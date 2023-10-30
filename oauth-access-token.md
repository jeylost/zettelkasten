---
tags:
  - oauth
---
From [[oauth-roles#Application|application]] perspective it doesn't matter what exactly the `access_token` is. And rather it's valid or not. It's like a door's key. Applications just use it against [[oauth-roles#API Resource|API]] to get authorized access to users resources

Opposite to [[oauth-id-token|id_token]] `access_token` **can** be any supported format

>[!warning]
>`access_token` **shouldn't** contain any specific data about the [[oauth-roles#User|user]]

[[The Nuts and Bolts of OAuth 2.0]]