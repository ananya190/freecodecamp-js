# freecodecamp JavaScript

### Data types

1. null - defined to be nothing
2. boolean
3. undefined - declared, not defined
4. string
5. symbol - immutable, primitive value that's unique
6. number
7. object - can store key-value pairs


### Declaring variables

    ```js
    var variableName = "value of variable";
    ```

The data type of the value can change - it is dynamically typed.

    ```js
    variableName = 8;
    ```

There are three ways of assigning values to some location in memory:

+ var: declare variables that can be reused and changed throughout the 
program. global scope / local when declared in function.
+ let: limited in scope - to block, statement or expression it was declared in + does not let you declare a variable twice.
+ const: can never change - read-only; common practice is to name these in 
all-caps.

it's good practice to use only let and const.

#### Use strict

```
"use strict";
```

enables strict mode - catch common coding mistakes and unsafe practices.

#### Mutate array declared with const

```js
const s = [5, 7, 2];
function editInPlace() {
    "use strict";

    s[0] = 2;
    s[1] = 5;
    s[2] = 7;
}
editInPlace();
```

#### Prevent object mutation

use `Object.freeze(object_name)`

### EOL

***END LINES WITH A SEMICOLON***

It's not necessary but it's good practice to show where the lines end.

### Using quotes within strings

There are three methods by which you can accomplish this:

+ backslash: \
+ backticks: ` `
+ use the other kind of quotes

### Strings

+ length = stringVariable.length
+ string immutability: strings can be changed, but individual characters of 
the string literal cannot.

### Arrays

+ resizable
+ can store mixed data types

adding elements to arrays:

1. using indices
2. using `push()` - appends to the end of the array
3. using `unshift()` - inserts at the beginning of the array

removing elements from arrays:

1. using `pop()` - removes last element of array
2. using `shift()` - removes first element of array

### Functions

```js
function functionName([parameter1, parameter2, ...]) {
    // code
    [return]
}
```

Note: Everything within square brackets is optional

### Comparison Operators

1. regular equality: ==
2. strict equality (checks type too): ===
3. not equal value: !=
4. not equal value or type: !==

greater than, less than are all the same.

### Logical Operators

1. and: &&
2. or: ||
3. not: !

### Ternary Operators

```js
condition ? if true expression : if false expression
```

### Objects

Similar to arrays, but you use properties (keys) instead of indices to access
values.

```js
var ourDog = {
    "name": "Camper",
    "legs": 4,
    "tails": 1,
    "friends": ["everything!"]
};
```

#### Accessing Object Properties

1. Dot Notation

Setup:

```js
var testObject = {
    "hat": "ballcap",
    "shirt": "jersey",
    "shoes": "cleats"
};
```

Using dot notation:

```js
var hatValue = testObject.hat;
var shirtValue = testObject.shirt;
```

2. Bracket notation

You can use bracket notation whenever you want to, but it is ***REQUIRED***
if the property you're trying to access has a space in it.

Setup:

```js
var testObject = {
    "an entree": "hamburger",
    "my side": "veggies",
    "the drink": "water"
};
```

Using bracket notation:

```js
var entreeValue = testObject["an entree"];
var drinkValue = testObject["the drink"];
```

#### Adding and Deleting Object Properties

1. Adding

There are two ways:

    1. Dot notation:

    ```js
    testObject.mainCourse = "pasta"
    ```

    2. Bracket notation:

    ```js
    testObject[mainCourse] = "pizza"
    ```

2. Deleting

```js
delete testObject.mainCourse
```

#### Lookup Values with Objects

```js
function phoneticLookup(val) {
    var result = "";

    var lookup = {
        "alpha": "Adams"
        "bravo": "Boston",
        "charlie": "Chicago",
        "delta": "Denver",
        "echo": "Easy",
        "foxtrot": "frank"
    };

    result = lookup.val

    return result
}
```

#### Check if object has a property

```js
var myObj = {
    gift: "pony",
    pet: "kitten",
    bed: "sleigh"
};

function checkObj(checkProp){

    if (myObj.hasOwnProperty(checkProp)) {
        return myObj[checkProp];
    }
    return "Change Me!";
}
```

#### Manipulating Complex Objects

```js
var myMusic = [
{
    "artist": "Billy Joel",
    "title": "Piano Man",
    "release_year": 1973,
    "formats": [
        "CD",
        "8T",
        "LP"
    ],
    "gold": true
},
{
    "artist": "Ryan Ross",
    "title" "He's back!",
    "release_year": 2024,
    "formats": [
    "LP",
    "MP3"
    ]
}
]
```

#### Nested Objects

```js
var myStorage = {
    "car": {
        "inside": {
            "glove box": "maps",
            "passenger seat": "crumbs"
        },
        "outside": {
        "trunk": "jack"
        }
    }
};
var gloveBoxContents = myStorage.car.inside["glove box"];
```

#### Nested Arrays

```js
var myPlants = [
    {
        type: "flowers",
        list: [
            "rose",
            "tulip",
            "dandelion"
        ]
        },
    {
        type: "trees",
        list: [
            "fir",
            "pine",
            "birch"
        ]
    }
];

var secondTree = myPlants[1].list[1]
```

### Loops

#### While

runs while a condition is true

```
while (condition) {
    // code
}
```

#### For

```
for (initialization; condition; end of each iteration) {
    // code
}
```

For loops counting backwards:

```js

var ourArray = [];

for (var i = 10; i > 0; i -= 2) {
    ourArray.push(i);
}

```

Nesting for loops:

```js

function multiplyAll(arr) {}
    var product = 1；
    for (var i = 0; i < arr.length; i++) {
        for (var j = 0; j < arr[i].length; j++) {
            product *= arr[i][j];
        }
        return product;
    }
}

var product = multiplyAll([[1,2],[3,4],[5,6,7]]);

```

#### Do... While Loop

While loops will always check before running. Do... while loops run at least 
once and THEN check the condition.

```js
var myArray = [];
var i = 10;

while (i < 5) {
    myArray.push(i);
    i++;
}

// if you console.log(myArray) you'll get an empty array because i is greater
than 10, so nothing was added.

do {
    myArray.push(i);
    i++;
} while (i < 5);

// this will run once, check the condition, realize it's false and break out.
// the array is now [10].
```

### Return default value if property does not exist

```
return property || "No such value"
```

### Generate random fractions and whole numbers

Random fractions:

```js
function randomFraction() {
    return Math.random();
    // returns random fraction between 0 and 1
}
```

Random whole numbers:

```js
var randomNumberBetween0and19 = Math.floor(Math.random() * 20);
// floor rounds down

function randomWholeNumber() {
    return Math.floor(Math.random() * 10);
}
```

Random whole numbers within a range:

```js
function ourRandomRange(ourMin, ourMax) {
    return Math.floor(Math.random() * (ourMax - ourMin + 1)) + ourMin;
}
```

### parseInt

Converts string to integer or returns NaN (Not a Number).

Can also be used with a radix, i.e the number that specifies the base of the 
number in the string.

example: parseInt("10011",2);

### Anonymous and Arrow Functions

Anonymous function:

No name associated with it.

```js
var magic = function() {
    return new Date();
};
```

Arrow function that does the same thing:

```js
var magic = () => {
    return new Date();
};
```

Since we're only returning one value, we can even omit the `return` keyword and
the curly braces.

```js
var magic = () => new Date();
```

Passing arguments to arrow functions:

```js
var myConcat = (arr1, arr2) => arr1.concat(arr2);
```

Writing higher order arrow functions:

Functions like map, filter and reduce take other functions as arguments. 
This is a good place to use arrow functions.

```js
 const realNumberArray = [4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2];

 const squareList = (arr) => {
     const squaredIntegers = arr.filter(num => Number.isInteger(num) && num > 0).map(x => x * x);
     // filters it according to whether the number passed to the arrow function
     // returns true or not
     return squaredIntegers;
 };

 const squaredIntegers = squareList(realNumberArray);
 console.log(squaredIntegers);
```
### Rest operator

Allows you to create a function that takes a variable number of arguments.

```js
const sum = (function() {
        return function sum(...args) {
            return args.reduce((a,b) => a + b, 0);
        };
})();
```

### Spread operator

Spreads an array into individual parts.

Can only be used in arguments to functions or array literal

```js
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;

(function() {
    arr2 = [...arr1]; // this copies the contents of arr1 into arr2 instead
    // of just passing by reference
    arr1[0] = 'potato';
 })();
 console.log(arr2);

// OUTPUT:

// JAN, FEB, MAR, APR, MAY
```

### Destructuring assignment

To assign values from objects to variables, we use destructuring
assignment.

```js
var voxel = { x: 3.6, y: 7.4, z: 6.54 };

// old way, w/o destructuring
var x = voxel.x; // x = 3.6
var y = voxel.y; // y: 7.4
var z = voxel.z; // z: 6.54

// using destructuring
const { x: a, y: b, z: c } = voxel; // a = 3.6, b = 7.4, c = 6.54

// another example
const AVG_TEMPS = {
    today: 77.5,
    tomorrow: 79
};

function getTempOfTmrw(avgTemperatures) {
    "use strict";

    const { tomorrow: tempOfTomorrow } = avgTemperatures;

    return tempOfTomorrow;
}

console.log(getTempOfTmrw(AVG_TEMPS));
```

#### Destructuring Assignment with Nested Objects

```js
const LOCAL_FORECAST = {
    today: { min: 72, max: 83 },
    tomorrow: { min: 73.3, max: 84.6 }
};

function getMaxOfTmrw(forecast) {
    "use strict";

    const { tomorrow: { max: maxOfTomorrow }} = forecast;

    return maxOfTomorrow;
}
```

#### Destructuring Assignement to Assign Variables from Arrays

```js
const [z, x, , y] = [1, 2, 3, 4, 5, 6];
console.log(z, x, y); // 1 2 4

let a = 8, b = 6;
(() => {
    "use strict";
    [a, b] = [b, a];
 })();
 console.log(a); // 6
 console.log(b); // 8
```

#### Destructuring Assignment with Rest Operator

```js
const source = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
function removeFirstTwo(list) {
    const [ , , ...arr] = list; 
    return arr;
}

const arr = removeFirstTwo(source); // arr = [3, 4, 5, 6, 7, 8, 9, 10]

```

#### Destructuring Assignment to Pass an Object as a Function's Parameters

```js
const stats = {
    max: 56.78,
    standard deviation: 4.34,
    median: 34.54,
    mode: 23.87,
    min: -0.75,
    average: 35.85
};
const half = (function() {
    return function half({ max, min }) {
        return (max + min) / 2.0;
    };
})();
console.log(stats);
console.log(half(stats)); // 28.015
```

### Template Literals

Create strings using template literals

Created using backticks

```js
const person = {
    name: "Ryan",
    age: 35
};

// Template literal with multi-line and string interpolation

const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`;

console.log(greeting);
```

### Simple Fields

Write concise object literal declarations using simple fields.

If the key is the name of the variable, you can use simple fields.

```js
// normally

const createPerson = (name, age, gender) => {

    return {
        name: name,
        age: age,
        gender: gender
    };
};

console.log(createPerson("Ryan", 35, "male"));

// with simple fields

const createPerson = (name, age, gender) => ( { name, age, gender } );
console.log(createPerson("Ryan", 35, "male"));

```

### Declarative Functions

Objects can contain functions.

```js
// long way
const bicycle = {
    gear: 2,
    setGear: function(newGear) {
      "use strict";
      this.gear = newGear;
    }
};

bicycle.setGear(3);
console.log(bicycle.gear);

// concise way
const bicycle = {
    gear: 2,
    setGear(newGear) {
      "use strict";
      this.gear = newGear;
    }
};
```

### class Syntax

Use class Syntax to define a constructor function.

old way of creating object:

using `new` keyword.

```js
// constructor function
var SpaceShuttle = function(targetPlanet) {
    this.targetPlanet = targetPlanet;
}

var zeus = new SpaceShuttle('Jupiter');

console.log(zeus.targetPlanet);
```

The class syntax replaces the constructor function.

```js
class SpaceShuttle {
    constructor(targetPlanet) {
        this.targetPlanet = targetPlanet;
    }
}
```

### getters and setters

getters: return the value of an object's private variable to the user without
allowing them to access the variable directly.

setters: let you set the value of an object's private variable.

```js
class Book {
    constructor (author) {
        this.author = author;
    }
    // getter
    get writer(){
        return this.author;
    }
    // setter
    set writer(updatedAuthor){
        this._author = updatedAuthor;
    }
}
```

example:

```js
function makeClass() {
    class Thermostat {
        constructor(temp) {
            this._temp = 5/9 * (temp - 32); // the underscore implies that it's private.
        }
        get temperature() {
            return this._temp;
        }
        set temperature(updatedTemp) {
            this._temp = updatedTemp;
        }
    }
    return Thermostat;
}

const Thermostat = makeClass();
const thermos = new Thermostat(76);
let temp = thermos.temperature;
thermos.temperature = 26;
temp = thermos.temperature;
```

### import and export vs require

require used to be used to import functions and code from other files.

But now, with import and export, you can export code in one file and import it
in another. It also allows you to import only certain functions and variables
from a file.

`string_function.js`

```js
export const capitalizeString = str => str.toUpperCase();
```

`index.js`

```js
import { capitalizeString } from "./string_function"
const cap = capitalizeString("hello!");
console.log(cap);
// HELLO!
```

#### Use export to reuse a code block;

```js
const capitalizeString = (string) => {
    return string.charAt(0).toUpperCase() + string.slice(1);
}

export { capitalizeString };

export const foo = "bar";
export const bar = "foo";

```

#### Using * to import everything from a file;

`import * as capitalizeStrings from "capitalize_strings";`

#### Create an export fallback with export default:

export defaults are often used only when you export just one thing from a file.

```js
export default function subtract(x, y) { return x - y; }
```

#### Import a default export

```js
import subtract from "math_functions"; // since it's a default export, you
// dont need the curly braces
subtract(7,4);
```
