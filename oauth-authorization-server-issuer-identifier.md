# Authorization Server Issuer Identifier

Issuer identifier is URL of [[oauth-roles#Authorization Server|Authorization Server]]. 

It's responsibility of [[oauth-roles#Authorization Server|Authorization Server]] to include `iss` query parameter inside [[oauth-authorization-code|authorization code's]] redirect to [[oauth-roles#Application|client]]
Client in his turn is responsible to validate this parameter. 

Redirect example:
```
Location: https://example-app.com/redirect?code=AUTHORIZATION_CODE&state=XYXYXYXY&iss=https://authorization-server.com/
```

It solves [[oauth-authorization-server-mixup-attack]]

[RFC 9207](https://www.rfc-editor.org/rfc/rfc9207)