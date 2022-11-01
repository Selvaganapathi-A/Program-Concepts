## Imperative Programming

Imperative programming consists of sets of detailed instructions that are given to the computer to execute in a given order. It's called "imperative" because as programmers we dictate exactly what the computer has to do, in a very specific way.

Imperative programming focuses on describing ***how* a program operates**, step by step.

Say you want to bake a cake. Your imperative program to do this might look like this (I'm not a great cook, so don't judge me 😒):

```
1- Pour flour in a bowl
2- Pour a couple eggs in the same bowl
3- Pour some milk in the same bowl
4- Mix the ingredients
5- Pour the mix in a mold
6- Cook for 35 minutes
7- Let chill
```

Using an actual code example, let's say we want to filter an array of numbers to only keep the elements bigger than 5. Our imperative code might look like this:

```javascript
const nums = [1,4,3,6,7,8,9,2]
const result = []

for (let i = 0; i < nums.length; i++) {
    if (nums[i] > 5) result.push(nums[i])
}

console.log(result) // Output: [ 6, 7, 8, 9 ]
```

See that we're telling the program to iterate through each element in the array, compare the item value with 5, and if the item is bigger than 5, push it into an array.

We're being detailed and specific in our instructions, and that's what imperative programming stands for.