# Process Exiting Codes
All the programs finished and terminates, can be only done so with an exit code. This can be accessed using the special `?` variable.
	In this challenge, I accessed the exit code that is returned by the `/challenge/get-code`
and then used that code as an argument when I ran `/challenge/submit-code` to exit the program and get the flag.

```bash
 Connected!
hacker@processes~process-exit-codes:~$ /challenge/get-code $?
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
224
hacker@processes~process-exit-codes:~$ /challenge/submit-code 224
CORRECT! Here is your flag:
pwn.college{0gGUY9RhNHLB3mNB3YWd5F-wZ1E.dljN4UDL2kTN0czW}
```
## References Used:
None
