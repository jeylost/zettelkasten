---
tags:
  - crypto
---
`jwt` is a token that contains header, body and signature divided by dot.

# Header
`json` encoded with `base64`.
contains `metadata` about the token. For example, alghorithm that used for [[jwt#Signature|signature]], etc,.

# Body
`json` encoded with `base64`
contains any data. For example, [[oauth-id-token|id_token]] contains [[oauth-roles#User|user]] data such email, name, etc,.

# Signature
crypto signature that signs [[jwt#Header|header]] and [[jwt#Body|body]] of the `jwt`  by a private key.
As base64 doesn't make any encryption and all the data inside token is open and can be changed by anyone. Signature guaranties that data isn't changed. As combination of `data(body, header) + private key`  gives a unique signature. 