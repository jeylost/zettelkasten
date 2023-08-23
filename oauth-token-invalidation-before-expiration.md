#oauth #security 

[[oauth-roles#API Resource|APIs]] should always consider [[oauth-access-token|access-token's]] possibility to be invalid before expiration time

## Use cases
-   [[oauth-roles#User|user]] can deactivated his account
-   user can revoke an [[oauth-roles#Application|application]] access
-   [[oauth-roles#Authorization Server|oAuth server]] can be configured that way that every time user changes password it can revoke all access tokens as well