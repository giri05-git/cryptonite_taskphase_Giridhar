# Redirecting Output 
The mechanisms behind the handing of input and output  on the commandline contribute to the command line's power. Every process in Linux has three initials, standard channels of communication: `stdin(standard input)`, `stdout(Standard output)`, `stderr(Standard error)`
We are learning to redirect our output to other files.
	In this challenge, we are supposed to redirect our input command of printing the word 
`PWN` to a file called `COLLEGE`.
	
```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{o05qeKG0W0XMo5zCEy_l997j4J6.dRjN1QDL2kTN0czW}
```

## References Used:
None
