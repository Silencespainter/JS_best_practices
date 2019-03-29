[JavaScript best practices W3C](https://www.w3.org/wiki/JavaScript_best_practices)
## Avoid globals
### Module Pattern

```javascript
myModule = function(){
  var current = null;
  function init(){...}
  function change(){...}
  function verify(){...}
}();
```
It is easy to call functions and access variables from other places without having to go through the myModule:

```javascript
myModule = function(){
  var current = null;
  function init(){...}
  function change(){...}
  function verify(){...}
  return{
    init:init,
    set:change
  }
}();
```

Calling myModule.set() will now invoke the change() method.

```javascript
myModule = function(){
  var current = null;
  function init(){...}
  function change(){...}
  function verify(){...}
  return{
    init:init,
    set:change
  }
}();

myModule.set()
```

## Naming js
- [https://code.tutsplus.com/articles/9-confusing-naming-conventions-for-beginners--net-15584](https://code.tutsplus.com/articles/9-confusing-naming-conventions-for-beginners--net-15584)

### _underscore 
__It is private or protected, use__

```javascript
var Person = (function() {
   var _trueAge = 50,
       _trueWeight = 140;
 
   return {
      age : _trueAge - 15,
      weight : _trueWeight - 30
   };  
})();
 
Person.age; // 35
Person.weight; // 110
Person._trueAge; // undefined (cause it's private, yo)
```

### UPPERCASE Constants
If the variable is a constant, never change his value, write it uppercase
```javascript
var SPEEDOFLIGHT = 299,792; // kilometers per second
```

### JavaScript Hungarian Prefixes

a - array
b - boolean
f - float
fn - function
i - integer
n - node
o - object
s - string

```javascript
var aData = [1, 2, 3];
var bFound = false;
var fGoldenRatio = 1.618;
var fnCallback = function() { };
var iCurrentPage = 1;
var nNewRow = document.createElement("tr");
var oSettings = {
    type: "GET",
    url: "test.json",
    dataType: "jsonp"
};
var sLabel = "First Name";
```

More: [https://www.darklaunch.com/javascript-hungarian-notation-variable-prefix-naming-convention](https://www.darklaunch.com/javascript-hungarian-notation-variable-prefix-naming-convention)


### Capital First Letter: 'Class' JS
In old JavaScript version, we don't have classes but constructor functions yes

```javascript
function Person(name) {
  // If the new keyword is absent, the constructor will be the window.
  // In this case, compensate, and return a new instance
  if ( this.constructor !== Person ) {
    return new Person(name);
  }
 this.name = name;
}

// Intentionally forgot the "new" keyword 
var Joey = Person('Joey');
Joey.name; // Joey
```

# Performance JS

## jQuery: data-atributes performance
- [http://www.nicoespeon.com/en/2013/05/jquery-data-and-performance/](http://www.nicoespeon.com/en/2013/05/jquery-data-and-performance/)



