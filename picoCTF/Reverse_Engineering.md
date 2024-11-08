# ARMssembly 1
I was asked to do a challenge related to *Reverse Engineering*. But since this is a new domain for me, I didn't know how to start, so I visited the videos provided by my mentor regarding the domain.
	Then, I downloaded and disassembled the file provided in the challenge, i.e, *chall_1.S* and I went through the lines. Initially I noticed it was a 64 bit file, but since the answer was asked in 32 bit, I knew it should be of that form. Then I, went through the lines inside the function. From that, initlial I noticed that certain values were loaded inside a registar using `str` in certain memory locations.
```
str	w0, [sp, 12]
mov	w0, 58
str	w0, [sp, 16]
mov	w0, 2
str	w0, [sp, 20]
mov	w0, 3
str	w0, [sp, 24]
```
So in this, the parameter is stored in *(sp+12)* whose hexadecimal will give us the flag. Similarly, 58 was stored in `*(sp+16)` , 2 in `*(sp+20)` and 3 in `*(sp+24)` respectively.

Then, I observed the next lines.
```
ldr	w0, [sp, 20]
ldr	w1, [sp, 16]
lsl	w0, w1, w0
```
From this, I knew we were supposed to load to registrars the values as given: `wo=*(sp+20)=2` and `w1=*(sp+16)=58` respectively. Then the given line contains *lsl* which basically means we should shift to left the 2nd argument in the line by no of digits given as value in 3rd argument and store the the coming value as wo. So, I what I had here basically was `wo=58<<2`. So I did it in binary, 58 is *111010* which shifted two times to left gives *11101000* which is the no 232. So, now I have wo=232.
Then, I observed the next lines.
```
str	w0, [sp, 28]
ldr	w1, [sp, 28]
ldr	w0, [sp, 24]
sdiv	w0, w1, w0
```
Load the registrar as `wo=*(sp+24)=3` and `w1=*(sp+28)=232`. Then division is the function. So were are dividing w1 with wo and storing the ans to wo.
Therefore, on doing *232/3*, we get the integer part as 77. 
Now from the following lines,
```
str	w0, [sp, 28]
ldr	w1, [sp, 28]
ldr	w0, [sp, 12]
sub	w0, w1, w0
```
Storing `*(sp+28)` as 77 and loading it to w1 and similarly `*(sp+12)` i.e, x to wo. Then on subtracting, we basically has with us `wo=77-x`. So, in our question we were asked about the argument which will give us the value as 0. Since x is our parameter which attains the value of argument, therefore that argument is 77. So what we need to get is the hexadecimal form of 77. For that, I went to wsl terminal, used python3 to run the python interpreter, then
found out the hexadecimal as `0x4d`. No were we asked to remove the *0x* and provide the ans in 32 bit, therefore, that is 8 digits. So basically after adding zero, I got `0000004d` to give as unique value inside the flag. So I obtained by final flag like that.
- ` Flag: picoCTF{0000004d}`

## References Used:
- https://www.youtube.com/watch?v=1d-6Hv1c39c&ab_channel=LowLevel
- https://youtu.be/BMvda3d0dt8?si=rb7NvCeByuSzmeoZ



# ARMssembly 0
So, for this challenge, what I did basically was just go through the lines provided in the diassembled code and I was easily able to figure out what is happening in it.
	So by going through the func1 function
```
sub     sp, sp, #16
str     w0, [sp, 12]
str     w1, [sp, 8]
ldr     w1, [sp, 12]
ldr     w0, [sp, 8]
```
So here first value provided as argument is stored in `*(sp+12)` and the second one in `*(sp+8)` but while loading this, if you observe, it is loaded opposite, i.e, wo is stored is the value in *(sp+8) and w1 with value in *(sp+12) respectively.
	Now, after that if you observe the next few lines,
```
      cmp     w1, w0
        bls     .L2
        ldr     w0, [sp, 12]
        b       .L3
.L2:
        ldr     w0, [sp, 8]
.L3:
        add     sp, sp, 16
        ret
        .size   func1, .-func1
        .section        .rodata
        .align  3
```
you can see that the program doing is basically comparing these two numbers. So, we are seeing if w1 is less than wo or not. If it is, then the function *.L2* is called and the higher value is getting loaded in wo and else, *.L3* function is called which loads the other value. So, from observing that, I understood that what were trying to do was to find the higher value among the two.
	Now, while going through the *.LC0* and *main* function, there are two lines which basically confirms our assumption. Those are:
```
.string "Result: %ld\n"
bl  printf
```
So, this printf showed that we are printing the larger value which we have stored and kept with the result string.
	So, now I just looked at the question compared the two values to be given as argument and found out which was the larger value. Then, I converted the given integer to hexadecimal by doing the step shown below in terminal:
```
giridhar@LAPTOP-EQ112OJM:~$ python3
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> hex(4110761777)
'0xf5053f31'
```
Now, in the final value to be provided inside the picoCTF{} brace, *0x* was asked to be removed, so I just gave the *f5053f31* part and got the flag.

` Flag: picoCTF{f5053f31} `

## References Used:
- https://youtu.be/1d-6Hv1c39c?si=_f-vPqgOR6XhN_ZI





