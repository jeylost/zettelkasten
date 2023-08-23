 #oauth

When [[oauth-roles#Application|applications]] need additional information about the [[oauth-roles|user]], they use OpenID

Opposite to [[oauth-access-token|access_token]] `id_token` must be a [[jwt]]. `id_token` contains users' data that's why `jwt` suits the best and it's the only supported format for `id_token`