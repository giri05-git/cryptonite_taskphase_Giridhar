# C3
Saw a python program which encrypted data based on its index value. The logic needed to be reversed to decipher the text.
The given program was
```
import sys
chars = ""
from fileinput import input
for line in input():
  chars += line

lookup1 = "\n \"#()*+/1:=[]abcdefghijklmnopqrstuvwxyz"
lookup2 = "ABCDEFGHIJKLMNOPQRSTabcdefghijklmnopqrst"

out = ""

prev = 0
for char in chars:
  cur = lookup1.index(char)
  out += lookup2[(cur - prev) % 40]
  prev = cur

sys.stdout.write(out)
```
So I created a copy file and did some modifications in it as given to reverse the steps done by the program.

```
prev = 0
for char in chars:
  cur = lookup2.index(char)
  pres= lookup1[(cur + prev) % 40]
  out+= pres
  prev = lookup1.index(pres)
```

Now I passed the ciphertext into this program using the grep command and I received a python program.

```
giridharsreekumar-picoctf@webshell:~$ cat ciphertext.1 | python3 convert2.py
#asciiorder
#fortychars
#selfinput
#pythontwo

chars = ""
from fileinput import input
for line in input():
    chars += line
b = 1 / 1

for i in range(len(chars)):
    if i == b * b * b:
        print chars[i] #prints
        b += 1 / 1
```
Now given in that was multiple tags but two of them were actually hints, i.e, selfinput and running using python2, so I gave the python program to itself and I got the flag as characters which I joined together to make the flag.

```
giridharsreekumar-picoctf@webshell:~$ cat ciphertext.1 | python3 convert2.py > file.py
giridharsreekumar-picoctf@webshell:~$ cat file.py | python2 file.py
a
d
l
i
b
s
```

`FLAG:picoCTF{adlibs}`

## References Used:
- https://youtu.be/yxQXi_w-PnY?si=tpy4xxkAxJR7DZ_b
