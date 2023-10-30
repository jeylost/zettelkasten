---
tags:
  - oauth
---
Non-repudiation, in common sense, refers to the protection against individuals falsely denying their involvement in a particular action.

Example:
John lends money to Jack, and when the deadline approaches, Jack falsely denies borrowing the money, claiming it was a gift. To establish non-repudiation and protect John's interests, a legally binding contract signed by Jack would serve as crucial evidence

In OAuth, non-repudiation is achieved through the use of cryptographic signatures, which provide evidence that a specific request was indeed made by a particular [[oauth-roles#Application|client]] or [[oauth-roles#Authorization Server|OAuth server]]. These signatures serve as proof and prevent the party responsible from denying their involvement in the request