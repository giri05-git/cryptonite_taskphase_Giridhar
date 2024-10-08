# implicit relative paths, from /

We know directory doesn't matter when we are providing absolute paths everywhere, but to be honest, 
providing absolute paths everywhere can be a big trouble if the path is too long or complex to track.
So there exists the concept of relative paths. However tho, it is very important in relative paths that
we have idea on the `current working directory(*cwd*)`. Our cwd is the directory where our prompt is 
currently located at. So in order to specify a particular file, we start with the path from where our prompt is located. 
In our challenge, we are asked to run `/challenge/run` using relative path which 
having cwd of `/`. So since our prompt is at */*, we start with the path from right after it, i.e, *c*
in this case. So we give path as `challenge/run`. Thus, the relative path is accessed, program is 
invoked, challenge is completed, and we earn a flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{0hx3J4GThPmKY1UUmz_p61PtNDI.dlDN1QDL2kTN0czW}
```
## References Used:
None
