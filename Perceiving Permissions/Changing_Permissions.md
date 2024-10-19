# Changing Permissions
When we try to list information on a file, we are able to see permissions given to different users for different perfomings on it like *read*, *modify* or *executing* the file. Any of this permissions can be adjusted accordingly to the user,group or others. This is done using the `chmod` command giving the permissions along with the mentioning who to give it to as the first argument and the  file name as the second argument.
	In this challenge, I changed the permission as I gave the world permissions to write in the flag file. Then I catted the flag file to get the flag value.

```bash
Connected!
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{4qKyb61R5fgy2koM7MUNBlzgrpH.dNzNyUDL2kTN0czW}
```

## References Used:
None
