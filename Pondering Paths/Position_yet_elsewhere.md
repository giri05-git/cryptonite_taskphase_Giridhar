# Position yet elsewhere
The filesystem contains multiple dictionaries with each of them containing multiple files. Sometimes, 
the program which we wanna invoke may not be present in the root directory, so it is needed to change the directory in order to execute the program from a specific path. So, for this, navigation around 
directories can be done using the command `cd(change directory)` and then the argument passed is the path which we wanna move to. The challenge required us to execute a program `/challenge/run` from a 
specific path(it is not the root directory). So we need to move to the directory in which this program
is contained. And the catch is, that directory is not provided to us, so in order to let the terminal
give us the directory for our program, first try invoking the program in the root directory, then they
would give us the actual directory of the program, which is `/usr/share/doc` in this
case. So since we received the directory, move to it using cd command and passing the directory as 
argument. Once we are in the directory, now invoke our program `run` giving its absolute path
`/challenge/run` which invokes the program, completes the challenge and earns us the flag.

```bash
Connected!
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/share/doc
hacker@paths~position-yet-elsewhere:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4oAvRrIHFpm7_ealjsTmPVjbutj.dhDN1QDL2kTN0czW}
```
## References Used:
None