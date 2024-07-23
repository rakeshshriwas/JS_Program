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
```

##### 2. Get Duplicate Element POsition

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

console.log(checkValueExsit(str, '1'));
```


##### 4. Check Armstrong Number of 3 digit

```javascript
let sum = 0;
let checkNumber = 153;
let temp = checkNumber;
while(temp > 0){
    let reminder = temp % 10;
    sum += reminder * reminder * reminder;
    console.log(temp)
    temp = parseInt(temp/10);
}

console.log(sum === checkNumber ? 'Armstrong' : 'Not a Armstrong')
```
