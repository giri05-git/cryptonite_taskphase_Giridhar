# Implicit relative path
We are looking at a very slightly improved version of our previous challenges. Linux contains a safety
measure where it explicitly avoids automatic looking in the `current working directory(cwd)` when 
a naked path is provided.
Providing an example:

```bash
hacker@dojo:~$ cd /challenge
hacker@dojo:/challenge$ run
```
Here, this program is not invoked. Linux has provided this safety feature because when Linux is 
searching the current directory for programs every time we enter a naked path, some programs in our
cwd which has same names as core system utilities may accidentally gets executed and cause troubles.
So, in order to invoke a program, we should use the help of implicit entries `.` which would reassure
the current directory and help us invoke the program.

In our challenge, we are asked to invoke a program `run` when our current directory is `/challenge`.
So, in order to make our current directory */Challenge* from *root*, use cd command. Then once, the 
directory is changed, instead of providing naked path of our program, provide the path with the help
of implicit entry as `./run`. This would get help us invoke the program without any troubles, 
finishing the challenge and earning us the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{YoezWnt0kPHjth3NuFoTBoJ362U.dFTN1QDL2kTN0czW}
```
## References Used:
None
