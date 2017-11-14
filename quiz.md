+# Javascript Evaluation

1. What is a potential pitfall with using typeof bar === "object" to determine if bar is an object? How can this pitfall be avoided?
Three equal comparison operator is for 'identical' comparison operator. 

2. What will the code below output to the console and why?
   
```javascript
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```

3. What is the significance of wrapping the entire content of a JavaScript source file in a function block?


4. What will the code below output to the console and why?
```javascript
 (function(){
    return typeof arguments;
  })();
```
typeof arguments == 'function'
Returns 'function' for methods and functions

5. What will the code below output to the console and why?
```javascript
  var foo = {
    bar: function() { return this.baz; },
    baz: 1
  };
  (function(){
    return typeof arguments[0]();
  })(foo.bar);
```

6. What will the code below output to the console and why?
```javascript
  var x = 1;
  if (function f(){}) {
    x += typeof f;
  }
  x;
```
Undefined

7. What will the code below output to the console and why?
```javascript
const KEY = 'white_rabbit';
if (true) {
  const KEY = 'ginger_rabbit';
}
console.log(KEY);
```
const KEY = 'ginger_rabbit';
const KEY was redeclarated

8. What will the code below output to the console and why?
```javascript
let x = 42;
if (true) {
  console.log(x);
  let x = 1337;
}
```

9. Rewrite the following code as Ecmascript Arrow Function
```
var double = function (i) {
  return i * 2;
};
```
var double = i => i*2;

10. Explain the difference between classical inheritance and prototypal inheritance.
In prototypal inheritance objects inherit directly from other objects. 
In classical inheritance classes inherit from classes and create subclass relationships. 
JavaScript doesn't have classical inheritance.

11. Using the following class
    ```
    class Logger {
      constructor (type = "Info") {
        this.type = type;
      }
    
      get current()     { return `Logger: ${this.type}`; }
      set current(type) { this.type = type; }
    
      static create(type) { return new this(type); }
      log (message)       { console.log(message) }
    }
    ```
    
    print to the console 'Hello World'

    
