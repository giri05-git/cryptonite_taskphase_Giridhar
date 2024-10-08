# Searching Manuals
In a man page, we can scroll using *Pg UP* and *Pg DOWN* keys. We can search in the manpage using `/`
key. After searching and entering, we can use `n` to move to the next result and `N` to move to the 
previous result. Also, `?` can be used to search backwards.
	In this challenge, we are asked to search for the argument that will give us the flag for `/challenge/challenge` from `challenge` manpage.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --fj
Initializing...
Correct usage! Your flag: pwn.college{QhZahB5SmE7fBYmxrEy6fV_3J4_.dVTM4QDL2kTN0czW}
```
## References Used:
None
