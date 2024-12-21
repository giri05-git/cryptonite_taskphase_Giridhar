# tunn3l_vision
For this challenge, I didn't have any pre knowledge, so I went along with the challenge and learnt multiple things on the way. First, I started by downloading the source file whose type was not mentioned. I opened the file using a hex editor and searched how to find file type. So after learning about that, I went through the file which started with *BM* which was the hint for bmp file. So, I saved the file as bmp type and went through it. On going through it, I found out some bytes were orrupted which was replaced as *BAD*. Then, I went through the file format description in Wikipedia to find out the replacements for the corrupts.
<img width="1280" alt="bmp file format" src="https://github.com/user-attachments/assets/d2691581-1613-451b-92bc-88d3b29e2fd5" />
Then the corrupt bytes was supposed to be that of file offset and file header, which has standard hex values 36 and 38 in bmp files. On entering these values, I got an image.

Next was to see if it was cropped image or not. This was done by readjusting the bitmap height which has the offset *16* and default value *01*. On adjusting the bytes, I realised what we received initially was a cropped verion of the actual image. So, I followed the last step again this time with a larger value i.e, *03*. On doing this, I was able to see the flag.

`FLAG:picoCTF{qu1t3_a_v13w_2020}`

## References Used:
- https://en.wikipedia.org/wiki/BMP_file_format


