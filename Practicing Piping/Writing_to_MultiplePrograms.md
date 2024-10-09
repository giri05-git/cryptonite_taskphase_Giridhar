# Writing to Multiple Programs
We are allowed to use utilities and and hook them up to input and output side of a program rather than just files because Linux follows *Everything is a file* philosophy. But to do this process substitution,
the command should be given inside a `()` by giving the redirecting operator or other operators outside this bracket.
	In this challenge, I had the program `/challenge/hack`. I needed to duplicate its output as input to other two commands `/challenge/the` and `/challenge/planet`. So in order to take the output as input, we need to use piping. On left side is the files which output is taken and on right side comes the input file. An inorder to duplicate the data, I used the tee command. So basically in a single line, when I gave `tee >(/challenge/the)` which duplicated the output data and took it as input by piping. Then, using piping one more time, again the output is taken as the input by */challenge/planet*.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~writing-to-multiple-programs:~$ cd /challenge
hacker@piping~writing-to-multiple-programs:/challenge$ /hack | tee >(the) | planet
ssh-entrypoint: /hack: No such file or directory
ssh-entrypoint: planet: command not found
ssh-entrypoint: the: command not found
hacker@piping~writing-to-multiple-programs:/challenge$ cd /home/hacker
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) | /challenge/planet
Congratulations, you have duplicated data into the input of two programs! Here is your flag:
pwn.college{AL9EdVdOnePHeZDA0sI-ABxvovo.dBDO0UDL2kTN0czW}
```

## References Used:
None
