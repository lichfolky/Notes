https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript

# strings

multi-line string:
```
let multiLineString = `this
is
ok`
```
or
```
console.log('string text line 1\n\
string text line 2');
```

```
const five = 5;
const ten = 10;
console.log(`Fifteen is ${five + ten} and not ${2 * five + ten}.`);
// "Fifteen is 15 and not 20."
```

Unicode escape sequences
The Unicode escape sequences require at least four hexadecimal digits following \u.

`'\u00A9' `


# loops

for arrays:
```
const arr = [3, 5, 7];
arr.foo = 'hello';

for (let i in arr) {
   console.log(i); // logs "0", "1", "2", "foo"
}

for (let i of arr) {
   console.log(i); // logs 3, 5, 7
}
```

# Function Closures


```
function outside(x) {
  function inside(y) {
    return x + y;
  }
  return inside;
}


fn_inside = outside(3); // Think of it like: give me a function that adds 3 to whatever you give

result = fn_inside(5); // returns 8

result1 = outside(3)(5); // returns 8
```

the variable it's preserved untill the returned inside is no longer accessible.

```
var getCode = (function() {
  var apiCode = '0]Eal(eh&2';    // A code we do not want outsiders to be able to modify...

  return function() {
    return apiCode;
  };
})();

getCode();    // Returns the apiCode
```
????
```
var createPet = function(name) {
    var sex;

    return {
        setName: function(newName) {
            name = newName;
        },

        getName: function() {
            return name;
        }
    }
}
```

## The arguments object
The arguments of a function are maintained in an array-like object. Within a function, you can address the arguments passed to it as follows:
`arguments[i]`
So, the first argument passed to a function would be arguments[0]. The total number of arguments is indicated by arguments.length.

```
function myConcat(separator) {
   var result = ''; // initialize list
   var i;
   // iterate through arguments
   for (i = 1; i < arguments.length; i++) {
      result += arguments[i] + separator;
   }
   return result;
}

// returns "elephant; giraffe; lion; cheetah; "
myConcat('; ', 'elephant', 'giraffe', 'lion', 'cheetah');
```

Note: The arguments variable is "array-like", but not an array. It is array-like in that it has a numbered index and a length property. However, it does not possess all of the array-manipulation methods.


## default parameters
```
function multiply(a, b = 1) {
  return a * b;
}

multiply(5);
```

## rest parameters

The rest parameter syntax allows us to represent an indefinite number of arguments as an array.

In the following example, the function multiply uses rest parameters to collect arguments from the second one to the end.
```
function multiply(multiplier, ...theArgs) {
  return theArgs.map(x => multiplier * x);
}

var arr = multiply(2, 1, 2, 3);
console.log(arr); // [2, 4, 6]
```

## Arrow functions
an arrow function does not have its own this, arguments, super, or new.target.
is always anonymous.
has no binding of `this`.

## `this`
```
function Person() {
  var self = this; // Some choose `that` instead of `self`.
                   // Choose one and be consistent.
  self.age = 0;

  setInterval(function growUp() {
    // The callback refers to the `self` variable of which
    // the value is the expected object.
    self.age++;
  }, 1000);
}
```

## Destructuring
```
var foo = ['one', 'two', 'three'];

// without destructuring
var one   = foo[0];
var two   = foo[1];
var three = foo[2];

// with destructuring
var [one, two, three] = foo;
```

## Operators

+ Strict equal (`===`)	Returns true if the operands are equal and of the same type

+ Increment (`++`)	Unary operator. Adds one to its operand. If used as a prefix operator (++x), returns the value of its operand after adding one; if used as a postfix operator (x++), returns the value of its operand before adding one.

+ Unary plus (`+`)	Unary operator. Attempts to convert the operand to a number, if it is not already.
```
+"3" returns 3.
+true returns 1.
```
+ `??`  works like `||`, but it only returns the second expression, when the first one is "nullish", i.e. null or undefined. It is thus the better alternative to provide defaults, when values like '' or 0 are valid values for the first expression, too.

+ ternary operator `condition ? val1 : val2`
```
var status = (age >= 18) ? 'adult' : 'minor';
```

+ The comma operator (`,`) simply evaluates both of its operands and returns the value of the last operand.

+ The delete operator deletes an object's property. The syntax is:
```
delete object.property;
delete object[propertyKey];
delete property; // legal only within a with statement
```
If the delete operator succeeds, it removes the propery from the object. Trying to access it afterwards will yield undefined. The delete operator returns true if the operation is possible; it returns false if the operation is not possible.

Since arrays are just objects, it's technically possible to delete elements from them. This is however regarded as a bad practice, try to avoid it. To achieve that behavior, it is much better to just overwrite the element with the value undefined. To actually manipulate the array, use the various array methods such as splice.

+ `typeof` operand

+ The `void` operator specifies an expression to be evaluated without returning a value.

+ The `in` operator returns true if the specified property is in the specified object.
```
var mycar = { make: 'Honda', model: 'Accord', year: 1998 };
'make' in mycar;  // returns true
'name' in mycar; // returns false
```

+ objectName `instanceof` objectType

## keywords
`this`
```
this['propertyName']
this.propertyName
```
```
function validate(obj, lowval, hival) {
  if ((obj.value < lowval) || (obj.value > hival))
    console.log('Invalid Value!');
}
```
You could call validate in each form element's onChange event handler, using this to pass it to the form element, as in the following example:
```
<p>Enter a number between 18 and 99:</p>
<input type="text" name="age" size=3 onChange="validate(this, 18, 99);">
```
`super`
```
super([arguments]); // calls the parent constructor.
super.functionOnParent([arguments]);
```

## Internationalization

The Intl object is the namespace for the ECMAScript Internationalization API

```
const msPerDay = 24 * 60 * 60 * 1000;

// July 17, 2014 00:00:00 UTC.
const july172014 = new Date(msPerDay * (44 * 365 + 11 + 197));

const options = { year: '2-digit', month: '2-digit', day: '2-digit',
                hour: '2-digit', minute: '2-digit', timeZoneName: 'short' };
const americanDateTime = new Intl.DateTimeFormat('en-US', options).format;

console.log(americanDateTime(july172014)); // 07/16/14, 5:00 PM PDT
```

## regular expressions

`let re = /ab+c/;`
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions

## arrays

`let arr = new Array(arrayLength)`
equals to:

```
let arr = []
arr.length = arrayLength
```

Note: In the above code, arrayLength must be a Number. Otherwise, an array with a single element (the provided value) will be created. Calling arr.length will return arrayLength, but the array doesn't contain any elements. A for...in loop will not find any property on the array.

```
let arr = ['one', 'two', 'three']
arr[2]          // three
arr['length']   // 3
```

If you know that none of the elements in your array evaluate to false in a boolean context—if your array consists only of DOM nodes, for example—you can use a more efficient idiom:
```
let divs = document.getElementsByTagName('div')
for (let i = 0, div; div = divs[i]; i++) {
  /* Process div in some way */
}
```
This avoids the overhead of checking the length of the array, and ensures that the div variable is reassigned to the current item each time around the loop for added convenience.

```
let colors = ['red', 'green', 'blue']
colors.forEach(function(color) {
  console.log(color)
})
```
or
```
colors.forEach(color => console.log(color))
```

+ concat() joins two or more arrays
`myArray = myArray.concat('a', 'b', 'c')`
+ join(delimiter = ',')
push
pop
shift
unshift
+ slice(start_index, upto_index) extracts a section of an array and returns a new array.
+ splice(index, count_to_remove, addElement1, addElement2, ...) removes elements from an array and (optionally) replaces them. It returns the items which were removed from the array.
+ indexOf(searchElement[, fromIndex]) searches the array for searchElement and returns the index of the first match.
+ map
+ filter
+ every(callback[, thisObject]) returns true if callback returns true for every item in the array.
+ reduce and reduceRight

## WeakMap for private obj data
https://fitzgeraldnick.com/2014/01/13/hiding-implementation-details-with-e6-weakmaps.html

```
const privates = new WeakMap();

function Public() {
  const me = {
    // Private data goes here
  };
  privates.set(this, me);
}

Public.prototype.method = function () {
  const me = privates.get(this);
  // Do stuff with private data in `me`...
};

module.exports = Public;
```

## Sets
Deleting Array elements by value (arr.splice(arr.indexOf(val), 1)) is very slow.
Set objects let you delete elements by their value. With an array, you would have to splice based on an element's index.
Set objects store unique values. You don't have to manually keep track of duplicates.
