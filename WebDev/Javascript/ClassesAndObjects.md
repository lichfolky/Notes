var myCar = new Object();
myCar.make = 'Ford';
myCar.model = 'Mustang';
myCar.year = 1969;

var myCar = {
    make: 'Ford',
    model: 'Mustang',
    year: 1969
};

myCar['make'] = 'Ford';
myCar['model'] = 'Mustang';
myCar['year'] = 1969;

var myObj = new Object(),
    str = 'myString',
    rand = Math.random(),
    obj = new Object();

## Enumerate the properties of an object
ways to list/traverse object properties:
+ for...in loops
This method traverses all enumerable properties of an object and its prototype chain
+ Object.keys(o)
This method returns an array with all the own (not in the prototype chain) enumerable properties' names ("keys") of an object o.
+ Object.getOwnPropertyNames(o)
This method returns an array containing all own properties' names (enumerable or not) of an object o.

```
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}
var mycar = new Car('Eagle', 'Talon TSi', 1993);
```

You can add a property to a previously defined object type by using the prototype property. This defines a property that is shared by all objects of the specified type, rather than by just one instance of the object. The following code adds a color property to all objects of type Car, and then assigns a value to the color property of the object car1.

Car.prototype.color = null;
car1.color = 'black';

methods:
```
objectName.methodname = functionName;

var myObj = {
  myMethod: function(params) {
    // ...do something
  }

  // OR THIS WORKS TOO

  myOtherMethod(params) {
    // ...do something else
  }
};
```
```
function Manager() {
  Employee.call(this);
  this.reports = [];
}
Manager.prototype = Object.create(Employee.prototype);
Manager.prototype.constructor = Manager;

function WorkerBee() {
  Employee.call(this);
  this.projects = [];
}
WorkerBee.prototype = Object.create(Employee.prototype);
WorkerBee.prototype.constructor = WorkerBee;
```

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model