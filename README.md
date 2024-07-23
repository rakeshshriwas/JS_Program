### JS_Program
1. Remove Duplicate Element From Array

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
