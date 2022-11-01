## Declarative Programming

Declarative programming is all about hiding away complexity and bringing programming languages closer to human language and thinking. It's the direct opposite of imperative programming in the sense that the programmer doesn't give instructions about *how* the computer should execute the task, but rather on *what* result is needed.

This will be much clearer with an example. Following the same array filtering story, a declarative approach might be:

```javascript
const nums = [1,4,3,6,7,8,9,2]

console.log(nums.filter(num => num > 5)) // Output: [ 6, 7, 8, 9 ]
```

See that with the filter function, we're not explicitly telling the computer to iterate over the array or store the values in a separate array. We just say what we want ("filter") and the condition to be met ("num > 5").

What's nice about this is that it's easier to read and comprehend, and often shorter to write.

JavaScript's `filter`, `map`, `reduce` and `sort` functions are good examples of declarative code.



An important thing to notice about declarative programming is that under the hood, the computer processes this information as imperative code anyway.



Following the array example, the computer still iterates over the array like in a for loop, but as programmers we don't need to code that directly.

What declarative programming does is to **hide away** that complexity from the direct view of the programmer.