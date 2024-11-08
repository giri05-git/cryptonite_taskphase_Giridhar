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
<img width="1272" alt="cookie" src="https://github.com/user-attachments/assets/4fc7c407-76ba-4fe9-8812-dea6e3598b7f">



