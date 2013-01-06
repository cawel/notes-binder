# Backbone.js

## Course #1: Backbone.js basics

Define a model:
```
Person = Backbone.Model.extend({
  initialize: function(){
    alert("Welcome to this world");
  }
});
    
var person = new Person;
```

Define a view with a template:
```
var AppointmentView = Backbone.View.extend({
  template: _.template('<span>{title}</span>'),
  render: function(){
    var attributes = this.model.toJSON();
    this.$el.html(this.template(attributes));
  }
});
```


Fetching data from the server:
```
var user = new Person({id: 1});

// The fetch below will perform GET /user/1
user.fetch({
  success: function (user) {
    alert(user.toJSON());
  }
})
```

Syncing data with the server:
```
user.save({name: 'Davis'}, {
  success: function (model) {
    alert(user.toJSON());
  }
});
```


made the defaults a function, so that date can be instanciated at instanciation time:
```
Backbone.Model.extend({
  defaults: function(){
    return {
      name: 'Fetus',
      date: new Date()
    }
});
```