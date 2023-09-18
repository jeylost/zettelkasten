---
tags:
  - architecture
  - grasp
---
A class that has all the required information to perform a task (make a decision) should be assigned to do it. In general, this means that all the internal logic of a functionality should be controlled by the 'nearest' class to which its functionality belongs.
# Example
```js
class Product {
	constructor(name, productPrice) {
		this.name = name;
		this.productPrice = productPrice;
	}
	// this class knows everything about products. Therefore this class is an information expert to calculate its price.
	get price() {
		return this.productPrice;
	}
}

class Purchase {
	constructor(name, ...collection) {
		this.name = name;
		this.collection = collection;
	}
	// this class knows everything about purchases. Therefore this class is an information expert to calculate its price.
	get price() {
		return this.collection.reduce((sum, entity) => {
			// class Purchase doesn't need to know how to calculate price of each individual entity. It's up to these entities. He only knows that price of any entity is available by a public field price. These entities in their turn are information experts to calculate their price
			return sum += entity.price;
		}, 0);
	}
}

const product1 = new Product('Laptop', 2000);
const product2 = new Product('Mouse', 40);
const purchase1 = new Purchase('Work kit', product1, product2);

const product3 = new Product('Book', 100);
const product4 = new Product('iPhone', 1000);

const total = new Purchase('All together', purchase1, product3, product4);

// Now it's easy to calculate total price
console.log(total.price);
```

