Download Link: https://assignmentchef.com/product/solved-ee306-program1-multiply-two-signed-numbers-given-in-memory
<br>
The purpose of this assignment is to write a program in LC-3 assembly language to multiply two signed numbers given in memory and put the result back in memory.

<h1>Details</h1>

The two signed numbers are given to you in memory locations x2FF0 and x2FF1. You may assume that the numbers are in the range -128 to +127. This means you do not have to worry about overflow. Your program should multiply these two signed numbers and store the result in memory location x2FF2. Note: Signed numbers can be positive or negative.

You can start with the code given to you through Canvas(called ​<strong>Program1.asm</strong>​) and incrementally change it as follows:

<ul>

 <li><u>Increment 1</u>​: Modify it so the two numbers are not from x3007 and a constant with the result just left in a register but, instead the input numbers are loaded from x2FF0 and x2FF1 and the result is stored to x2FF2.</li>

 <li><u>Increment 2</u>:​ Modify the code from Increment 1 so now you consider the numbers to be signed rather than unsigned.

  <ul>

   <li>If you think of the numbers as <em>Num1 </em>​ ​and <em>Num2 </em>​ ​then your goal is to add <em>Num1+Num1+</em>​ … ​<em>Num2</em>​ Start with ​<em>Num2 </em>​in some register and as you add ​<em>Num1 </em>​to some accumulating register repeatedly, keep decrementing the register holding ​<em>Num2 </em>​until it reaches zero.</li>

   <li>Note that as long as <em>Num2 </em>​ ​is positive, it does not matter if ​<em>Num1 </em>​is positive or negative the code you wrote in Increment 1 still works. Convince yourself that this is case by testing the program for different values of ​<em>Num1 </em>​(positive or negative) but keeping <em>Num2 </em>​as a positive number. Set a breakpoint at the HALT statement and check to see what the contents of x2FF2 are after you run the program.</li>

   <li>Now, you have to modify your code to account for the possibility that ​<em>Num2 </em>​may be negative. Here are some hints:</li>

  </ul></li>

</ul>

&#x25aa; To see if a register has a negative number just add zero to the register, this will set the N bit to 1 if the register had a negative number, which you can check for. Alternatively, if you want to see if a register has a zero or positive number you do the same, except the addition will set the Z or P bit to 1 if the register had a zero value or a non-zero positive number respectively.

&#x25aa; See if the decrement step can be changed to do increment or decrement based on whether Num2 is negative or positive respectively.  Make sure you apply a fix to the result accordingly.

Examples: These are just examples the two numbers at x2FF0 (​<em>Num1</em>​) and x2FF1(​<em>Num2</em>​) can be any two signed numbers.

<ul>

 <li>If the memory locations ​<em>Num1</em>​, <em>Num2 </em>​ ​are the numbers 45 and 4 respectively your program should multiply 45 and 4 and store the result 180 in memory location x2FF2. In terms of your code the calculation performed is R = 45+45+45+45 = 180.</li>

 <li>If the memory locations ​<em>Num1</em>​, <em>Num2 </em>​ ​are the numbers -5 and 200 respectively your program should multiply -5 and 200 and store the result -1000 in memory location x2FF2. In terms of your code the calculation performed is R = (-5)+(-5)+(-5)+(-5)… 200 times = -1000.</li>

 <li>If the memory locations ​<em>Num1</em>​, <em>Num2 </em>​ ​are the numbers 50 and -4 respectively your program should multiply 50 and -4 and store the result -200 in memory location x2FF2. In terms of your code the logic performed is: ​<em>Num2 </em>​is negative, so perform R = 50+50+50+50=200. Now fix it: -200.</li>

 <li>If the memory locations ​<em>Num1</em>​, <em>Num2 </em>​ ​are the numbers -10 and -20 respectively your program should multiply -10 and -20 and store the result 200 in memory location x2FF2. In terms of your code the logic performed is: ​<em>Num2 </em>​is negative, so perform R = (-10)+(-10)+(-10)+(-10)… 20 times = -200. Now fix it: +200.</li>

</ul>