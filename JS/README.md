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

## Primative Data

|     Data     |         Syntax         |
| -----------  | ---------------------- |
|   String     |   "This is a string"   |
|    Number    |  200, 2000, 3.15, 4.4  |
|   Boolean    |      True , False      |
|     Null     |          null          |
|   Undefined  |       undefined        |


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

Array is an object that define a list of primative data, for example:

`var students = ["Daniel", "Daniela", "Jose", "Pancho", "Josefina"];`

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

Example 1:
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

Example 2:
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

Example 3:
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

### Calling functions of objects (Computed Access Member)

Example 1:
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

Example 2:
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

## References:

SessionStorage: https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage