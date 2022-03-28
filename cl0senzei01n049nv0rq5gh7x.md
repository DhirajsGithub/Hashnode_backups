## JavaScript key concepts


- ### Difference between Object and Map data structures, Sets


1.**Object Data Structure**

Objects --> reference type, mutable, don't have index, also called instances, having key value pairs
```
const person = {
    name: "Harshit",
    age: 22,
    hobbies: ["guitar", "sleeping", "music"]
}
// access object key values using dot method
console.log(person.name);
console.log(person.hobbies[1]);    //can apply array methods
// access object key values using square bracket method
console.log(person["name"])
// set key value pairs
person.gender = "male";
person["passing"] = 12;
console.log(person);
// NOTE: duplicate key can't exist in object hence if the key already exist and we are assigning new value to the key 
// then preference will be go to new value of the key, and the later will be added
```
difference between dot and bracket notation:
```
console.log(person["person hobbies"]);     // can have key with space seperated words
const key = "email";
// if we want email as key and borsedhiraj123@gmail.com as it's value in our object then
// this is also know as computed property
person[key] = "borsedhiraj123@gmail.com";    
// person.key = "borsedhiraj123@gmail.com";       //directly take key as key not as email
```

```
console.log(Object.keys(person));                   // will show array of keys
console.log(typeof (Object.keys(person)));           // object
const val = Array.isArray(Object.keys(person));      //typeof is boolean. 
console.log(val);                                    //  true

// for(let element of person){
//     console.log(element)
// }
//above code will show error as person is not itterable
for(let key of Object.keys(person)){
    console.log(key);
}
```
spread operator
```
newObject1 = {..."abcd"};
newObject2 = {...["item1", "item2"]};
const newObject = {...newObject1, ...newObject2, name : "Harshal"};    // {0: 'item1', 1: 'item2', 2: 'c', name: 'Harshal'}
console.log(newObject);
```
newObject1/2 are not specified with keys hence there indexing will be used as key 
the output don't have a, b as value coz lately index 0 and 1 as key are occupied by item1 and item2


2.**Map Data Structure**

```
const person = new Map();
//now add key value pairs in our map
person.set('firstName', 'harshit');        // firstName as key and harshit as value
person.set('age', 22);
person.set(1, 'one');
person.set([1,2,3], "array_key")
person.set({key: "value"}, 'object_key')
console.log(person);
``` 
```
//how to get any key value pair in map
console.log(person.get('age'));

for (let element of person.keys()){
    console.log(element, typeof element);
}
```
since maps are iterable therfore we can apply for of loop unlike objects
```
for(let key of person){
    console.log(Array.isArray(key));      // Array.isArray(parameter) method checks is parameter is array or not
}
```
shows all value given will be store in array, hence we can access them as we destructure array

```
for(let [key, value] of person){       
    console.log(key, value);
    // console.log(key);   to access all keys and vice versa for values
}
```
this can only be done with map funcition of person


we can also add key value pairs like this

```
const person11 = new Map([['firstName', 'harshit'], ['age', 22]]);
console.log(person11);
```
practical example of maping

```
const person2 = {
    id : 2,
    firstName : "shreya"
}
//we are maping object with object
const extraInfo2 = new Map();
extraInfo2.set(person2, {age: 18, gender: "female"});
console.log(extraInfo2.get(person2))       //to get the value in map by setting a key here it is person2
console.log(extraInfo2.get(person2).gender)
```


3.**Sets Data Structure**

sets (it is ITERABLE i.e. apn for of loop laga sakte hain sets pr)
No index based access
ordered is not guaranteed
unique items only (no duplicate allowed)
since sets are itterable therfore they can only be sotre as array or string

```
const numbers = new Set([1,2,3,4]);
const numbers2 = new Set([1,2,2,3,4]);
console.log(numbers);
console.log(numbers2);
//same outcome !
```


```
const firstName = new Set("harshal");
console.log(firstName);         //it will print out a strings as indexing elements and won't repeat charcters which are repeating

const items = ['item1', 'item2', 'item3'];
//adding elements in set:
const numbers = new Set();            //creating an empty set
numbers.add(1);
numbers.add(2);
numbers.add(2);
numbers.add(items);                    // this and the below one items are both same
numbers.add(items);  
numbers.add(['item3','item4'])         // this and below one have different address in heap memeory hence are unique
numbers.add(['item3', 'item4']) 
``` 

to find length of a set:
```
console.log(numbers.length)           // undefine
let length = 0;
for(let element of numbers){
    length ++;
}
console.log(length);
```



- ### Array, Object and nested destrcutruing
JavaScript has something different to destructre reference types.
Destructring won't affect the orginal array / object !

**. Array destrcutruing** 

```
const myArray = ["value1", "value2", "value3", "value4"];

let [myArray1, myArray2] = myArray;
console.log("value of myArra1 is ", myArray1);
console.log("value of myArra2 is ", myArray2);
``` 

if we want to assign value3 to myarray2 take no of commas as per index as shown below:

```
let [myArray1, , myArray2] = myArray;
console.log("value of myArra1 is ", myArray1);
console.log("value of myArra2 is ", myArray2);
``` 
If we assign any such value to a variable which is not in myArray it will show undefine

For defining rest of the items in an array:

```
let myNewArray = myArray.slice(2);
console.log(myNewArray);
//Or
// let [myArray1, myArray2,...myNewArray] = myArray;
// console.log(myNewArray);           //rest of the elements will be store in myNewArray
// console.log(myArray1);
``` 

**2. object destructruing**

```
const band = {
    bandName : "led zepplin",
    famousSong : "stairway to heaven",
    year : 1986,
    famousSong2 : "kashmir"
};
const {bandName, famousSong : lovedSong , ...restProps} = band;
console.log(bandName);
// console.log(famousSong);   // undefine now, coz we assign famourSong ans lovedSong
console.log(lovedSong)         // output stairway to heaven
console.log(restProps);       // output ({year: 1986, famousSong2: 'kashmir'})
console.log(band.famousSong);      // stairway to heaven
``` 
only need to specifiy the key it destructre it's value accordingly, no need of commos to access the further key value.



** 3. nested destructuring**
treating same as array destructuring then object destructring

```
const users = [
    {userID: 1, firstName: "Harshit", gender: "male"},
    {userID: 2, firstName: "Mohit", gender: "male"},
    {userID: 3, firstName: "Hemashri", gender: "female"}
];
const [{firstName}, user2, {gender: user3Gender}] = users;
console.log(firstName);        // Harshit
console.log(user3Gender);     // female
console.log(user2);           // output ({userID: 2, firstName: 'Mohit', gender: 'male'})

``` 


- ### Primitive vs Reference data types

primitive data types are String, Number, Null, boolean, undefine, etc

```
let num1 = 6;
let num2 = num1;
console.log("value of num1 is "+num1);    // output: 6
console.log("value of num2 is "+num2);    // output: 6
num1++;
console.log("after incrementing num1");          
console.log("value of num1 is ", num1);     // output: 7 
console.log("value of num2 is ", num2);     // output: 6
//1.primitive data types are store in stacks therfore each variable is store in different stack
//2.therfore updating value of any variable won't affect the value of other
//they are store like blocks one on the other
``` 

referece data types are array, functions, objects


```
let array1 = ["item1", "item2"];
let array2 = array1;                    
console.log("array1", array1);
console.log("array2", array2);
console.log(array===array4);         // true     --> array is not clone 
// array2 has the same address as that of array1 in the heap memory
array1.push("item3");
console.log("after pushing element to array1");
console.log("array1", array1);               // output: ["item1", "item2"]
console.log("array2", array2);              // output: ["item1", "item2"]

//since arrays elements are store in heap having a specific address
//we assign array2 = array1 hence both array are sotre in differnt block but there pointer have same address 
//hence if we push any element in array1 it will go to heap and hence array2 also have the same element caz of same address to heaps
``` 

- 
### Clone an array

```
let array = ["item1", "item2"];
//1.)
let array1 = ["item1", "item2"];   
console.log(array===array1);         // false   --> array is clone successfully
//Some language use such method, and also if array1 contains 100 elements then we are not supposed to type all 100 elements in array2. 

//2.)
let array2 = array.slice(0);       
//note: this is the fastest method to clone an array from another array 
//.slice(0) implies slice an array from 0th index to last, you can change to desired index as .slice(1, 3)or any applicable index

//3.)
let array3 = [].concat(array);

//4.) new way spread operator, mostly used 
let array4 = [...array];               
console.log(array===array4);         // false


array1.push("item3");
console.log(array1);
console.log(array2);


//now add other items in array2 including items in array1
let array2 = array1.slice(0).concat(["items3", "item4",array1]);
//Or
// let array2 = [].concat(array1, ["item3", "item4"]);
//Or 
// let array2 = [...array1, "item3", "item4"]
//Or
// let array2 = [...array1,"itemshit"].concat(["usefulitem"])

let array3 = ["G1", "G2", 2, 0];
// let array2 = [...array1, ...array3, "item4"]         //how we can clone two or more arrays in any array + adding elements
//Or
let array2 = [].concat(array1, array3, ["item5"]);

array1.push("item3");
console.log(array1);
console.log(array2);

``` 


- 
### Array methods

Which you use quite often, get rid of writing for loop make you code look simple and elegant using array methods.

```
console.log("---------forEach method-----------")
let s = [1,2,3,4]
// forEach()	Calls a function for each array element
// forEach() calls a function for each element in an array.
// forEach() is not executed for empty elements. And it won't return any value

s.forEach((element, index)=>{
    console.log(`element is ${element} index is ${index} shit a real shit!!`)
})


console.log("---------map method---------")
let s = [1,2,3,4]
// map()	Creates a new array with the result of calling a function for each array element

let squareIndex = s.map((e, i)=>{
    return `${e**e} index is ${i}`
})
console.log(squareIndex)


console.log("---------filter method---------")
// filter()	Creates a new array with every element in an array that pass a test (that passes the test imp hain )
// checks for boolean value only and return the element which satisfies the condition
const users = [
    {firstName: "Harshal", age: 18},
    {firstName: "Rohit", age: 19},
    {firstName: "Dhiraj", age: 20}
]

let adult = users.filter((e)=>{
    return e.age > 18;
})
console.log(adult)


console.log("---------reduce method---------")
//reduce()	Reduce the values of an array to a single value (going left-to-right)
const userCart = [
    {productId: 1, productName: "mobile", price: 15000},
    {productId: 2, productName: "Laptop", price: 40000},
    {productId: 3, productName: "TV", price: 35000}
]
// takes two parameter as accumulator(totalAmounr here) and currentValue(currentProduct here)
// value of accumulator is set to 0 or by default it is 0th index value as it's updated as currentValue of previous value of accumulaor
// currentvalue is the succedding value to accumulator 
const amount = userCart.reduce((totalAmount, currentProduct)=>{
    return totalAmount + currentProduct.price;
}, 0)
console.log(amount)


console.log("---------sort method---------")
// The sort() sorts the elements of an array. The sort() overwrites the original array.
const products = [
    {productID: 1, productName: 'p1', price: 300},
    {productID: 2, productName: 'p2', price: 400},
    {productID: 3, productName: 'p3', price: 3000},
    {productID: 4, productName: 'p4', price: 200},
]
console.log("sort according to ascii values but we will play a trick over here")
const lowToHigh = [].concat(products).sort((a, b)=>{
    return a.price - b.price;
})
console.log(lowToHigh);
console.log(products)
// can reverse the order by returning as return b.price-a.price


console.log("---------find method---------")
//find()	Returns the value of the FIRST element in an array that pass a test
const usersID = [
    {userID: 1, userName: "harshal"},
    {userID: 2, userName: "dhiraj"},
    {userID: 3, userName: "rohit"},
    {userID: 4, userName: "gayatri"}
]
//make a function which finds the user which havinf id 4 (that's the wanted user)
const myUser = usersID.find((user)=>{
    return user.userID ===4;
});
console.log(myUser);


console.log("---------every method---------")
// every()	Checks if every element in an array pass a test
//callback function returns true/false (boolean)
const userCart2 = [
    {productId: 1, productName: "mobile", price: 15000},
    {productId: 2, productName: "Laptop", price: 40000},
    {productId: 3, productName: "TV", price: 35000}
]
const check = userCart2.every((checkPrice)=>checkPrice.price < 30000

);
console.log(check);


console.log("---------some method---------")
const userCart2 = [
    {productId: 1, productName: "mobile", price: 15000},
    {productId: 2, productName: "Laptop", price: 40000},
    {productId: 3, productName: "TV", price: 35000}
]
//some method ()
//some()	Checks if any of the elements in an array pass a test
const check2 = userCart2.some((check)=>{
    return check.price < 35000;
})
console.log(check2)


console.log("---------splice method---------")
//splice method:
//splice()	Adds/Removes elements from an array
//it takes: .splice(start, delete, insert)
//consider as (where to start(indexing no.), how many elements to delete, what to insert)
// no of deleted and inserted items can by anything

const myArray3 = ['item1', 'item2', 'item3'];
const deletedItem = myArray3.splice(0, 2, 'inserted item1', 'inseted item2','inserted item 3');
console.log('deleted items ', deletedItem);
console.log(myArray3);               
// doesn't matter how many you insert it will insert all items


console.log("---------fill method---------")
// fill() Fill the elements in an array with a static value
//it takes: fill(valueToBeFilled, startIndice, endIndice)  
// new Array creates a new array without having [] bracket
const myArray = new Array(10).fill(0);       // 0 to be filled start is 0th and end is last index
console.log(myArray);
const myArray2 = [1,2,3,4,5,6,7,8];
myArray2.fill(0,2,5)
console.log(myArray2);

``` 

![1636362778121.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1647800910941/Aj4QbGPj5.jpg)


- ### 'This' keyword

 1. this represents the object that is executing the current function 
 2. function part of object --> method then this in function is the object itself
 3. normal function ---> then this is the global object (window, node)

```
const video = {
  titile : "a",
  play(){
    console.log(this);         // object itself here video. from point_2
  }
}
video.stop = function(){           // creating method of object video 
  console.log(this);
}
video.stop();    // ({titile: 'a', play: ƒ, stop: ƒ}). from point_2
``` 

```
function playVideo(){
  console.log(this)     
}
 playVideo();       // from point_3 window object
``` 

```
function VideoAnd(title){
  this.title = title;
  console.log(this)
}
VideoAnd();     // Window ({window: Window, self: Window, document: document, name: '', location: Location, …})
const v = new VideoAnd("b")   // VideoAnd {title: 'b'}
``` 



new keyword creates a empty object that a function provides to us and it points towards new object rather than window object


**1. dealing with function decleration**

```
const video = {
  titile : "a",
  tags : ["d", "b", "c"],
  play(){
    console.log(this);
  },
  showTags(){
    console.log(this.titile)             // note the difference b/w line 98 and 100
    this.tags.forEach(function(tag){     // in showTag metthod we can access tags as well title 
      console.log(this.titile, tag)      // here this.titile won't refer to "a" coz we are inside the callback function which is a normal function. from point_3
    })                                   // we are able to access tag iems coz we pass it as parameter in showTag iteself
  },

  showTags1(){
    console.log(this.titile)             
    this.tags.forEach(function(tag){     
      console.log(this.titile, tag)      
    }, this)   
    // here this.title is not undefine as forEach accept to parameter first function and second the scope (here 'this' implies object of our method)                                
  }

}
video.showTags(); 
video.showTags1();
``` 

**2. dealing with function expression**

```
const video = {
  titile : "a",
  tags : ["d", "b", "c"],
  play(){
    console.log(this);
  },
  arrowFunc : ()=>{
    console.log(this)
  },
  showTags(){
    console.log(this.titile)          
    this.tags.forEach((tag)=>{
      console.log(this)                  //  it's arrow functiona
      console.log(this.titile, tag)
    })                                 //  arrow function takes 'this' of the object itself even if the function is normal
  }                                     // arrow function retains the 'this' value of the enclosing lexical context
}
video.arrowFunc();          // Window ({window: Window, self: Window, document: document, name: '', location: Location, …})
video.showTags();   
``` 

1. note the difference b/w 'this' in arrowFunc and in showTags function
2. since arrowFunc is arrow function 'this' will come from lexical scope which is window object
3. for arrow function in showTags it's lexical scope is the object video itself
4. normal function takes 'this' from the object they are define in

```
const eating = ()=>{
  return this
}
console.log(eating());      // window object 
``` 


- ### Call, Apply and Bind method

```
function hello (){
    console.log("hellow world");
}
hello();
hello.call();       //same

``` 

1.**Call method**

```
function about (hobby, favMusician){
    console.log(`user name ${this.firstName} age is ${this.age}, hobby: ${hobby}, favMusicician: ${favMusician}`)
}

const user1 = {
    firstName : "harshit",
    age : 8
}
const user2 = {
    firstName : "mohit",
    age : 18,
    userInfo : about
}
// without defining the key value pair in object we can call the function with call/bind/apply method
about.call(user1,"guitar", "moazart");
user2.about("playing", "arigit");
``` 
2.**Apply method**

```
// takes function arguments in array
about.apply(user2,["guitar", "arijit"])
``` 
3.**Bind method**

```
//bind :   bind will return functioon therfore store that function in func variable and call it.
const func = about.bind(user1,"sleeping", "lata-ji");
func();
```










That's it for now, I will be keep updating this post with new exciting content so make sure you sign in the **Newsletter** 
.....


