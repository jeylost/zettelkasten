#ts 
# Use cases

## The validation function should check for an optional value in this case. However, since validation doesn't occur within this function, TypeScript throws an error

```typescript
function createPost(userId: string, title: string) {

}

export class SDK {

	constructor(public loggedInUserId?: string) { }

	createPost(title: string) {

		this.assertUserIsLoggedIn();
		createPost(this.loggedInUserId, title);
	}
	
	assertUserIsLoggedIn(): asserts this is this & { loggedInUserId: string } {
		if (!this.loggedInUserId) {
			throw new Error("User is not logged in");
		}
	}
}
```