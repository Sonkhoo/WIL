# Contents
1. Basics
2. DOM Manipulation
3. Jquery
***
## Basics
### Variables and Data types
````js
const a=10
let name='sonkho'
let bool = false
//null = empty
console.log(type of null); //object
//undefined = not assigned
````
### Datatype conversion
````js
let val = '3'
let value = Number(val);
console.log(typeof value) // number
let value - Number(false);
console.log(value) // 0

let val1= '3'
let val2 =2
let val3= 1
console.log(val3+val2+val1) //33 as val 3 is number so val2 is also converted into number and concatinated to string 3
console.log(val1+val2+val3) //321 as val1 is '3' so val2 and val3 is not converted to number
````
for boolean conversion </br>
0, empty = **false**
1, not empty = **true**

## Compararision operators
````js
console.log(2 > 1);
console.log(2 >= 1);
console.log(2 < 1);
console.log(2 == 1);
console.log(2 != 1);

console.log("2" > 1); //true and 2 is converted into number
console.log("02" > 1);

console.log(null > 0); //false
console.log(null == 0); //false
console.log(null >= 0); // true since here type coercion occurs and null is converted into 0

console.log(undefined == 0); //false
console.log(undefined > 0); //false
console.log(undefined < 0); //false

console.log("2" === 2); //false as === used for strict checking meaning data type is also checked
````

### Strings
````js
const namee = "hitesh"
const repoCount = 50

console.log(`Hello my name is ${namee} and my repo count is ${repoCount}`);

//string methods

 const gameName = new String('hitesh-hc-com')

console.log(gameName);
console.log(gameName[0]);
console.log(gameName.__proto__);
console.log(gameName.length);
console.log(gameName.toUpperCase());
console.log(gameName.charAt(2));
console.log(gameName.indexOf('t'));

const newString = gameName.substring(0, 4)//substring
console.log(newString);

const anotherString = gameName.slice(-13, -10) //negative indexing
console.log(anotherString);

const newStringOne = "   hitesh    "
console.log(newStringOne);
console.log(newStringOne.trim()); //getting rid of spaces


const url = "https://hitesh.com/hitesh%20choudhary"

console.log(url.replace('%20', '-')) //replaces given parameter by a different parameter

console.log(url.includes('sundar')) //checks and returns boolean

console.log(gameName.split('-')); //splits on the basis of parameter into an **array**
````
more about **Strings** https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String

### Nums and Math
````js
const score = 400
console.log(score);

const balance = new Number(100)
console.log(balance);

let bal = String(balance); //type conversion
console.log(typeof bal) //string
console.log(bal.length); // string length is 3
console.log(balance.toString().length); // same output but using to.String() method
console.log(balance.toFixed(4)); // parameter gives the number of 0s after decimal point

const otherNumber = 123.8966

console.log(otherNumber.toPrecision(3)); // output is 124
console.log(otherNumber.toPrecision(4)); // output is 123.9

const hundreds = 1000000
console.log(hundreds.toLocaleString('en-IN'));

// Math Methods

console.log(Math);
console.log(Math.abs(-4));
console.log(Math.round(4.6));
console.log(Math.ceil(4.2));
console.log(Math.floor(4.9));
console.log(Math.min(4, 3, 6, 8));
console.log(Math.max(4, 3, 6, 8));

console.log(Math.random());
console.log((Math.random()*10) + 1);
console.log(Math.floor(Math.random()*10) + 1);

//Find a random number btw given range

const min = 10
const max = 20

console.log(Math.floor(Math.random() * (max - min + 1)) + min)
````
### Date and Time
````js
let myDate = new Date()
console.log(myDate.toString());//Fri May 31 2024 04:34:43 GMT+0530 (India Standard Time)
console.log(myDate.toDateString());// Fri May 31 2024
console.log(myDate.toTimeString());// 04:34:43 GMT+0530 (India Standard Time)
console.log(myDate.toLocaleString()); // 31/5/2024, 4:34:43 am
console.log(typeof myDate); //object
console.log(myDate.toJSON()); //2024-05-30T23:04:01.489Z
console.log(myDate.toLocaleDateString()); //31/5/2024
console.log(myDate.toLocaleTimeString()); // 4:34:01 am


let myCreatedDate = new Date(2023, 0, 23) //23/1/2023, 12:00:00 am

let myCreatedDate = new Date(2023, 0, 23, 5, 3)// 23/1/2023, 5:03:00 am
console.log(myCreatedDate.toLocaleString());
````
