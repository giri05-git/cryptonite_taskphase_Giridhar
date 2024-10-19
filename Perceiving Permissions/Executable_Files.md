# Executable Files
Use whatever learned in the previous challenge.
	In this challenge, only hacker user had the power to execute the program */challenge/run* so I changed the access to all the users *(a)* using chmod and then executed the program to get my flag.

```bash
Connected!
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{4qKyb61R5fgy2koM7MUNBlzgrpH.dNzNyUDL2kTN0czW}
```
## References Used:
None
