# Contents
1. Basics
2. DOM Manipulation
3. Jquery
***
## Basics
### Variables and Primitive Data types
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

console.log(newDate.getMonth() + 1); //to get the month
console.log(newDate.getDay()); //to get the day


let myCreatedDate = new Date(2023, 0, 23) //23/1/2023, 12:00:00 am

let myCreatedDate = new Date(2023, 0, 23, 5, 3)// 23/1/2023, 5:03:00 am
console.log(myCreatedDate.toLocaleString());

//Custom object for date to get custom output results according to users

console.log(newDate.toLocaleString('default', {
    weekday: "short",
})); // Output is Fr and if weeekday: "long" output becomes Friday

//Time

console.log(myCreatedDate.getTime()); // to get the time in milisecond from the created date to today's date
console.log(Math.floor(Date.now()/1000)); // to convert it into seconds
````
### Datatypes Summary

Primitive Dataypes

1. String
2. Number
3. Boolean
4. Null
5. Undefined
6. BigInt
7. Symbol
   
````js
//  Primitive

//  7 types : String, Number, Boolean, null, undefined, Symbol, BigInt

const score = 100
const scoreValue = 100.3

const isLoggedIn = false
const outsideTemp = null
let userEmail;

const id = Symbol('123')
const anotherId = Symbol('123')

console.log(id === anotherId);

// const bigNumber = 3456543576654356754n



// Reference (Non primitive)

// Array, Objects, Functions

const heros = ["shaktiman", "naagraj", "doga"];
let myObj = {
    name: "hitesh",
    age: 22,
}

const myFunction = function(){
    console.log("Hello world");
}
````

Non - Primitive Datatypes

1. Arrays
2. Objects
3. Functions

### Arrays
````js
// array

const myArr = [0, 1, 2, 3, 'Hello', false] //Array Declaring
const myHeors = ["shaktiman", "naagraj"]

const myArr2 = new Array(1, 2, 3, 4) //Array declaring using object

console.log(myArr[1]); //aray indexing


// Array methods

myArr.push(6)
myArr.push(7)
myArr.pop()
console.log(myArr.includes(9)); // returns boolean
console.log(myArr.indexOf(3)); // returns index of element
const newArr = myArr.join('-') // adds the all the elements of an array into a string joined by the parameter provided 

myar1=Array.from("Hitesh") //breaks the string into array
console.log(Array.isArray([{}])) //checks if the parameter passed is an array
console.log(Array.from({name: "hitesh"})) // returns an empty array as it cannot iterate through objects

let score1 = 100
let score2 = 200
let score3 = 300

console.log(Array.of(score1, score2, score3)); //returns an array of the parameters provided


// Shift and Unshift

const myArr = [0, 1, 2, 3, 'Hello', false]
myArr.unshift(9) //adds the parameter passed to the first index of the array also returns the length of the array after inserting

const val= myArr.unshift(9)
console.log(val); // val is the length of the array after inserting

myArr.shift() //removes the first index of the array


// slice, splice in Arrays

const myArr = [0, 1, 2, 3, 'Hello', false]

const myn1 = myArr.slice(1, 3) // copies the elements from the inital array from index 1-2
console.log(myn1); //[1,2]
console.log("B ", myArr);//[0, 1, 2, 3, 'Hello', false]


const myn2 = myArr.splice(1, 3) // cuts the elemets from the initial array from index 1-3
console.log(myn2); // [1,2,3]
console.log("C ", myArr);//[0, 'Hello', false]


// Joining an array

const marvel_heros = ["thor", "Ironman", "spiderman"]
const dc_heros = ["superman", "flash", "batman"]

marvel_heros.push(dc_heros)  // pushes the array passed as argument as an individual array rather than pushing the elements 
console.log(marvel_heros[3][1]); // Output is flash

const all_new_heros = [...marvel_heros, ...dc_heros] //Joins the elements of both the arrays and returns an array


//Flatening an array

const another_array = [1, 2, 3, [4, 5, 6], 7, [6, 7, [4, 5]]]

const real_another_array = another_array.flat(1) //flats one time recursively. infinity can also be given to get flattened array
console.log(real_another_array);
````
### Objects
````js

// singleton method of object creation

Object.create


// object literals

const mySym = Symbol("key1") // declaring a symbol

const JsUser = {
    name: "Hitesh",
    "full name": "Hitesh Choudhary",
    [mySym]: "mykey1",
    age: 18,
    location: "Jaipur",
    email: "hitesh@google.com",
    isLoggedIn: false,
    lastLoginDays: ["Monday", "Saturday"]
}

console.log(JsUser.email) // to access property
console.log(JsUser["full name"]) // to access string property
console.log(JsUser[mySym]) // to access symbol


// Object methods

Object.freeze(JsUser)
console.log(Object.keys(JsUser));
console.log(Object.values(JsUser));
console.log(Object.entries(JsUser));
console.log(JsUser.hasOwnProperty('isLoggedIn'));


//Function inside an Object

JsUser.greeting = function(){
    console.log("Hello JS user");
} // A propety greeting is created which stores this function

JsUser.greetingTwo = function(){
    console.log(`Hello JS user, ${this.name}`);
} // this keyword can be used inside a function in an object to pass the properties of the object as a parameter to the function


// Object inside an object

const regularUser = {
    email: "some@gmail.com",
    fullname: {
        userfullname: {
            firstname: "hitesh",
            lastname: "choudhary"
        }
    }
}

console.log(regularUser.fullname.userfullname.firstname);


// Joining an object

const obj1 = {1: "a", 2: "b"}
const obj2 = {3: "a", 4: "b"}
const obj4 = {5: "a", 6: "b"}

const obj3 = {...obj1,...obj2,...obj4}
console.log(obj3);


// Changing names of keys in an object

const course = {
    coursename: "js in hindi",
    price: "999",
    courseInstructor: "hitesh"
}
const {courseInstructor: instructor} = course
