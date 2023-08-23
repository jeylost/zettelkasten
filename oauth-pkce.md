# Proof Key for Code Exchange

#oauth #security 

As we can't trust [[oauth-front-channel-insecure|front channel]] to deliver sensitive data as [[oauth-access-token]]. PKCE was developed to make [[oauth-roles|users]] authorization flow more secure.

PKCE is originally was developed for native apps because they don’t have `client_secret`. But now it’s recommended flow for all apps even though they have `client_secret`

## Implementation sample

1. [[oauth-roles#Application|application]] generates a cryptographically-random `code_verifier` and from this generates a `code_challenge`
2. This `code_challenge` is included in users requests to [[oauth-roles#Authorization Server|oAuth server]]  and instead of asking for `access_token` it asks for an otp code specifying `response_type=code`
3. Using [[oauth-back-channel]] the application exchanges `code` + `code_verifier` for `access_token` or `id_token` or both. Having both `code_challenge` and `code` oAuth server can verify that request from the application, therefore it's secure to respond with tokens