# Home Sweet Home
In this challenge, what I was asked to do was basically combining the knowledge of relative pathing I learnt in the module. We need to run the program /challenge/run which will copy the flag to the file which we give as argument. But this argument should follow specific conditions. Argument must be absolute path so it should start from home directory which is given as another condition. And finally, the condition says argument should be only three characters or less. So, in order to represent home directory easily, I used `~`but I didn't know the file name so I randomly tried one letter file names. And since flag started with f, I gave it as the flag name. So giving `~/f` as the argument to the command `/challenge/run` which gave me the flag.

```bash
Connected!
hacker@paths~home-sweet-home:~$ ls
COLLEGE  PWN  college  flag  grep  instructions  instructions.txt  myflag  not-the-flag  profile  the-flag
hacker@paths~home-sweet-home:~$ /challenge/run ~/f
Writing the file to /home/hacker/f!
... and reading it back to you:
pwn.college{8Urj_0BDIZ0e5lv9jXm2xDZxWDt.dNzM4QDL2kTN0czW}
```

## References Used:
None
