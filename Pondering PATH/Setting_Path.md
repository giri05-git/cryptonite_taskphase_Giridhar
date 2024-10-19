# Setting Path
	In this challenge, the path variable is not an empty string. We need to set a director as the path, and then invoke the program `challenge/run`, so we get the flag once *PATH* is overwritten with that one directory.

```bash
 Connected!
hacker@path~setting-path:~$ cd /challenge/more_commands/
hacker@path~setting-path:/challenge/more_commands$ PATH=/challenge/more_commands /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{4I1z8xKvM6_R-ilYVLdfT21C7um.dVzNyUDL2kTN0czW}
```

## References Used:
None
