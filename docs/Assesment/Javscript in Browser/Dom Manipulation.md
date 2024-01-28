# Dom Manipulation

## Different selectors

```javascript
document.querySelector('.class')
document.querySelector('#id').textContent = 'Correct Number'
```

## Click events

```javascript
document.querySelector('.button').addEventListener('click',function() {
    console.log('pressed')
})
```

## Keyboard events
```javascript
document.addEventListener('keydown',function(e) {
    if(e.key === "Escape"){
        //do something
    }
})
```

## Classes

```javascript
document.querySelector('.modal').classList.add('show')
document.querySelector('.modal').classList.remove('show')
document.querySelector('.modal').classList.toggle('show')
```

## Styles

```javascript
document.querySelector('body').style.backgroundColor = '#FFFFFF'
```