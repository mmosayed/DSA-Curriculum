# Big-O Notation
### Efficiency of Code

---

Big-O Notation is a way of measuring the performance of an algorithm relative to how many items you give it as input

---

A simple way of looking at it is how many steps does it take to complete the action

-

### Constant Time O(1)

```javascript
const add = (num1,num2) => { 
	// I have two numbers, takes one step to return the value
	return num1 + num2
}

// Assignment operation only takes constant time
let x = add(2,3);
```

As long as the program doesn't depend on a growing input, it's constant.

-

### Linear Time O(n)

```javascript

const printEach = (arr) => {
	arr.forEach(item => {
		console.log(item);
	});
}

```

This is linear because the steps to complete this function will grow directly with the number of elements in the array.

-

### Quadratic Time O(n^2)

```javascript

const quad = (arr) => {
	for (let i = 0; i < arr.length; i++) {
		for (let j = 0; j < arr.length; j++) {
			console.log(arr[i], arr[j]);
		}
	}
}

```

This grows quadratically because for each element in the array, you iterate through the array once again. This repeats for the length of the array

-

### Logarithmic Time O(log n)

Divide and Conquer recursive algorithms

---

### Most Common Runtimes

![](https://cdn-images-1.medium.com/max/1600/1*_8PfaIyJC7dWJOsKxz47ow.png)

---

### Big-O is an Approximation

```javascript
// O(1)
let num = []; 

// O(n)
for (let i = 0; j < 1000; i++) {
	num.push(i);
}

// O(n)
for (let j = 0; j < num.length; j++) {
	console.log(num[j]);
}

```

O(n) + O(n) + O(1) = O(2n + 1)

But ...

-
### It's actually O(n)

