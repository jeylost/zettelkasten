#oauth #security 

Opposite to [[oauth-access-token]] that [[oauth-roles#Application|applications]] don't utilize for themself and use it only with [[oauth-roles#API Resource|API]] requests to obtain access. [[oauth-id-token]] often is used by applications to present users' avatars, email, names, etc
Therefore applications should guarantee `id_token` validation

If token obtained by [[oauth-back-channel]] then further validation is unnecessary as back channel is secured way to obtain token

Back channel is recommended way to get tokens. But sometimes it's useful to get `id_token` by [[oauth-front-channel]]. 

For instance, [[oauth-show-user-info-asap]]

## validation of `id_token` obtained from front channel
1.  validate the signature of [[jwt]]
2. validate with `c_hash`
3.  check next claims: `iss` , `aud==client_id`, `iat`, `exp`, `nonce==nonce_value_in_the_request` . The reason why is because someone can use a valid `jwt` but intended for another application

## revalidation
If we use `id_token` once and then discard it, we don’t need to revalidate it. But if we store it in untrusted place we need to revalidate it again.

For instance, cookies