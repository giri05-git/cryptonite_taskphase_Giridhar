## explicit relative path

When the relative path is **_naked_**, it means we just directly specified the directory to go into with
respect to the current working directory(cwd). We can represent relative paths more explicitly. In 
almost all operating systems, including Linux, every directory has two implicit entries that carry a 
meaning which we can reference in paths. Those are `.` and `..`. The single dot translate as the current
directory and the double dot represent parent directory. So, what I basically mean is that using 
`./` doesn't affect our reference pathing as it translates to the naked pathing itself. 
> We can use `./` as much as we want and before or after pathing cause all of them will be identical.

In our challenge, we are asked to do what we did in the previous challenge itself, which is invoking 
a program challenge from its cwd `/` doing relative pathing by first moving into the `/` directory 
using cd. But then the catch is, providing it naked won't give us the flag as they need us to get familiarized with the implicit entries. So we use *./* in our path to complete the challenge. But again, I was unsure how many times to use it, so I started with applying it one time in order to give for a 
trial and error, but apparently, the application was correct and challenge was completed, flag was provided.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{smSEEVhhG1sG2_xBwGUHHjdcTaX.dBTN1QDL2kTN0czW}
```
## References Used:
None
