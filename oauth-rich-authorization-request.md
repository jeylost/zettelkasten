#oauth #security 
Some operations can be sensitive from [[oauth-roles#API Resource|API]] perspective. As sending money from one user to another. To prevent unintentional actions application can require [[oauth-roles#User|users]] to re-login to get scope specific [[oauth-access-token|access_token]]. Such case is described here [[oauth-access-token-lifetime-consideration]]

Rich Authorization Request(RAR) is a parameter that can be added to authorization request. [[oauth-roles#Authorization Server|OAuth Server]] will add this parameters as part of `access_token`. Then API validates this parameters from `access_token` and can be sure that this action is user's intention.

Example:
```js
[  
	{  
		"type": "payment_initiation",  
		"actions": ["initiate", "status", "cancel"],  
		"locations":[  
			"https://example.com/payments"  
		],  
		"instructedAmount":{  
			"currency":"EUR",  
			"amount":"123.50"  
		},  
		"debtorAccount":{  
			"iban":"DE40100100103307118608"  
		},  
		"creditorName":"Merchant123",  
		"creditorAccount":{  
		"iban":"DE02100100109307118603"  
		},  
		"remittanceInformationUnstructured":"Ref Number Merchant"  
	}  
]
```
https://oauth.net/2/rich-authorization-requests/
