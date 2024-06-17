# Contents
1. Basics
2. Control Flow
3. Iterations
4. DOM Manipulation
5. Jquery
6. Events
7. Fetch and Promises
8. Class and OOP
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
````
### Functions
````js
function addTwoNumbers(number1, number2){  // Definind a function

    return number1 + number2
}

const result = addTwoNumbers(3, 5) // calling a function by passing arguments


// Passing parameter inside a function

function calculateCartPrice(val1, val2, ...num1){ 
    return [val1 +val2 + num1[0] + num1[1], num1]
}

console.log(calculateCartPrice(100, 100, 100, 100)) // output is [ 400, [ 100, 100 ] ]
````
### Scope
Each {} is a scope and there is global scope also. A variable declaraed in an outer scope can be used in an inner scope but vice versa not possible.
````js
function one(){
    const username = "hitesh"

    function two(){
        const website = "youtube"
        console.log(username); // will be printed
    }
    two()
    console.log(website); // wont be printed
}
one()
````
### DIfferent types of functions
````js
// Using arrow function and parenthesis

const addTwo = (num1, num2) => {
    return num1 + num2 //you cannot use console.log in an arrow function
}
console.log(addTwo(2,3));

// Using arrow function and  first bracket but should be in a sinle line

const addTwo2 = (num1, num2) =>  (num1 + num2)
const addTwo2 = (num1, num2) => ({username: "hitesh"}) // an object can also be printed.
console.log(addTwo2(3, 4))

// Immediately Invoked Function Expressions (IIFEE)

// it is used when we do not want the global scope to polute the value returned by the function. 
//We just apply first bracket and directly call the function.

(function chai(){
    // named IIFE
    console.log(`DB CONNECTED`);
})();

( (name) => {
    console.log(`DB CONNECTED TWO ${name}`);
} )('hitesh')
````
## Control Flow

### if else statements
````js
if ( temperature === 40 ){
    console.log("temperature is 40");
} 
else if(temperature < 40 ) {
    console.log("temperature is lesser than 40");
}
else{
    console.log("temperature is more than 40");
}
````
**Comparision Operators** :
// <, >, <=, >=, ==, !=, ===, !==

### Relational Operator: && , ||
 ````js
const userLoggedIn = true
const debitCard = true
const loggedInFromGoogle = false
const loggedInFromEmail = true

if (userLoggedIn && debitCard && 2==3) {
    console.log("Allow to buy course");
}

if (loggedInFromGoogle || loggedInFromEmail) {
    console.log("User logged in");
}
````
### Switch Case statement
````js
const month = "march"

switch (month) {
    case "jan":
        console.log("January");
        break;
    case "feb":
        console.log("feb");
        break;
    case "march":
        console.log("march");
        break;
    case "april":
        console.log("april");
        break;

    default:
        console.log("default case match");
        break;
}
````
### Truthy and Falsy Values

Truthy values:
````js truth "0", 'false', " ", [], {}, function(){}````

Falsy values: 
````js false, 0, -0, BigInt 0n, "", null, undefined, NaN````

## Iterations

### For Loops
````js
for (let i = 1; i <= 3; i++) {
   for (let j = 1; j <= 3; j++) {
    console.log(`Inner loop value ${j} and inner loop ${i}`);
   }  
}

let myArray = ["ironman", "batman", "spiderman"]
for (let i = 0; i < myArray.length; i++) {
    console.log(myArray[i]);   
}
````
### Break and Continue
Break : Breaking out of the loop stoping it from executing
Continue : It skips the iteration of the loop
````js
for (let index = 1; index <= 10; index++) {
    if (index == 5) {
        console.log(`Detected 5`);
        break
    }
   console.log(`Value of i is ${index}`);  
}

for (let index = 1; index <= 10; index++) {
    if (index == 5) {
        console.log(`Detected 5`);
        continue
    }
   console.log(`Value of i is ${index}`); // this statement wont be executed when cond. is satisfied 
}
````
### While and DoWhile Loop
````js
let arr = 0
while (arr < myArray.length) {
    //console.log(`Value is ${myArray[arr]}`);
    arr = arr + 1
}

let score = 11

do {
    console.log(`Score is ${score}`);
    score++
} while (score <= 10);
````
### For of Loop
````js
["", "", ""]
[{}, {}, {}] 

//common datatypes used in js

//for arrays

const arr = [1, 2, 3, 4, 5]
for (const num of arr) {
    console.log(num);
}

//for strings

const greetings = "Hello world!"
for (const greet of greetings) {
    console.log(`Each char is ${greet}`)
}

//for maps

const map = new Map()
map.set('IN', "India")
map.set('USA', "United States of America")
map.set('Fr', "France")
map.set('IN', "India")
for (const [key, value] of map) {
    console.log(key, ':-', value);
}

//for objects for of loop cant iterate thorugh it.
````
### For In Loop
````js

// for objects

const myObject = {
    js: 'javascript',
    cpp: 'C++',
    rb: "ruby",
    swift: "swift by apple"
}
for (const key in myObject) {
    console.log(`${key} shortcut is for ${myObject[key]}`);
}

//for arrays

const programming = ["js", "rb", "py", "java", "cpp"]

for (const key in programming) {
    console.log(programming[key]); //here keys are the indexes
}
````
### ForEach Loop
* forEach doesnt have the return keyword.
````js
let coding=['js','node', 'react', 'next','express']

//forEach for normal callback function

coding.forEach( function (val){ 
    console.log(val);
} )


//forEach for arrow function

coding.forEach( (item) => {
    console.log(item);
} )


//passing a function as reference in forEach

function printMe(item){
    console.log(item);
}

coding.forEach(printMe)


//different parameter for forEach

coding.forEach( (item, index, arr)=> {
    console.log(item, index, arr);
} )


//forEach loop for an array of Objects

const myCoding = [
    {
        languageName: "javascript",
        languageFileName: "js"
    },
    {
        languageName: "java",
        languageFileName: "java"
    },
    {
        languageName: "python",
        languageFileName: "py"
    },
]

myCoding.forEach( (item) => {
    console.log(item); // prints the objects
    console.log(item.languageName); //prints the property of each of the objects
} )
````
* to return using forEach Loop
````js
  let codingarray=[]
  const myCoding = [
      {
          languageName: "javascript",
          languageFileName: "js"
      },
      {
          languageName: "java",
          languageFileName: "java"
      },
      {
          languageName: "python",
          languageFileName: "py"
      },
  ]
  
  myCoding.forEach( (item) => {
      codingarray.push(item.languageFileName)
  } )
  console.log(codingarray);
````
## Filters, Maps & Reduce
### Filters : 
* The filter() method of Array instances creates a shallow copy of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the provided function. 
* Returns the elements of an array that meet the condition specified in a callback function.
* The paremeters of a filter is items,index,array.
````js
const books = [
    { title: 'Book One', genre: 'Fiction', publish: 1981, edition: 2004 },
    { title: 'Book Two', genre: 'Non-Fiction', publish: 1992, edition: 2008 },
    { title: 'Book Three', genre: 'History', publish: 1999, edition: 2007 },
    { title: 'Book Four', genre: 'Non-Fiction', publish: 1989, edition: 2010 },
    { title: 'Book Five', genre: 'Science', publish: 2009, edition: 2014 },
    { title: 'Book Six', genre: 'Fiction', publish: 1987, edition: 2010 },
    { title: 'Book Seven', genre: 'History', publish: 1986, edition: 1996 },
    { title: 'Book Eight', genre: 'Science', publish: 2011, edition: 2016 },
    { title: 'Book Nine', genre: 'Non-Fiction', publish: 1981, edition: 1989 },
  ];

let mybooks= books.filter((keys)=>{
return keys.genre=='Fiction'
});
console.log(mybooks);
````
### Maps:
* The map() method of Array instances creates a new array populated with the results of calling a provided function on every element in the calling array.
* The parameters of a map is elements, index, array.
````js
const myNumers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const newNums = myNumers.map( (num) => { return num + 10})

// map chaining

const newNums = myNumers
                .map((num) => num * 10 )
                .map( (num) => num + 1)
                .filter( (num) => num >= 40)

console.log(newNums);
````
### Reduce: 
The reduce() method of Array instances executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.
````js
//for arrays
const myNums = [1, 2, 3]
const myTotal = myNums.reduce( (acc, curr) => acc+curr, 0)
console.log(myTotal);

// for Object arrays

const shoppingCart = [
    {
        itemName: "js course",
        price: 2999
    },
    {
        itemName: "py course",
        price: 999
    },
    {
        itemName: "mobile dev course",
        price: 5999
    },
    {
        itemName: "data science course",
        price: 12999
    },
]

const priceToPay = shoppingCart.reduce((acc, item) => acc + item.price, 0)
````
## DOM Manipulation
The DOM is one of the most-used APIs on the Web because it allows code running in a browser to access and interact with every node in the document. Nodes can be created, moved, and changed. Event listeners can be added to nodes and triggered on the occurrence of a given event.

* The hierarchy of children of DOM is Windows --> Document ---> Html ---> Head and Body etc.
* A tag can have attributes and text node for DOM diagram
**Different DOM Manipulation methods**
````js

// to select

document.getElementById('')
document.getElementsByName('')
document.getElementsByClassName('')

//to get attribute

document.getElementById('title').getAttribute('class')
document.getElementById('title').getAttribute('id')

// set attribute

document.getElementById('title').setAttribute('class', 'headingg')
const title = document.getElementById('title')
title.style.color='red' 
````
**Query Selector**

````js
document.querySelectorAll('.class')
document.querySelector('#id') 
document.querySelector('input[type="password"]')
document.querySelector('li:nth-child(3)') // to directly access any li item without converting it into a nodelist

let heading = document.querySelector('.heading').id //to get the id of the selector

const myul= document.querySelector('ul')
const myli =myul.querySelectorAll('li') //returns a node list of list items


// myul has different methods

myul.children //returns the nodelist of the children meaninng the li
myul.parent //returns the parent div if any
mypara.firstElementChild //returns the first element child
mypara.style //css property can be applied
myul.childNodes //returns a complex tree structure of the nodes

//styling

myli.style.color='red'

````
* .style can also be used to add styles to the selector
* Nodelist has forEach but html collection doesnt have forEach
* **Both can be converted into an array**
````js
const myli =myul.querySelectorAll('li') //returns a node list of list items
const myar = Array.from('myul')
````
* **Normal For loop iteration** is also possible in html collection and nodelist
````js
let htmlCollection = document.getElementsByClassName('example');
for (let i = 0; i < htmlCollection.length; i++) {
  console.log(htmlCollection[i].textContent);
}

let nodeList = document.querySelectorAll('.example');
for (let i = 0; i < nodeList.length; i++) {
  console.log(nodeList[i].textContent);
}
````
* Creating a new element using query selector
````js
const div = document.createElement('div')
console.log(div);
div.setAttribute('class','myclass')
div.style.color='yellow'
div.innerText='Chai aur code'
document.body.appendChild(div)
````
* Creating a new list item
````js
    function addlistitem(lii){
        const li = document.createElement('li')
        li.innerHTML = `${lii}`
        document.querySelector('#list_id').appendChild(li)
    }
    addlistitem('List3')
// This method to create is not the most optimized method as the DOM needs to traverse through the whole list in order to append child at the end. so for list containing many items it might cause a problem.

    function addlistitemOptimized(lii){
        const li = document.createElement('li')
        li.appendChild(document.createTextNode(lii))
        document.querySelector('#list_id').appendChild(li)
    }
    addlistitemOptimized('List4')
````
* Editing list items
````js
    function editlistitem(lii){
        const fourthli = document.querySelector('li:nth-child(3)')
        const newli =document.createElement('li')
        newli.textContent=lii
        fourthli.replaceWith(newli)
    }
    editlistitem('NewList')
````
* Remove list items
````js
        const lastli = document.querySelector('li:last-child')
        lastli.remove()
````
### Events
```js
document.querySelector('#id').addEventListener('click', function(){
//function definition
}, false)

document.querySelector('.class').addEventListener('keydown', function(){
},false)
```
Event Propogation and Event Capturing

* event propogation is basically event bubling basically from bottom tag to top tag so if there is a list of images and only one image has an owl. if we add event listeners to the list and the owl if the owl is clicked the owl event listener will work before then the list event listner (this happens when value is set to **false**)
* event capturing is from top to bottom and basically viceversa and happens when value is set to **true**)

```js
//Event Objects
document.querySelector('.class').addEventListener('keydown', function(e){
//e stands for event object
})

//preventDefault
document.querySelector('.class').addEventListener('keydown', function(e){
e.preventDefault();
})
```

