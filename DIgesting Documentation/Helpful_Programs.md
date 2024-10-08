# Helpful Programs
Some programs can't have manpage, but without manpage also, we can get to know how to run with the help of a special argument. That argument is `--help`, but it can often be `-h` or in some rare cases, `-?`,
`help`, or other estoric values.
	In this challenge, I needed to do something similar to that. I didn't have a manpage for challenge so I used help. Then it gave me the optional arguments which can be used out of which I needed to find the needed one to get the flag. But since this concept is little tricky, I got confused with what to be given exactly as the argument, the one written or the left or its definition argument written 
on right. So, after some errors and mistakes, I found out that like previous challenges, we were supposed to give the argument `--give-the-flag` and some value as an argument to this argument. In order to do that, I used `--print-value` to get the value which was 704 in my case. Then atlast, correct usage 
led to getting the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~helpful-programs:~$ --help
ssh-entrypoint: --help: command not found
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -g GIVE_THE_FLAG
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: invalid int value: 'GIVE_THE_FLAG'
hacker@man~helpful-programs:~$ /challenge/challenge --give-the-flag
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: expected one argument
hacker@man~helpful-programs:~$ -h
ssh-entrypoint: -h: command not found
hacker@man~helpful-programs:~$ /challenge/challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge --print-value
The secret value is: 704
hacker@man~helpful-programs:~$ /challenge/challenge --give-the-flag 704
Correct usage! Your flag: pwn.college{Mpk7HeQuTTbkfTXQyScwLULT0BW.ddjM4QDL2kTN0czW}
```

## References Used:
None
