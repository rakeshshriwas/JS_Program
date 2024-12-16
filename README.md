### JS_Program

### 1. Remove Duplicate Element From Array

```javascript
const fruits = [ 'Apple', 'Banana', 'Mango', 'Apple', 'Banan'];

function methodOne(arr){
    let result = [];
    for(let fr of arr){
        if(result.indexOf(fr) === -1){
            result.push(fr)
        }
    }
    return result;
}

console.log('Method One ::', methodOne(fruits));

function methodTwo(arr){
    return [...new Set(arr)];
}

console.log('Method Two ::', methodTwo(fruits));

function methodThird(arr){
    let result = [];
    arr.forEach((name, index) => {
       if(!result.includes(name)){
           result.push(name);
       } 
    });
    
    return result;
}

console.log('Method Third ::', methodThird(fruits));

function methodFour(arr){
    return  arr.reduce((acc, curr) => {
        return acc.includes(curr) ? acc : [...acc, curr]
    },[]);
}

console.log('Method Four ::', methodFour(fruits));

function methodFive(arr){
    return arr.filter((name, index) => arr.indexOf(name) === index);
}

console.log('Method Five ::', methodFive(fruits));

Output:
Method One :: [ 'Apple', 'Banana', 'Mango', 'Banan' ]
Method Two :: [ 'Apple', 'Banana', 'Mango', 'Banan' ]
Method Third :: [ 'Apple', 'Banana', 'Mango', 'Banan' ]
Method Four :: [ 'Apple', 'Banana', 'Mango', 'Banan' ]
Method Five :: [ 'Apple', 'Banana', 'Mango', 'Banan' ]
```

### 2. Get Duplicate Element Position

```javascript
const str = ['a', 'c', 'm', 'a', 'd', 'e', 'c'];

function dublicateStringPosition(arr, ele){
    let result = [];
    currentIndex = arr.indexOf(ele);
    
    while(currentIndex != -1){
        result.push(currentIndex);
        currentIndex = arr.indexOf(ele, currentIndex + 1);
    }
    return result;
}

console.log(dublicateStringPosition(str, 'c'));

Output: [ 1, 6 ]
```


### 3. Check and add elemnt

```javascript
function checkValueExsit(arr, ele){
    
    if(arr.indexOf(ele) === -1){
        arr.push(ele)
        console.log('Ele Added', arr)
    }else{
        console.log('Dublicate')
    }
}

checkValueExsit(str, '1');

Output: Element Added ['a', 'c', 'm','a', 'd', 'e','c', '1']
```


### 4. Check Armstrong Number of 3 digit
###### Armstrong number is a number that is equal to the sum of cubes of its digits

```javascript
let sum = 0;
let checkNumber = 153;
let temp = checkNumber;
while(temp > 0){
    // finding the one's digit
    let reminder = temp % 10;
    sum += reminder * reminder * reminder;
    // removing last digit from the number
    temp = parseInt(temp/10);
}

console.log(sum === checkNumber ? 'Armstrong' : 'Not a Armstrong')

Output: Armstrong
```

### 5. Remove Specific Item From an Array

```javascript
const str = ['a', 'c', 'm', 'a', 'd', 'e', 'c'];

function removeSpecificItemFromArrayOne(arr, item){
    let result = [];
    
    arr.forEach((value, index) => {
        if(value !== item){
            result.push(value)
        }
    })
    return result;
}

function removeSpecificItemFromArrayTwo(arr, item){
    let currentIndex = arr.indexOf(item);
    
    if(currentIndex > -1) {
        arr.splice(currentIndex, 1)
    }
    return arr;
}


console.log('One', removeSpecificItemFromArrayOne(str, 'e'));
console.log('Two', removeSpecificItemFromArrayTwo(str, 'd'));

Output:

One [ 'a', 'c', 'm', 'a', 'd', 'c' ]
Two [ 'a', 'c', 'm', 'a', 'e', 'c' ]
```

### 6. Program to merge and remove duplicate value from an array

##### Method 1 [Using Spread Syntax and Set]
```javascript
function removeDuplicateAfterMerge(firstArr, secondArr){
    const mergedArr = [...firstArr, ...secondArr];
    let result = [...new Set(mergedArr)];
    return result;
}

const array1 = [1, 2, 3];
const array2 = [2, 3, 5];

console.log(removeDuplicateAfterMerge(array1, array2))
console.log(removeDuplicateAfterMerge(array1, array2));

Output: [ 1, 2, 3, 5 ]

```

##### Method 2 [Using concat() and for Loop]
```javascript
function removeDuplicateAfterMerge(firstArr, secondArr){
    // merge two arrays
    const mergeArray = firstArr.concat(secondArr);
    let result = [];
    
    for(let item of mergeArray){
        if(result.indexOf(item) === -1){
            result.push(item);
        }
    }
    return result;
}

console.log(removeDuplicateAfterMerge(array1, array2));

Output: [ 1, 2, 3, 5 ]

```

### 7. Check Prime Number
###### A prime number is a whole number greater than 1 whose only factors are 1 and itself. The first ten primes are 2, 3, 5, 7, 11, 13, 17, 19, 23, 29. It should be
```javascript

let number = 6;
let isPrime = true;

// check if number is equal to 1
if (number === 1) {
    console.log("1 is neither prime nor composite number.");
}

// check if number is greater than 1
else if (number > 1) {

    // looping through 2 to number-1
    for (let i = 2; i < number; i++) {
        if (number % i == 0) {
            isPrime = false;
            break;
        }
    }

    if (isPrime) {
        console.log(`${number} is a prime number`);
    } else {
        console.log(`${number} is a not prime number`);
    }
}

// check if number is less than 1
else {
    console.log("The number is not a prime number.");
}

Output: 6 is a not prime number
```


### 8. Reverse a String  

##### Method 01 [Using for Loop] 

```javascript

function reverseString(str){
    let reverseStringResult = '';
    for(i = str.length - 1; i >= 0; i-- ){
        reverseStringResult += str[i]
    }
    return reverseStringResult;
}

console.log('Reverse a String Using for Loop:', reverseString('Hello'));

Output: Reverse a String Using for Loop: olleH

```

##### Method 02 [Using built-in Methods]

```javascript
function reverseUsingBuiltInFunction(str){
    
    // return a new array of strings
    let arrayString = str.split('');
    // reverse the new created array elements
    let reverseString = arrayString.reverse();
    // join all elements of the array into a string
    let resultStr = reverseString.join('')
    
    return resultStr;
}

console.log('Reverse a String Using built-in Methods:', reverseUsingBuiltInFunction('HelloIndore'));
console.log('Reverse a String each word Using built-in Methods:', reverseUsingBuiltInFunction('Hello Im Rakesh Shriwas From Indore '));

Output:
Reverse a String Using built-in Methods: erodnIolleH
Reverse a String each word Using built-in Methods: erodnI morF sawirhS hsekaR mI olleH

```
### 9. Find Factorial
###### The factorial of a number is the multiplication of all the numbers between 1 and the number itself.

#### Method 1 [Using Loop]

```javascript
function factorial(number){
    // checking if number is negative
    if (number < 0) {
        console.log('Error! Factorial for negative number does not exist.');
    }
    // if number is 0
    else if (number === 0) {
        console.log(`The factorial of ${number} is 1.`);
    }
    // if number is positive
    else {
        let fact = 1;
        for (i = 1; i <= number; i++) {
            fact *= i;
        }
        console.log(`The factorial of ${number} is ${fact}.`);
    }
}

factorial(5);
Output: The factorial of 5 is 120.
```

#### Method 2 [Using Recursion]

```javascript
let number = 5;

function factRecursion(num){
    if(num === 0){
        return 1;
    } else {
        return num * factRecursion(num - 1);
    }
}

if (number >= 0) {
    console.log(`The factorial of ${number} using recursion is`, factRecursion(number));
}
else {
    console.log('Enter a positive number.');
}

Output: The factorial one of 5 is 120
```

```javascript
// custom sorting an array of strings
var names = ["Adam", "Jeffrey", "Fabiano", "Danil", "Ben"];

function len_compare(a, b){
    return a.length - b.length;
}

// sort according to string length
names.sort(len_compare);

console.log(names);
```


### 9. Deep Copy Custom Funcation

```javascript
const object = {
  id: 1,
  name: "Leanne Graham",
  username: "Bret",
  email: "Sincere@april.biz",
  address: {
    street: "Kulas Light",
    suite: "Apt. 556",
    city: "Gwenborough",
    zipcode: "92998-3874",
    geo: {
      lat: "-37.3159",
      lng: "81.1496"
    }
  },
  phone: "1-770-736-8031 x56442",
  website: "hildegard.org",
  company: {
    name: "Romaguera-Crona",
    catchPhrase: "Multi-layered client-server neural-net",
    bs: "harness real-time e-markets"
  }
}

function deepCopy(obj) {
    
    if(typeof obj !== 'object' || obj === null){
        return obj;
    }
    
    const copiedVal = Array.isArray(obj) ? [] : {};
    const keys = Object.keys(obj);
    
    for(let i = 0; i < keys.length; i ++){
        copiedVal[keys[i]] = deepCopy(obj[keys[i]])
    }
    return copiedVal
}


const result = deepCopy(object);
result.address.geo.lat = '192.168.1.1'
console.log('object', object);
console.log('result', result);

```

### 10. Reverse each word in a sentance
```javascript
const str = "Jai Shree Ram Bhaiyo Kaise Hai Aap Log";

result = str.split(" ").map((item) => {
    return item.split("").reverse().join("");
});

console.log('Result:', result.join());

Output: Result: iaJ,eerhS,maR,oyiahB,esiaK,iaH,paA,goL

```

### 11. Reverse a number
```javascript
function reverseNumber(num){
    let reverseNum = 0;
    
    while(num > 0){
        // finding the one's digit
        let lastNumber = num % 10;
        reverseNum = reverseNum * 10 + lastNumber;
        // removing last digit from the number
        num = parseInt(num/10);
    }
    
    return reverseNum;
}
// Second Method
function reverseNumber(number){
    return number.toString().split("").reverse().join('');
}

console.log(reverseNumber(12345));
Output: 54321
```

### 12. String is Palindrome or Not

#### Method 1 [Create a custom logic]
```javascript

function checkPalindrome(string) {

    // find the length of a string
    const len = string.length;

    // loop through half of the string
    for (let i = 0; i < len / 2; i++) {
        // check if first and last string are same
        if (string[i] !== string[len - 1 - i]) {
            return 'It is not a palindrome';
        }
    }
    return 'It is a palindrome';
}

// call the function
console.log(checkPalindrome('madam'));

Output: It is a palindrome
```

#### Method 2 [Builtin Function]

```javascript

function checkPalindrome(string) {
    
    let tempString = string.split('').reverse().join('');
    
    if(string === tempString){
        console.log('It is a palindrome');
    }else{
        console.log('It is not a palindrome');
    }
}

// call the function
checkPalindrome('madam')

Output: It is a palindrome
```


### 13. Sort Words in Alphabetical Order
```javascript

function sortWordInAlphOrder(word){
    return word.split('').sort().join('');
}

console.log('Sorted Word : ', sortWordInAlphOrder('apple'));

Output: Sorted Word :  aelpp
```

### 14. Capitalize string every word first letter capitalize
```javascript

function Capitalize(str){
    return str.split(" ").map((word) => word.charAt(0).toUpperCase() + word.substring(1)).join(" ");
}

console.log(Capitalize('hello indore'))

Output: Hello Indore
```

### 15. Find the number of occurrences in each letter of a string

```javascript
function getOccurance(str){
    let obj = {};
    str.split('').forEach((char) => {
        if(!obj.hasOwnProperty(char)){
            obj[char] = 1;
        }else {
            obj[char]++;
        }
    });
    
    return obj;
}

console.log('Occurance', getOccurance('madam'));

Output: Occurance { m: 2, a: 2, d: 1 }

```

### 16. Find the second largest number in an unsorted array without any built-in method in JavaScript

```javascript
let array = [10, 30, 35, 20, 30, 25, 90, 89];

function secondLargestNumber(array) {
    let max = 0;
    let secondMax = 0;

    for (let i = 0; i < array.length; i++) {
        if (array[i] > max) {
            max = array[i];
        }
    }

    for (let i = 0; i < array.length; i++) {
        if (array[i] > secondMax && array[i] !== max) {
            secondMax = array[i];
        }
    }
    return secondMax;
}
console.log(secondLargestNumber(array));

```

### 17. Compaire two object

```javascript
function compareObj(obj1, obj2) {
    const keys1 = Object.keys(obj1);
    const keys2 = Object.keys(obj2);
    
    if(keys1.length !== keys2.length) return false;
    
    for(let key of keys1) {
        if(obj1[key] !== obj2[key]) return false;
    }
    
    return true
}



const obj1 = {name: 'Ramesh', age: 20};
const obj2 = {name: 'Ramesh', age: 40}

 console.log(compareObj(obj1, obj2));
    }

    for (let i = 0; i < array.length; i++) {
        if (array[i] > secondMax && array[i] !== max) {
            secondMax = array[i];
        }
    }
    return secondMax;
}
console.log(secondLargestNumber(array));

```

### 18. Modify Obj

```javascript
const endorsements = [
  { skill: 'javascript', user: 'Chad' },
  { skill: 'javascript', user: 'Bill' },
  { skill: 'javascript', user: 'Sue' },
  { skill: 'html', user: 'Sue HTML' },
  { skill: 'css', user: 'Sue CSS' },
  { skill: 'css', user: 'Bill CSS' }
];

// Transform endorsements to desired output
const resultData = Object.values(
  endorsements.reduce((acc, { skill, user }) => {
      console.log(acc[skill]);
    if (!acc[skill]) {
      acc[skill] = { skill, user: [], count: 0 };
    }
    acc[skill].user.push(user);
    acc[skill].count++;
    return acc;
  }, {})
);

console.log(resultData);

Output:
[
  { skill: 'javascript', user: [ 'Chad', 'Bill', 'Sue' ], count: 3 },
  { skill: 'html', user: [ 'Sue HTML' ], count: 1 },
  { skill: 'css', user: [ 'Sue CSS', 'Bill CSS' ], count: 2 }
]

```

### 19. Compaire two obj and find dublicate

```javascript
let a = [1,2,3,4,5,6,7,8];
let b = [4,5,6,7];
let result = [];
b.forEach((item) => {
    if(a.includes(item)){
        result.push(item)
    }
});

console.log(result)

Output: [ 4, 5, 6, 7 ]

```
###. Problems 1

```javascript
// Problem 
var obj = { num: 3 };

var sum = function(a,b,c) {
     return this.num+a+b+c;
}
console.log(sum(1,2,3))

// Soluation 1
var obj = { num: 3 };

var sum = function(a, b, c) {
    return this.num + a + b + c;
};

// The call method allows you to explicitly specify what this refers to when calling the function.
console.log(sum.call(obj, 1, 2, 3)); // Output: 9

// The apply method is similar to call, but it takes an array of arguments instead of individual arguments.
console.log(sum.apply(obj, [1, 2, 3])); // Output: 9

var boundSum = sum.bind(obj);
console.log(boundSum(1, 2, 3)); // Output: 9

// Soluation 2

const countMap = new Map();
array.forEach(item => {
    countMap.set(item, (countMap.get(item) || 0) + 1);
});
console.log(countMap)
// Filter only the elements that appear more than once
const duplicates = [...countMap.entries()]
    .filter(([key, value]) => value > 1)
    .map(([key]) => key);

console.log(duplicates); // Output: [6, 2]

```


