# Object Property Descriptors

- Javascript objects have 3 meta data properties: 
1. `Writable` - make a property read only
2. `Configurable` - if false, you can't redefine the property, cannot change any descriptor except for the `writable`, which can be changed only ONCE
3. `Enumerable` - ignore a property


```javascript
var Product = {
    Title: "Pen",
    Price: 100,
    inStock: true
}

    console.log(Object.getOwnPropertyDescriptor(Product,"Price"));
// outputs {value: 100, wriable: true , enumerable: true, configurable: true}

Object.defineProperty(Product, "Price", {writable: false}); //make it read only
Object.defineProperty(Product, "inStock", {enumerable: false}); //disable it basically, if we were to log this object out now, it inStock wouldn't appear in the log

```

Links: https://www.youtube.com/watch?v=17JGj1CW3no&ab_channel=Geek97
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor

# Getters and Setters

- Getters -> access property
- Setters -> change (mutate) them

```javascript
const person ={
    firstName: 'Leo',
    lastName: 'Posa',
    fullName() {
        return `${person.firstName} ${person.lastName}`
    },
}

console.log(person.fullName());

//this has couple of issues, first of all its read only second of all we have to call it as person.fullName(), it would be nicer if we can treat it as a property person.fullName
// this is where getters and setter come in handy

const person ={
    firstName: 'Leo',
    lastName: 'Posa',
    get fullName() {
        return `${person.firstName} ${person.lastName}`
    },
    set fullName(value) {
       const parts = value.split(' ');
       this.firstName = parts[0];
       this.lastName = parts[1];
    }
}
```

# Static object methods

- Static methods are those methods which are associated with class and not with instances.

```javascript
class Person{
    constructor(name, birthYear, gender){
        this.name = name;
        this.birthYear = birthYear;
        this.gender = gender;
    }
    
    calcAge(){
        console.log('age')
    }
    
    static greet(){
        console.log("Hello")
    }
}

let john = new Person('John', 1990, 'Male');
console.log(john)

//output will be wihtout the greet method, since that is related to the class and not instance, so it's STATIC

Person.greet(); // this is how we call it!
```

Link: https://www.youtube.com/watch?v=3037A244awI&ab_channel=procademy