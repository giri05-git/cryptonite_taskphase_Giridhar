# Redirecting Input
Like redirecting output of programs, we can also redirect their inputs. It is done using `<`.
In this challenge, we are redirecting the input PWN to the program `/challenge/run`. But before that, I needed to enter a command which gave the value *COLLEGE* and redirect its output to this file first.

```bash
Connected!
hacker@piping~redirecting-input:~$ echo COLLEGE>PWN
hacker@piping~redirecting-input:~$ /challenge/run <PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{oT8QTi6RpoCRuKlRzgYUFrjSvRB.dBzN1QDL2kTN0czW}
```

## References Used:
None
