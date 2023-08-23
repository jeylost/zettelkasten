#oauth #security 
In the default OAuth flow, sensitive data is passed through the [[oauth-front-channel|front channel]], which may present [[oauth-front-channel-insecure|security concerns]]. To address this issue, the push authorization request (PAR) was introduced as an alternative method. PAR eliminates the need to transmit sensitive data through the front channel, thereby mitigating the associated security risks.

PAR involves sending an HTTP POST request to the [[oauth-roles#Authorization Server|OAuth server]], including all the necessary parameters that are typically sent via redirect. Instead of directly transmitting these parameters through the front channel, the OAuth server responds with a unique URL. This URL serves as a secure mechanism to redirect the user while preserving the integrity of the sensitive data.

[RFC 9126](https://www.rfc-editor.org/rfc/rfc9126.html)