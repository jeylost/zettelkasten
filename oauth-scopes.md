#oauth 

just strings that mean nothing to [[oauth-roles#Authorization Server|oAuth server]] itself

It’s up to [[oauth-roles#API Resource|API]]  to validate scopes and grant access granularly

scopes isn't designed to be used for creating roles inside API

scopes can contain description that will be presented to [[oauth-roles#User|users]] on [[oauth-user-consent-screen|user consent screen]]

## Suitable for
	- dividing read and write access
- [[oauth-access-token-lifetime-consideration#Use cases|protecting sensitive operations]]