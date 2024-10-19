# Storing Command Output
We know that we can invoke a program and get its output but this output is not stored anywhere. So, in order to store output of a command into a variable, we use command substitution.
	In this challenge, we need to read the output of `/challenge/run` command and store it in the variable `PWN`. and this contains the flag value. So I did *$(/challenge/run)* to get the output and it was stored to *PWN* using *=*.
```bash
Connected!
carhacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{4EcLO-1fuNAOk5LcPBpmHeNZb5S.dVzN0UDL2kTN0czW}
```

## References Used
None
