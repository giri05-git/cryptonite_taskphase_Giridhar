# Learning Complex Usage
Most commands in Linux have simple applications but there are some commands which are very complex. Those commands can have literally have an entire program as its argument. Some commands take arguents to their arguments...

In this challenge, I was asked to do something like that. The program we wanted to invoke was /challenge/challenge which allowed to print arbitrary files to the terminal. So for this program, we were supposed to give the argument `--printfile` and as an argument to this argument, we are supposed to give the path of the file that we want to read. So I gave the path of the *flag* file which contained the flag as the argument to the argument *--printfile* with the command */challenge/challenge* which gave me the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile ./flag
Correct argument! Here is the ./flag file:
cat: ./flag: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile flag
Correct argument! Here is the flag file:
cat: flag: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{Qm3ITdiAskXRw_n5WrbHvpaKCBG.dVjM5QDL2kTN0czW}
```

## References Used:
None
