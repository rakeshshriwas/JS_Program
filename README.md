### JS_Program

##### 1. Remove Duplicate Element From Array

```javascript
const str = ['a', 'c', 'm', 'a', 'd', 'e', 'c'];

function removeDuplicate(arr){
    let result = [];
    for(let item of arr){
        if(result.indexOf(item) === -1){
            result.push(item)
        }
    }
    return result;
}

function removeDuplicateBySet(arr){
    let result = [...new Set(arr)];
    return result;
}

Output: [ 'a', 'c', 'm', 'd', 'e' ]
```

##### 2. Get Duplicate Element Position

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


##### 3. Check and add elemnt

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


##### 4. Check Armstrong Number of 3 digit

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

##### 5. Remove Specific Item From an Array

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

##### 6. Program to merge and remove duplicate value from an array

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

##### Check Prime Number
```javascript

let number = 6;
let isPrime = false;

function checkPrimeNumber(num){
    // check if number is equal to 1
    if(num === 1){
        console.log("1 is neither prime nor composite number.");
    }else if(num > 1){
        for(i = 2; i < num; i++){
            if(num % i === 0){
                isPrime = true;
            }
        }
    } else {
        console.log("The number is not a prime number.");
    }
}

checkPrimeNumber(number);

if(isPrime){
    console.log('Number is Prime Number');
}else{
    console.log('Number is not Prime Number');
}

Output: Number is Prime Number

```


##### Reverse a String  

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
