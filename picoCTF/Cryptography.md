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

  # Custom Encryption
I downloaded  the python code and on going through it, I understood this code have two levels of encryption, one a normal and other one a XOR Encryption.

```
def encrypt(plaintext, key):
    cipher = []
    for char in plaintext:
        cipher.append(((ord(char) * key*311)))
    return cipher

def dynamic_xor_encrypt(plaintext, text_key):
    cipher_text = ""
    key_length = len(text_key)
    for i, char in enumerate(plaintext[::-1]):
        key_char = text_key[i % key_length]
        encrypted_char = chr(ord(char) ^ ord(key_char))
        cipher_text += encrypted_char
    return cipher_text
```
For this challenge, I created two new scripts, one for each decryption. For the normal one, I just needed to switch the files and operations.
```
def decrypt(ciphertext, key):
    plain=""
    for num  in ciphertext:
       plain+= chr(int((num/ key/ 311)))
    return plain
```

XOR Decrypt was comparatively easier cause there was no need in change of operations because XOR logic works like **P XOR Q = R** and **P XOR R = Q**, therefore it required slight modifications to create the script.
```
def dynamic_xor_decrypt(ciphertext, text_key):
    plain_text = ""
    key_length = len(text_key)
    for i, char in enumerate(ciphertext):
        key_char = text_key[i % key_length]
        decrypted_char = chr(ord(char) ^ ord(key_char))
        plain_text += decrypted_char
    return plain_text
```
After creating decrypt scripts, I needed to do some changes in the program to decrypt the cipher text too. It is done as given.
```
semi_cipher = decrypt(cipher_text, shared_key)
    plain = dynamic_xor_decrypt(semi_cipher, text_key)
    print(f'plain is: {plain[::-1]}')


if __name__ == "__main__":
    message= [61578, 109472, 437888, 6842, 0, 20526, 129998, 526834, 478940, 287364, 0, 567886, 143682, 34210, 465256, 0, 150524, 588412, 6842, 424204, 164208, 184734, 41052, 41052, 116314, 41052, 177892, 348942, 218944, 335258, 177892, 47894, 82104, 116314]
    test(message, "trudeau")
```

On doing this and running the program, I received the flag.
```
giridharsreekumar-picoctf@webshell:~$ python custom_encryption.py
a = 96
b = 24
plain is: picoCTF{custom_d2cr0pt6d_66778b34}
```
`FLAG: picoCTF{custom_d2cr0pt6d_66778b34}`

## References Used:
- https://en.wikipedia.org/wiki/XOR_cipher

