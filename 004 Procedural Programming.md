## Procedural Programming

Procedural programming is a derivation of imperative programming, adding to it the feature of functions (also known as "procedures" or "subroutines").



In procedural programming, the user is encouraged to subdivide the program execution into functions, as a way of improving modularity and organization.



Following our cake example, procedural programming may look like this:

```
function pourIngredients() {
    - Pour flour in a bowl
    - Pour a couple eggs in the same bowl
    - Pour some milk in the same bowl
}

function mixAndTransferToMold() {
    - Mix the ingredients
    - Pour the mix in a mold
}

function cookAndLetChill() {
    - Cook for 35 minutes
    - Let chill
}

pourIngredients()
mixAndTransferToMold()
cookAndLetChill()
```

You can see that, thanks to the implementation of functions, we could just read the three function calls at the end of the file and get a good idea of what our program does.



That simplification and abstraction is one of the benefits of procedural programming. But within the functions, we still got same old imperative code.