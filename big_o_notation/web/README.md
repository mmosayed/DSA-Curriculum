# Big-O Notation

## Goals
* Understand what an algorithm is
* Understand how to identify the run time of algorithms
* Understand how Big-O makes it easy to label efficiency
* Understand what the most common run times are

## Lesson 

### Algorithm

An algorithm is a set of instructions for accomplishing a task. Every piece of code could be called an algorithm, but we tend to talk about algorithms that solve very common problems. 

Imagine you're given a random list of names and you would like to find "John Smith" in the fastest amount of steps. Or what if you wanted to order those names alphabetically?

Many times we come across problems which have been solved efficiently already!

### Run Time

Generally when we talk about algorithms we talk about runtime. Runtime is specifically talking about the Time Complexity of algorithms. But be aware that you can also talk about Space Complexity of an algorithm which focuses on how much memory a program takes up. Since our computers are increasing memory significantly with gigabytes of RAM; we tend to focus more on Time Complexity.

**Time Complexity**: How long does it take an algorithm to run when given *n* elements as input?

A simple way of looking at it is how many steps does it take to complete the action given the input. If you increase the input how drastically does it affect the run time?

### Big-O

So what is Big-O and why does it matter? 

Imagine you had a list of names with a 10 names. Your simple search algorithm starts at the beginning of the list and works its way down the list one name at a time. You want to find "Bob" which ends up being the last name on the list. You would end up with 10 steps to find "Bob".

Not bad right? 

Now what if that list was 1,000,000 names long and "Bob" was the last name on that list. You'd have to search through 1,000,000 names to find "Bob". 

This "linear" search algorithm depends directly on the number of inputs, n. So the number of steps increase directly with n. 

This is would be a Linear or O(n) algorithm. 

### Where is the Time in Time Complexity?

Time is relative. It's much easier to label algorithms with Big-O than say "This algorithm takes 1 second to complete". Why? Because depending on the computer you run your algorithm the exact time will change. 

What doesn't change is the number of steps! Using the number of steps you can calculate the time. 

### Common Big-Os 
![](https://cdn-images-1.medium.com/max/1600/1*_8PfaIyJC7dWJOsKxz47ow.png)
|Big O Runtime|Name|Example|
|---|---|---|
|O(1) | Constant | Print the first string in an array of count *n* |
|O(n) | Linear | Print every string in an array of count *n* |
|O(n<sup>2</sup>) | Quadratic | Print every character of every string in an array of count *n* (Assume that every string is also of length n) |
|O(log n)|Logarithmic|Divide data set in half every step|


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

### Linear Time O(n)

```javascript
// Pass in an array with size n
const printEach = (arr) => {
  // Iterate through the entire array
  arr.forEach(item => {
    console.log(item);
  });
}
```

This is linear because the steps to complete this function will grow directly with the number of elements in the array.

### Quadratic Time O(n<sup>2</sup>)

```javascript
const quad = (arr) => {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      console.log(arr[i], arr[j]);
    }
  }
}
```

This grows quadratically because for each element in the array, you iterate through the array once again. This repeats for the length of the array.

## Worst Case, Average Case and Best Case
Usually when we talk about runtime, we talk about the *Average Case* runtime.  This is what we would expect the algorithm to do with a typical data set.  Sometimes is also makes sense to talk about the *Best Case* or *Worst Case* situation.  In these cases, we can make special assumptions about the input and see what the minimum possible or maximum possible runtimes are.

Example:

```javascript
const bestAverageAndWorstFunc = (arr) => {
    // O(1)
    if (arr.count < 3) {
      return;
    }
    // O(1)
    if (arr[0] === 8675309) {
      return;
    }
    // O(n^2)
    if (arr[0] + arr[1] === 24601) {
      arr.forEach(item => {
        arr.forEach(item => {
          console.log(item);
        });
      });
      return;
    }
    // O(n)
    arr.forEach(item => {
      console.log(item);
    });
}
```

|Case|Big O|
|---|---|
|Best Case|O(1)|
|Average Case|O(n)|
|Worst Case|O(n^2)|

### Big-O is an Approximation

Now take a look at this following algorithm. Let's derive the Big-O of each step:

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
If we follow algebraic rules and add the Big-O functions together we get:
```
O(n) + O(n) + O(1) = O(2n + 1)
```
This is known as a compound runtime. When we have a compound runtime, we only keep the ***most significent*** term.  In fact, the O in *Big O Notation* stands for "Order" because we care most about the "Biggest Order" that appears.  Order in this case is talking about the [order of the algebraic function](https://en.wikipedia.org/wiki/Order_of_a_polynomial) also called the [degree](https://en.wikipedia.org/wiki/Degree_of_a_polynomial).

So ultimately the Big-O ends up being:
```
O(n)
```

## Resources

* [Cheat Sheet](http://bigocheatsheet.com/)












