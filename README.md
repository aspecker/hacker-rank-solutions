# My Solutions to Coderbyte Problems

### Process a string using ASCII char codes
* change all letters to the next letter in the alphabet
* don't change non letter characters
* capitalize all vowels in final string
```
function LetterChanges(str) { 
    let strArr = [...str.toLowerCase()];
    let charArr = [];
    for (let i =0; i<strArr.length;i++){
        charArr.push(strArr[i].charCodeAt(0));
    }
    let shiftArr = charArr.map(char=>{
        if ((char>96 && char<122)){
             return char +1;
        }
        else if (char===122){
             return 97;
        }
        else if (char === 90){
            return 65;
        }
        else {
            return char;
        }
    });
    let capArr = shiftArr.map(char=>{
        if (char===97||char===101||char===105||char===111||char===117){
             return char -32;
        } 
        else{
            return char;
        }         
    });
    let returnArr = capArr.map(char=>String.fromCharCode(char));
    let string = returnArr.join('');
  return string;       
}
```

### Capitalize the first letter in every word
```
function LetterCapitalize(str) { 
    let strArr = [...str];
    let capArr = [];
    let capNext = false;
    for (let i=0;i<strArr.length;i++){
        if (i===0){
            capArr.push(strArr[i].toUpperCase())
        } else if (strArr[i]===' ' ){
            capArr.push(strArr[i]);
            capNext = true;
        } else if (capNext===true) {
            capArr.push(strArr[i].toUpperCase());
            capNext = false;
        } else {
            capArr.push(strArr[i]);
        }
    }
    let string = capArr.join('');
  return string;         
}
```
