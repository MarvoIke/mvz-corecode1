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
