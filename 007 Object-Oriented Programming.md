## Object-Oriented Programming

One of the most popular programming paradigms is object-oriented programming (OOP).

The core concept of OOP is to separate concerns into entities which are coded as objects. Each entity will group a given set of information (properties) and actions (methods) that can be performed by the entity.



OOP makes heavy usage of **classes** (which are a way of creating new objects starting out from a blueprint or boilerplate that the programmer sets). Objects that are created from a class are called instances.



Following our pseudo-code cooking example, now let's say in our bakery we have a main cook (called Frank) and an assistant cook (called Anthony) and each of them will have certain responsibilities in the baking process. If we used OOP, our program might look like this.



```
// Create the two classes corresponding to each entity
class Cook {
	constructor constructor (name) {
        this.name = name
    }

    mixAndBake() {
        - Mix the ingredients
    	- Pour the mix in a mold
        - Cook for 35 minutes
    }
}

class AssistantCook {
    constructor (name) {
        this.name = name
    }

    pourIngredients() {
        - Pour flour in a bowl
        - Pour a couple eggs in the same bowl
        - Pour some milk in the same bowl
    }
    
    chillTheCake() {
    	- Let chill
    }
}

// Instantiate an object from each class
const Frank = new Cook('Frank')
const Anthony = new AssistantCook('Anthony')

// Call the corresponding methods from each instance
Anthony.pourIngredients()
Frank.mixAndBake()
Anthony.chillTheCake()
```

What's nice about OOP is that it facilitates the understanding of a program, by the clear separation of concerns and responsibilities.