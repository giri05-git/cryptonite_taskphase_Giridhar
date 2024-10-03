# Intro to Arguments
We are given us an introduction on arguments on this challenge. ```Arguments``` are basically additional data passed to the command. The shell parses our inputs into commands and arguments, where the first word of our line is the command and the rest are all arguments. One of the most simple command is `echo` which basically echoes back all the arguments entered back onto the terminal. In order to complete the challenge, we invoke the command `hello` followed by the argument `hacker` which earns us the flag. 
```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{ADCySNFE7mW9NFaDDWmWezhGBjT.dhjNyUDL2kTN0czW}
```
## Refernces Used:
None

