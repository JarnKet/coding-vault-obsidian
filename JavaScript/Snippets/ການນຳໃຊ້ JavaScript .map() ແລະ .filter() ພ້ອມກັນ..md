---
tag: JavaScript
---
Source: https://masteringjs.io/tutorials/fundamentals/map-filter

## 1. filter()

> ເປັນ Array Method ທີ່ໃຊ້ກັດກອງຂໍ້ມູນຕາມເງື່ອນໄຂທີ່ກຳນົດຂຶ້ນມາ.

```js
const nums = [25, 125, 75, 200];

function atLeast100(num) {
  return num >= 100;
}

nums.filter(atLeast100); // [125, 200]
```

## 2. map()

> ເປັນ Array Method ທີ່ນຳເອົາຂໍ້ມູນຕ່າງໆ ໄປແປຮູບເປັນຂໍ້ມູນອີກຊຸດໃໝ່.

```js
const products = [
  { name: 'T-Shirt', price: 25 },
  { name: 'Headphones', price: 125 },
  { name: 'Keyboard', price: 75 },
  { name: 'Monitor', price: 200 }
];


console.log(products.map(product => product.price));
// [25, 125, 75, 200]
```

## 3. ການນຳໃຊ້ຮ່ວມກັນ

### 3.1 map() ກ່ອນ filter()


```js
const products = [
  { name: 'T-Shirt', price: 25 },
  { name: 'Headphones', price: 125 },
  { name: 'Keyboard', price: 75 },
  { name: 'Monitor', price: 200 }
];


function atLeast100(num) {
  return num >= 100;
}

nums.filter(atLeast100);

// Gets the number of products whose price is at least 100.
products.map(product => product.price).filter(atLeast100).length;

```

### 3.2 filter() ກ່ອນ map()

```js
const orders = [
  { quantity: 2, item: { name: 'T-Shirt', price: 25 } },
  { quantity: 1, item: { name: 'Keyboard', price: 75 } },
  // Maybe there was a bug and a order with a null `item` ended up in the database!
  { quantity: 2, item: null }
];

const orderedItemNames = orders.
  filter(order => order.item != null).
  map(order => order.item.name);

/*
	const orderedItemNames = [
		{ quantity: 2, item: { name: 'T-Shirt', price: 25 } },
		{ quantity: 1, item: { name: 'Keyboard', price: 75 } },
	]
*/
```