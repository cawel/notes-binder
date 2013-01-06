# CoffeeScript

An object is a list of keys and values
```
my_object = 'color': '#eee', 'font-weight': 'bold'
```

here is a coffeeList object which wraps a function called 'init'
```
coffeeList =
  init: ->
    $('.drink a').click (e) ->
      e.preventDefault()
      alert $(@).text()
coffeeList.init()
```