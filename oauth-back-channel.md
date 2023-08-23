#oauth 

Back channel is a way to pass data between [[oauth-roles#Authorization Server|oAuth server]] and [[oauth-roles#Application|application]]

Generally speaking back channel is a HTTP request from the application codebase to oAuth server. oAuth server answers with data such as [[oauth-access-token]]

Back channel is a secured way to obtain sensitive data. As opposite to [[oauth-front-channel-insecure|front channel]] nobody will intercept application request from the codebase