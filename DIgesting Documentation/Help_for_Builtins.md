# Help for built-ins
So, till now, we saw programs that have been created with manpages and help options, but some options are built into the shell itself. Those are builtins. Builtins are invoked just like commands, but the shell handles them internally unlike programs getting launched. We can know available builtins by using
*help* and we can know more about a specific builtin by using *help builtin*.
	In this challenge, I was supposed to get the flag from `challenge` which unlike previous challenges is a builtin in this case. So, I first needed to find the argument to be used to get the secret value for this builtin. So, I did *help challenge*. Then, after finding the suitable argument, I used it to get the secret value after which I used the suitable argument `--secret` which was also provided by the help page itself.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "w-319KPR".
hacker@man~help-for-builtins:~$ /challenge/challenge --secret w-319KPR
ssh-entrypoint: /challenge/challenge: No such file or directory
hacker@man~help-for-builtins:~$ challenge --secret w-319KPR
Correct! Here is your flag!
pwn.college{w-319KPRBo6_EcGB3d2WbjEQS5Q.dRTM5QDL2kTN0czW}
```

## References Used:
None
