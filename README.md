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

### 11 Reverse a number
```javascript
function reverseNumber(num){
    let reverseNum = 0;
    
    while(num > 0){
        let lastNumber = num % 10;
        reverseNum = reverseNum * 10 + lastNumber;
        num = parseInt(num/10);
    }
    
    return reverseNum;
}

console.log(reverseNumber(12345));
Output: 54321
```

