---
tags:
  - oauth
---
# Application
Client that [[oauth-roles#User|users]] use to make operations against [[oauth-roles#API Resource|API]]
Example: Web Application, Native application(iOS, Android, WIndows, Linux, MacOS)

#### Client types
- confidential(has both `client_id` and `client_secret`)
- public(has only `client_id`)

# Authorization Server
API that contains data about [[oauth-roles#User|users]](email, phone number, hash_pasword, photo, etc)
Logins [[oauth-roles#User|users]] and pass they [[oauth-access-token]], [[oauth-id-token]], etc. to [[oauth-roles#Application|applications]]
Manages tokens lifetime, invalidation, etc

# User Agent
A device that [[oauth-roles#User|users]] use to access they data. 
Example: Browser, CLI, etc

# User 
User is a resource owner, real people

# API Resource
Backend service that allows [[oauth-roles#User|users]] make operations against it
To make operations [[oauth-roles#User|users]] use [[oauth-roles#Application|applications]] in most cases
Example: Web Server
