## Functional Programming

Functional programming takes the concept of functions a little bit further.



In functional programming, functions are treated as **first-class citizens**, meaning that they can be assigned to variables, passed as arguments, and returned from other functions.



Another key concept is the idea of **pure functions**. A **pure** function is one that relies only on its inputs to generate its result. And given the same input, it will always produce the same result. Besides, it produces no side effects (any change outside the function's environment).



With these concepts in mind, functional programming encourages programs written mostly with functions. It also defends the idea that code modularity and the absence of side effects makes it easier to identify and separate responsibilities within the codebase. This therefore improves the code maintainability.



Going back to the array filtering example, we can see that with the imperative paradigm we might use an external variable to store the function's result, which can be considered a side effect.

```javascript
const nums = [1,4,3,6,7,8,9,2]
const result = [] // External variable

for (let i = 0; i < nums.length; i++) {
    if (nums[i] > 5) result.push(nums[i])
}

console.log(result) // Output: [ 6, 7, 8, 9 ]
```

To transform this into functional programming, we could do it like this:

```javascript
const nums = [1,4,3,6,7,8,9,2]

function filterNums() {
    const result = [] // Internal variable

    for (let i = 0; i < nums.length; i++) {
        if (nums[i] > 5) result.push(nums[i])
    }

    return result
}

console.log(filterNums()) // Output: [ 6, 7, 8, 9 ]
```

It's almost the same code, but we wrap our iteration within a function, in which we also store the result array. In this way, we can assure the function doesn't modify anything outside its scope. It only creates a variable to process its own information, and once the execution is finished, the variable is gone too.