#oauth #security

[[oauth-front-channel]] is not secured way to pass sensitive data such as [[oauth-access-token]]

## Reasons
- Browser extensions can intercept requests made in search bar
- Requests will be seen in browser's history
- [[oauth-roles#User|Users]] can modify requests' data on their own

It's recommended to avoid front channel using [[oauth-push-authorization-request]]

Also  [[oauth-roles#Application|application]] **cannot** be sure that data is passed from [[oauth-roles#Authorization Server|oAuth server]] cause its a HTTP request that anyone can send. One of possible attack is [[oauth-authorization-code-injection]]

That's why [[oauth-pkce]] is recommended way to obtain access_token