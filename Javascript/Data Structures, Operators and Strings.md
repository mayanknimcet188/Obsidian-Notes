We will be seeing all the concepts from this example:
```js
const restaurant = {
 name: 'Classico Italiano',
 location: 'Via Angelo Tavanti 23, Firenze, Italy',
 categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
 starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
 mainMenu: ['Pizza', 'Pasta', 'Risotto'],
 order: function (starteerIndex, mainIndex) {
 return [this.starterMenu[starteerIndex], this.mainMenu[mainIndex]];
 },
 orderDelivery: function ({ open, close }) {
 console.log(open, close);
 },
 openingHours: {
 thu: {
 open: 12,
 close: 22,
 },
 fri: {
 open: 11,
 close: 23,
 },
 sat: {
 open: 0, // Open 24 hours
 close: 24,
 },
 },
};
```
### Destructuring Arrays
```js
// basic example
const arr = [1,2,3];
const [a,b,c] = arr;

// For skipping values in between while destructuring
const [first, ,second] = restaurant.categories;

// Swapping values using destructuring
let [main, ,secondary] = restaurant.categories;
// first we create an array with the above values reversed and then descture it
[main, secondary] = [secondary, main];

// Destructuring return values from a function
const [starter,main_course] = restaurannt.order(2, 0);

//Nested destructuring
const nested = [2,3,[5,6]];
const [i, ,j] = nested;
const [i, ,[j,k]] = nested;

//default values
const [p = 1, q = 1, r = 1] = [8,9];
```
### Destructuring Objects
```js
const {name, openingHours, catgories} = restaurant;

// if we dont want to keep default object names
const {
	name: restaurantName,
	openingHours: timings,
	categories: cat,
} = restaurant;

// setting default values in object destructuring
const {menu = [],name: res_name} = restaurant;

// combining the above two things
const {
	name: resName,
	openingHours: hours,
	categories: tags,
	starterMenu: resMenu = [],
} = restaurant;

// Mutating values
let a = 12, b= 23;
cosnt obj = {a: 23, b: 34, c: 56};
// to destructure into existing values we have to 
// enclose the whole statement in parenthesis
({a, b} = obj);

// nested object destructuring
const {fri} = openingHours;
// to destructure the inner objects
const {fri: {open, close}} = openingHours;

// Destructuring objects in a function
const orderDelivery = function ({ open, close }) {
console.log(open, close);
}

orderDelivery(fri);
```
### Spread Operator 
```js

```


