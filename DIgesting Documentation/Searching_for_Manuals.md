# Searching for Manuals
In this challenge, unlike previous challenge, the manpage of `challenge` is hidden by randomizing its name. So we are first asked to scroll through the mangpage of the command `man` itself to find some useful arguments. From there, with the help of `-k` argument, I was able to read manpage of challenge.
From it, I got the argument `--pcfakx` and that the no 852 should be passed as the argument to the argument. So correctly using this earned me the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~searching-for-manuals:~$ man man
MAN(1)                                            Manual pager utils                                           MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is the system's manual pager.  Each page argument given to man is normally the name of a program, utility
       or function.  The manual page associated with each of these arguments is then found and displayed.  A section,
       if  provided,  will direct man to look only in that section of the manual.  The default action is to search in
       all of the available sections following a pre-defined order (see DEFAULTS), and to show only  the  first  page
       found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)

hacker@man~searching-for-manuals:~$ man -k challenge
pcfakxhhkr (1)       - print the flag!
hacker@man~searching-for-manuals:~$ /challenge/challenge --pcfakxhhkr
Incorrect usage! Please read the challenge man page!
hacker@man~searching-for-manuals:~$ man pcfakxhhkr

CHALLENGE(1)                                      Challenge Commands                                     CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --pcfakx NUM
              print the flag if NUM is 852

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)
hacker@man~searching-for-manuals:~$ /challenge/challenge --pcfakx 852
Correct usage! Your flag: pwn.college{8pAcfGJ52ak0X9x-hQh5PkErTLC.dZTM4QDL2kTN0czW}
```
## References Used
None
