# Javascript

Languages: [Spanish](https://github.com/danielmoreno58/documentation/tree/master/JS/README.es.md), [English](https://github.com/danielmoreno58/documentation/tree/master/JS/README.md)

Frameworks:

* [Jquery](https://github.com/danielmoreno58/documentation/tree/master/JS/JQUERY/README.md)


## Operator precedence

B O DM AS

B = Brackets

O = pOwers

DM = Division | Multiplication

AS = Adition | Substraction

[Precedence Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

## How javascript runs

Javascript runs as we a read a book, from left to right, to the first line to the last line.

## Primative Data

|     Data     |         Syntax         |
| -----------  | ---------------------- |
|   String     |   "This is a string"   |
|    Number    |  200, 2000, 3.15, 4.4  |
|   Boolean    |      True , False      |
|     Null     |          null          |
|   Undefined  |       undefined        |

## Variables 

For define a variable we just write the following syntax:

`var i=0;`

We can put any type of primative data and objets in a variable, and the cool thing about javascipt is that we can redefine the value of the variable even of type data.

For :

`var i=0;` _This is an integer_

`i='hello';` _Now is a string_

`i=true;` _Now is a boolean_

### Constant

The constant is a type of variable that by the logic of the name is constant, it means that once you define it you cannot change the value, the correct syntax is the following one:

`const = 'variable constant';`

## Functions

Functions are procedures that we do in every day life with or without parameters.

The syntax without parameters is like this:

```js
function name(){
  //Code here
}
```

The syntax with parameters is like this:

```js
function name(Parameter_1, Parameter_2){
  //Code here
}
```

### Calling a function

In our code for calling our function we put:

```js
  //Code
  name();
```

## Arrays

Array is an object that define a list of primative data, for :

`var students = ["Daniel", "Daniela", "Jose", "Pancho", "Josefina"];`

### Calling an array

Calling an array is just simple as writing:

**Example 1:**
```js
  var array = ["value 1", "value 2", "value 3"];
  console.log(array[0]); //Print value 1 as result
```

### Helpful methods in array

_Notes:_

1. Parameters are indicated as **p1 = parameter 1**, **p2 = parameter 2** and so on.
2. For multiple parameters there are indicated as **mp**

|     Method            |                                                      Usage                                                                                     |
| --------------------- | -------------------------------------------------------------------------------------------------------------------                            |
| .length               | Return the size of the array as a number                                                                                                       |
| .shift()              | Eliminates the first element of the array and return the size of the array                                                                     |
| .unshift(mp)          | Add the parameters that you put in the method at the first of your array and returns the size of the array. _Requires parameter_               |
| .pop()                | Eliminates the last element of the array and return the size of the array                                                                      |
| .push(mp)             | Add the parameters that you put in the method at the end of your array and returns the size of the array. _Requires parameter_                 |
| .splice(p1, p2, mp)   | Define where do you want to start modify your array _(p1)_, eliminates the number of properties _(p2)_ and add many propierties as you like _(mp)_. _Require parameters_  |

## Objects

Objects in Javascript are defined in this way:

`var object = {};`

The objects can contain primative data, functions and other objects as well, here's an example to an object:

```js
var car = {
  //Primative Data
  car_name: "Ford Fiesta",
  wheels: 4,
  //Functions
  run: function (){ return "run"; },
  //Objects
  car_companies: ["BMW", "Volvo", "Audi", "Ford"],
  driver: {
    name: "Daniel",
    age: 21
  },
};
```

### Objects inside Objects (Embedded)

We can define objects inside objects having more logic in our program, is like we define earlier:

```js
var car = {
    make: "volvo",
    speed: 160,
    engine: {
        size: 2.0,
        make: "bmw",
        fuel: "petrol",
        pistons:[
            { maker: "BMW" },
            { maker: "BMW2" }
        ]
    },
    drive: function(){ return "drive"; }
};
```

### Calling objects

Calling objects is easy as writing the name of the object:

`var mycar = car;`

### Calling properties of objects (Member Access)

We can call the properties of an object just by writing:

**Example 1:**
```js

  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };

  var maker = car.make;
  console.log(maker); //Print volvo as result
```

**Example 2:**
```js

  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };

  var car_size = car.engine.size;
  console.log(car_size); //Print 2.0 as result
```

**Example 3:**
```js

  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };

  var piston_by_maker = car.engine.pistons[0].maker;
  console.log(piston_by_maker); //Print BMW as result
```

**Example 4:**
```js

  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };

  var maker = car["engine"]["pistons"][0]["maker"];
  console.log(maker); //Print BMW as result
```

**Example 5:**
```js

  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };

  var engine = "engine";
  var numberarray = 0;
  var maker = car[engine]["pistons"][numberarray]["maker"];
  console.log(maker); //Print BMW as result
```

### Calling functions of objects (Computed Access Member)

**Example 1:**
```js
  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };

  var drive = car.drive();
  console.log(drive); //Print drive as result
```

**Example 2:**
```js

  var array = [ 
      "string",
      100,
      [ "embed", 200 ],
      { car: "ford" },
      function(){ return "drive"; }
  ];

  var drive = array[4]();
  console.log(drive); //Print drive as result
```

### Create a new property and method

**Example 1:**

If we have an existing object such like this:

```js
  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };
```

And we want to add another property we just add:

`car.property_name = "something";`

So, for example we can add the version of the car like this:

`car.version = "v1";`

And then the object will be like this:

```js
  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
      version: "v1"; //New property added
  };
```

**Example 2:**

We can also created functions properties as well

`car.stop = function(){ return "stop"; };`

That will return:

```js
  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; },
      stop: function(){ return "stop"; } //New function added
  };
```

### Delete properties and methods

For delete a property or method from an object we use the keyword `delete`, for example we have the next object:

```js
  var car = {
      make: "volvo",
      speed: 160,
      engine: {
          size: 2.0,
          make: "bmw",
          fuel: "petrol",
          pistons:[
              { maker: "BMW" },
              { maker: "BMW2" }
          ]
      },
      drive: function(){ return "drive"; }
  };
```

And if we want to delete a property we just write:

`delete car.make;`

### Constructors

Constructors is a function that has some properties and methods with the difference that the first letter should be capitalized.

For example:

```js
  function Apple(color, weight){
    color: "red",
    weight: 20
  }
```

### Prototype

The prototype is a method that calls a construcutor and add share properties and values

```js

//Prototype
Apple.prototype = {
  eat(),
  throw()
}
```
## Useful methods

| Method              |                                         Usage                                        | Resource                           |
| ------------------- | ------------------------------------------------------------------------------------ | ---------------------------------- |
| onload();           |                                                                                      | _[Source](https://bit.ly/2Qsr2is)_ | 

## References:

Udemy free course: https://www.udemy.com/javascript-essentials/

SessionStorage: https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage