# Grepping for needle in a haystack
So we understood that cat is used to read out files, but what if the file containing a specific data is 
very big and we are unable to find what we need from it? To help with that, we use grep command.
grep basically searches the file for the lines of text we have given as argument and print them to the console.
	In this challenge, we are asked to access the flag from the file `data.txt` with the absolute path `/challenge/data.txt`, but since it contain lot of content, we need to specify the search string
`pwn.college` which will give us the line of flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{s9h5qr0KEXFl_lCQoMrWyyZwR5D.ddTM4QDL2kTN0czW}
```

## References Used:
None
