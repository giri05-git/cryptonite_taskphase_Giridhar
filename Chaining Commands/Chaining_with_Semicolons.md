# Chaining with Semicolons
Piping is done to relate an output of a command to input of other. But then,msometimes we need to run several commands together to get cumulative effects. One of such ways is by chaining the commands using 
*semicolon(;)*.
	In this challenge. I was asked to run */challenge/pwn* and after that */challenge/college* in quick succession by chaining them with a semicolon. After I did that, I received the flag.

```bash
sshgiridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/run
ssh-entrypoint: /challenge/run: No such file or directory
It looks like you invoked /challenge/pwn, but did not chain it with
/challenge/college. Please try again! Remember, you can use ';' to separate two
commands and have them run one after the other.
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ;/challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{oZYWTN90ZG8RWGm599nKkGRZd-P.dVTN4QDL2kTN0czW}
```
## References Used:
None
