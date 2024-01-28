# ECMA Script 2015 (ES6)

1. Arrow Functions - create one-liners, better readable code and easier to understand.
2. The `let` keyword - allows block scoping

```javascript
var fs = [];
for(var i = 0; i < 10; i++){
    fs.push(function (){
        console.log(i)
    })
}

fs.forEach(function (f) {
    f();
})

// this prints out 10 10 10 10 10 10 10 10 10 10
// but if we do 

var fs = [];
for(let i = 0; i < 10; i++){
    fs.push(function (){
        console.log(i)
    })
}

fs.forEach(function (f) {
    f();
})

// this prints out 0 1 2 3 4 5 6 7 8 9
```