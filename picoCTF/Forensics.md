# tunn3l_vision
For this challenge, I didn't have any pre knowledge, so I went along with the challenge and learnt multiple things on the way. First, I started by downloading the source file whose type was not mentioned. I opened the file using a hex editor and searched how to find file type. So after learning about that, I went through the file which started with *BM* which was the hint for bmp file. So, I saved the file as bmp type and went through it. On going through it, I found out some bytes were orrupted which was replaced as *BAD*. Then, I went through the file format description in Wikipedia to find out the replacements for the corrupts.
<img width="1280" alt="bmp file format" src="https://github.com/user-attachments/assets/d2691581-1613-451b-92bc-88d3b29e2fd5" />
Then the corrupt bytes was supposed to be that of file offset and file header, which has standard hex values 36 and 38 in bmp files. On entering these values, I got an image.


![tunn3l_v1s10n2](https://github.com/user-attachments/assets/201943c7-df01-495a-b4a0-41c56e30db86)

Next was to see if it was cropped image or not. This was done by readjusting the bitmap height which has the offset *16* and default value *01*. On adjusting the bytes, I realised what we received initially was a cropped verion of the actual image. So, I followed the last step again this time with a larger value i.e, *03*. On doing this, I was able to see the flag.

![tunn3l_v1s10n3](https://github.com/user-attachments/assets/ee07a2ed-0684-4efc-88a0-9f3d43db8edf)



`FLAG:picoCTF{qu1t3_a_v13w_2020}`

## References Used:
- https://en.wikipedia.org/wiki/BMP_file_format

  # m00nwalk
For this challenge, I received a wav file that had some random audio in it. By hearing it, I was doubtful there was some encoding done in it. So inorder to decode it, we needed to have some idea on the decoder, so for that, I went through the hints provided. In that, they gave a question *How did pictures from the moon landing get sent back to Earth?* On researching on that, I found it was through SSTV. SSTV is a picture transmission method used to transmit and receive picture using radio.
So after learning it was SSTV, I just searched for few sstv decoders and I found an app called `Robot36`. I played the audio on the app and received an image which had the flag in it.

![WhatsApp Image 2024-12-21 at 17 52 36_235fbd8e](https://github.com/user-attachments/assets/72010520-0995-465d-a99f-d39a3fc02ace)

```THIS CHALLENGE INTRODUCED ME TO THE CONCEPT OF SSTV DECODING```

`FLAG:picoCTF{beep_boop_im_in_space}`

## References Used:
- https://youtu.be/_6AlE4ZsjR4?si=XElu9zp3UnHvabot

  # Trivial Flag Transfer Protocol
The hint gave me an idea that the flag data is hidden in some way. I started the challenge by downloading the file given which was a `.pcapng` file. I searched for softwares to open the  file and found out that the file itself gave it was a wireshark capture file. So I used wireshark to open the file which showed me that it was multiple packet files in it.

<img width="1279" alt="tftpwireshark" src="https://github.com/user-attachments/assets/783d378d-fe2d-46f5-a2c3-c6e58ba2a29a" />

So I tried to extract the files with tftp extension so I get only the required items I need.

<img width="1280" alt="tftpwiresharkextract" src="https://github.com/user-attachments/assets/000d375b-30c7-427d-8084-d9bb478bdc0d" />

So, on extracting, I received the following files.

<img width="1149" alt="tftpfolder" src="https://github.com/user-attachments/assets/2086a231-36ac-434c-b713-4a8357b7fcfd" />

On opening the instructions txt file, I saw `GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA` and opening plan txt file, I saw `VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF`. I tried to decipher it using rot13 website which gave me
`TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN` for instructions file and `IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS` for plan file.

It also contained a Debian file which ran in wsl showed me an app `steghide` in it. Steghide is a stegnography hiding tool, so inorder to access it, we needed a key. On looking at the deciphered text, I assumed the key to be `DUEDILIGENCE` and tried it out.

```
giridhar@LAPTOP-EQ112OJM:/mnt/c/Users/sreek/Downloads/tftp$ steghide extract -sf picture1.bmp
steghide: could not extract any data with that passphrase!
giridhar@LAPTOP-EQ112OJM:/mnt/c/Users/sreek/Downloads/tftp$ steghide extract -sf picture2.bmp
steghide: could not extract any data with that passphrase!
giridhar@LAPTOP-EQ112OJM:/mnt/c/Users/sreek/Downloads/tftp$ steghide extract -sf picture3.bmp
wrote extracted data to "flag.txt".
```
On opening the `flag` file, I got the file.

`FLAG:picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}`

## References Used:
- https://wiki.debian.org/InstallingDebianOn/Microsoft/Windows/SubsystemForLinux
- https://manpages.ubuntu.com/manpages/trusty/man1/steghide.1.html




