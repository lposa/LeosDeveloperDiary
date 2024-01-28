## What are Higher Order Functions and give an example?

https://www.youtube.com/watch?v=ucn4jAPWBdQ&ab_channel=CatherineLi

- A function that takes another functions as a parameters or returns another function. Functions are also objects in JS. `.map()` and `.filter()` are great examples of HOF. The map function takes a callback function that does something to each element of an array.

## What are arrow functions and name a key difference between arrow functions and regular JS functions?

https://www.youtube.com/watch?v=ucn4jAPWBdQ&ab_channel=CatherineLi

- Arrow functions introduced in ES6. Much shorter way of writing functions. We can remove the curly braces and return keyword, because it implicitly returns something. If the function takes in only 1 parameter, we can even remove the surrounding braces. **WE CANT USE ARROW FUNCTIONS AS OBJECT CONSTRUCTORS**

## What will this code output?

```javascript
function run() {
    console.log(1);
    setTimeout(function(){console.log(2)},1000);
    setTimeout(function(){console.log(3)},0);
    console.log(4);
}

// answer 1 4 3 2 
```

## Are these two function the same? 

```javascript
function foo1()
{
    return {
        bar: 'hello'
    }
}

function foo2()
{
    return // you don't see this, but this will actually be return;
    {
        bar: 'hello'
    }
}
// answer no, first one returns object, second one undefined **LINE BREAKS**
```

## What are JS Promises and use cases?

- We wrap a for example `ajax` call in a promise, and then we can call the `.then` to do something with the returned values.

```javascript
function doTheThing() {
    return new Promise((resolve,reject)=>{
        $.ajax({
            url: window.location.href,
            type: 'POST',
            data: {
                key: 'value',
            },
            success: function (data) {
                resolve(data)
            },
            error: function (error) {
                reject(error)
            }
        })
    })
    
    doTheThing().then((data)=>{
        console.log(data);
        doSomethingElse();
    }).catch((error)=>{
        console.log(error)
    })
}
```

## Closure example - what does it log out?

```javascript
for (var i = 0; i < 3; i++){
    const log = () => {
        console.log(i);
    }
    
    setTimeout(log, 100)
}

// output is 3 3 3 
// var gets hoisted up to global scope
// change var to let -> 0 1 2 is output
// in this case, the loop will capture the variable in each iteration
// this way it lives in the HEAP memory and not in the call stack where it would get removed immediatly
```

## Strict mode - what is it?

- We enable this for 2 main reasons. One is that it enhances security in a sense of catching errors, type errors, reference errors, etc. Second, it makes sure we are not using any JS reserved words such as 'interface', 'private', etc...

