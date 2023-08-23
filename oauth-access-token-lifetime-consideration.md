#oauth 

considering [[oauth-access-token]] lifetime developers should think in scope of security. What if token will be stolen? How much damage it can inflict to [[oauth-roles#Application|application]] or [[oauth-roles#User|users]]? 

## Use cases
- Basic recommendation <= 24h and refresh token to obtain a new one
- For sensitive operations such a checkout or card charging, developers can consider using a specific [[oauth-scopes|scope]] that permits such operation. Lifetime could be, for instance, 4h and no refresh token available. In this case user should re-login and by providing password confirm his identity and the will to proceed this checkout