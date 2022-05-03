# mvz-corecode1
MarvoIke's CoreCode bootcamp Software desde cero repository 


### Week-1 challenge #1

Compiled vs Interpreted:  
Programming languages help to communicate humans with computers, which speaks very different languages that's why we need a translating process and the translation can be done all at once (which is the case for the compiled langages) or can be done on the fly "step by step" (which will be the case for the interpreted languages) thus we can communicate with computers and have different paradigms to "translate" our communications.

Java programming language is a hybrid between compiled and interpreted, the whole Java infrastructure designed by Sun Microsystems, takes the best of both worlds.

```
Start
variable inputAmount = 0
variable outputAmount = 0
variable usdToBtcExchange = 0
from API get usdToBtcExchange
print "usd: " + "$"
get inputAmount
outputAmount = inputAmount * usdToBtcExchange
print inputAmount + "usd equals to: " + outputAmount + "btc"
End
```

### Week-1 challenge #2

My date of birth is 22/04/02 in DD/MM/YY format that means i have to convert this triad {22,4,2002} of base 10 numbers to base 2 numbers.
I would follow the next algorithm:
```
START 
1 define the 'x' number to convert.
2 define an array 'almostAnswer' with a 'n' number of empty spaces.
3 if x/2 is an integer, then write a '0' in the current space of the array, else write a '1'.
4 define 'c' as x/2, if c > -1, then go to line #3 with x = c, else continue.
5 define 'answer' as reversed almostAnswer.
6 return answer.
FINISH
```
And follow the algorithm for every number of my date of birth.

MIPS excercise:
```
  .data
        number1: .asciiz "\nIngrese el primer numero: "
	      number2: .asciiz "\nIngrese el segundo numero: "
	      result_message: .asciiz "\nEl resultado es: "
	      last_br: .asciiz "\n"
	
  .text
        main:
              li $v0, 4
              la $a0, number1
              syscall
              
              li $v0, 5
              syscall
              
              move $t0,$v0
              
              li $v0, 4
              la $a0, number2
              syscall
              
              li $v0, 5
              syscall
              
              move $t1,$v0
              
              add $t2,$t0,$t1
              
              li $v0, 4
              la $a0 result_message
              syscall

              li $v0, 1
              move $a0, $t2
              syscall
              
              li $v0, 4
              la $a0, last_br
              syscall       
```

### Week-1 challenge #3

Print special numbers:
```
for (let i = 0; i <= 100; i++){
    if (i%2 == 0)
        console.log(i);
}
```
Bad code 1:
```
var cond = false;

if ((cond = true)) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```
The error within this code is in the if condition, "(cond = true)" this code does not make sense as an if condition, be cause it does not evaluate a boolean expression, it is an assignment with "=" operator, instead of being "==" or "===" both of which produce a boolean value product of the comparison, this code will always execute the if statement within be cause the condition will always be true.

I would fix it this way:
```
var cond = false;

if (cond) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```

Bad code 2:
```
var n = 100;

if (n == 100) {
  console.log('This is a special number!');
}
else if ((n < 1000) && (n % 10 == 0)) {
  console.log('This number is almost special');
} else {
  console.log('Just a regular number');
}
```
### Week-2 Katas
```
1-1
function multiply(a, b){
  return a * b;
}

1-2
function uniTotal(s) {
  let total = 0;
  for (let i = 0; i < s.length; i++) {
    total += s.charCodeAt(i);
  }
  return total;
}

1-3
function getChar(c){
  return String.fromCharCode(c);
}

1-4
function decToBin(n) {
  let answer = "";
  let biNum = new Array(32);
  let i = 0;

  while (n > 0) {
    biNum[i] = n % 2;
    n = Math.floor(n / 2);
    i++
  }

  for (let j = i - 1; j >= 0; j--) {
    answer = answer + biNum[j].toString();
  }

  return answer;
}

function addBinary(a,b) {
  return decToBin(a + b);
}

1-5
function finalGrade (exam, projects) {
  if(exam > 90 || projects > 10)
    return 100;

  if(exam > 75 && projects >= 5)
    return 90;

  if(exam > 50 && projects >= 2)
    return 75;

  return 0;
}

2-1
function dutyFree(normPrice, discount, hol){
  return Math.floor(hol/((normPrice/100)*discount));
}

2-2
function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs(dadYearsOld - (sonYearsOld * 2));
}

2-3
function validSpacing(s) {
  if(s[0] == " " || s[s.length-1] == " ")
    return false;

  let spaces = 0;
  let spaIndexes = [];
  for(let i = 0; i < s.length; i++) {
    if(s[i] == " "){
      spaces++;
      spaIndexes.push(i);
    }
  }

  if(spaces <= 1)
    return true;

  for(let i = 0; i < spaIndexes.length; i++) {
    if(Math.abs(spaIndexes[i] - spaIndexes[i+1]) == 1)
      return false;
  }

  return true;
}

2-4
function fakeBin(x){
  let answer = ""
  for(let i = 0; i < x.length; i++) {
    if(x[i] < 5)
      answer = answer + "0";
    else
      answer = answer + "1";
  }
  return answer;
}

3-1
function remove(myString) {
  if (myString[myString.length - 1] == "!")
    return remove(myString.slice(0, -1));
  else
    return myString;
}

3-2
function shortcut(string) {
  let result = string;
  for(let i = 0; i < string.length; i++) {
    if (string[i] == "a" ||
        string[i] == "e" ||
        string[i] == "i" ||
        string[i] == "o" ||
        string[i] == "u")
      result = result.replace(string[i], "");
  }
    return result;
}

3-3
const rps = (p1, p2) => {

  if(p1.length == p2.length)
    return "Draw!";

  if(p1.length != 5 && p2.length != 5)
  {
    if(p1.length == 4)
      return "Player 1 won!";
    else
      return "Player 2 won!";
  }
  else if(p1.length > p2.length)
  {
    return "Player 1 won!";
  }
  return "Player 2 won!";
};

3-4
function persistence(num) {

  if(num <= 9)
    return 0;

  let flag = true;
  let saveMult = 1;
  let counter = 0;
  let numStr = num.toString();

  do {
    for (let i = 0; i < numStr.length; i++) {
      saveMult *= numStr[i];
    }
    numStr = saveMult.toString();
    saveMult = 1;
    counter++;
    if (numStr.length < 2)
      flag = false;

  } while (flag);

  return counter;
}
```
