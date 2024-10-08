# cat: not the pet, but the command!
Cat is an important Linux command that is used for reading out files. It can also read multiple files(concatenate files) when it is provided multiple arguments. When not provided any arguments, cat will read from terminal input and print it as output. 
	In this challenge, we will read from the flag file present in the home directory. So cat command
on the flag file will provide us the required flag value.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{8SPYoOZ1UeDhHl6Fj3ayWpbiGuy.dFzN1QDL2kTN0czW}
```
## References Used:
None
