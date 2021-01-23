# Traboda Forensics Challenges

### Snow Snow

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/1.jpeg?raw=true)

```
--> By the hint "Suspicious between these lines" we can understand that this challenge is based on the Whitespace Steganography.
```

- Reference --> **https://wiki.bi0s.in/steganography/stegsnow/** 

```
--> By refering the wiki.bi0s.in we can get to know that there is a tool named Stegsnow which conceals messages in text files by appending tabs and whitespaces at the end of lines.
```

- Download the txt file which has to be decrypted.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/2.jpeg?raw=true)

#### Installation

```
$ sudo apt install stegsnow
```

#### Decryption

```
$ stegsnow -C <Filename>

--> Filename = 1.txt ( In my case )

$ stegsnow -C 1.txt
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/3.jpeg?raw=true)

- Now we get a flag which is being encrypted cryptographically.

```
--> ntio{eP1B35x4K3_aB3O0_q5_K00t}
```

- The next step is to decryt the flag using cryptography.

- Decryption Online Tool --> **https://www.dcode.fr/caesar-cipher**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/4.jpeg?raw=true)

- Finally we get the flag in the right format.

```
--> flag{wH1T35p4C3_sT3G0_i5_C00l}
```

### You Can't See Me

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/5.jpeg?raw=true)

- If we try to open the given **PNG** image it gives the **Invalid Format Error**. 

```
--> We can understand that there are some errors in the Hex values.
```

- Reference --> **https://wiki.bi0s.in/steganography/pngcheck/** 

```
--> By refering the wiki.bi0s.in we can get to know that there is an official PNG tester and debugger tool named Pngcheck which tests the PNG image files for corruption, display size, type, compression info.
```

#### Installation

```
$ sudo apt install pngcheck
```

#### Installation and Process

```
$ pngcheck <Filename>

--> Filename = 1.png ( In my case )

$ pngcheck 1.png
```

- If we execute this command we can get to know that there is an error in the **PNG**

#### Errors

```
Error 1 --> IHDR Chunk

Error 2 --> IDAT Chunk
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/6.jpeg?raw=true)

#### Decryption

- The next step is to correct the errors using the Hex Editor.

- Ghex is a tool which helps us to view and edit the hex data or hex dump of an image.

#### Tool Installation

```
$ sudo apt install ghex
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/7.jpeg?raw=true)

#### Usage

```
$ ghex <Filename>

Filename --> 1.png ( Initial Image ) --> In my case
         --> 2.png ( After Correcting Errors in IHDR Chunk ) --> In my case
         --> 3.png ( After Correcting Errors in IDAT Chunk ) --> In my case
```
 - Finally we get the flag in the corrected **PNG Image**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/8.jpeg?raw=true)

### My - First - Stegnography

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/9.jpeg?raw=true)

- Reference --> **https://wiki.bi0s.in/steganography/steghide/** 

- Here we get two **JPEG** images and download the images.
- Since two images are given we can have a wild guess that this challenge can be solved using **Steghide** tool.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/11.jpeg?raw=true)
![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/12.jpeg?raw=true)

```
--> By refering the wiki.bi0s.in we can get to know that there is a tool named Steghide which is used to embed and extract secret messages in images. 

--> It supports all the general formats of images like .png, .jpg etc.
```

#### Installation

```
$ sudo apt install steghide
```

#### Usage 

```
$ steghide extract -sf <Filename>

 (output)$ Enter passphrase : ********

 (output)$ wrote extracted data to "xxx.txt"
```

#### Decryption

```
$ steghide extract -sf 1.jpeg
```

- Then it prompts us to enter the **Passphrase**.
- Since we dont have any **Passphrase** we can just click **ENTER**.
- Now the **Passphrase** for the next image has been extracted in the file named **password.txt**.

```
$ steghide extract -sf 2.jpeg

(output)$ d4rk_s1d3
```

- Then it prompts us to enter the **Passphrase**.
- Since we have **Passphrase** we can enter **d4rk_s1d3** and click **ENTER**.
- Now the data has been extracted in the file named **plans.txt**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/10.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/13.jpeg?raw=true)

```
Flag --> inctfj{w3_4r3_pl4nt1ng_4_b0mb}
```

### Security 101

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/14.jpeg?raw=true)

- Download and unzip the zip file.
- When you unzip you can find that 2 files are extracted out of which one is a image and one is the password protected file.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/16.jpeg?raw=true)

- Hint is given as **Nerd : Some people keep their username as password. Why would they do that ? Me : Hmm ...**
- We can understand that username is meant to be the creator of the image or the owner of the image.
- So next step is to analyse the extracted image.
- **Tool -->** http://fotoforensics.com/analysis.php?id=f38a1f992968fda2c000b2f25fe70a8796e1b43a.33254
- Now if you try to view the meta data of the image then you can find that the **Creator** is **R3DDIT_US3R**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/15.jpeg?raw=true)

- Now if you try to extract the one of the other previously password protected extracted file with the password as **R3DDIT_US3R** then you can extract one another which contains the flag.

- Here we are giving the password as **R3DDIT_US3R** since the hint is given as **Some people keep their username as password.**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/17.jpeg?raw=true)

```
Flag --> inctfj{1ts_4ll_f1ne_tru5t_m3}
```

### Jay-chot

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/18.jpeg?raw=true)

- If you download the file and try to open it then it will show an error.
- We can understand that the format is not correct which means that the **Hex Dump** has to be corrected.
- **Online Tool -->** https://hexed.it/
- Modify the Magic Numbers and try to open the file.
- It opens and you can see the flag. 

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/19.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/20.jpeg?raw=true)

```
Flag --> flag{a4aa04741a8d3a952a 7ec88457991b97}
```

### The Office Trouble I

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/21.jpeg?raw=true)

- Try cracking the password using the **Frackzip** tool.
- Try **Dictionary** Attack using **rockyou.txt** file.

#### Installation

```
$ sudo apt install fcrackzip
```

#### Usage

**Brute force Attack**

```
$ fcrackzip -v -b -u -p <file_name.zip>
```

**Dictionary attack**

```
$ fcrackzip -v -u -D -p <path_to_wordlist_file> <file_name.zip>
```

**Rockyou.txt File -->** https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/22.jpeg?raw=true)

- Here we use **Dictionary Attack**
```
$ fcrackzip -v -u -D -p rockyou.txt 1.zip
```

- We get the password and then if we try to unzip it using the **password** then we shall get the extracted image which contains the **flag**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/23.jpeg?raw=true)

```
Flag --> inctfj{dw1ght_1s_cr4zy_bu7_awes0me}
```

### Always Has Been

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/24.jpeg?raw=true)

- Download the **PNG** image.
- You wont be able to see anything.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/25.jpeg?raw=true)

- From the hint given in the question, **Look up in the BLUE sky ! It's a bird, it's a PLANE or wait .. It's both ? But how ?** we can understand that the image has to be analysed in different planes.
- Using **Stegsolve** we can analyze images in different planes by taking off bits of the image.

#### Installation

```
$ wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
$ chmod +x stegsolve.jar
$ mkdir bin
$ mv stegsolve.jar bin/
```

#### Usage

- Stegsolve can be invoked by placing the image in the /bin folder and running stegsolve.

```
$ java -jar stegsolve.jar
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/26.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/27.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/28.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/29.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/30.jpeg?raw=true)

```
Flag --> inctfj{th3_fl4g_was_liter4lly_ins1de_4_m3me}
```

### Back to San Andreas

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/31.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/32.jpeg?raw=true)

- Here when we try to open the image then we cannot find anything.
- So next step is to analyze the **JPEG** image.
- Jsteg is a package for hiding data inside JPEG files with a technique known as steganography. 
- This is accomplished by copying each bit of the data into the least-significant bits (LSB) of the image. 

#### Installation

```
$ sudo wget -O /usr/bin/jsteg https://github.com/lukechampine/jsteg/releases/download/v0.1.0/jsteg-linux-amd64
$ sudo chmod +x /usr/bin/jsteg
$ sudo wget -O /usr/bin/slink https://github.com/lukechampine/jsteg/releases/download/v0.2.0/slink-linux-amd64
$ chmod +x /usr/bin/slink
```

#### Revealing data

```
$ jsteg reveal <in.jpg> <output file name>
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/33.jpeg?raw=true)

- The data will be extracted in the specified file.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/34.jpeg?raw=true)

- If we open the file we can see that there is a link.
- Now if we open the link then we shall see the **flag**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/35.jpeg?raw=true)

```
Flag --> inctfj{gr0ve_5treet_f0r_l1fe}
```

### 10111001

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/36.jpeg?raw=true)

- This challenge is based on LSB steganography.
- Zsteg is also a tool like Jsteg but it is used to detect LSB steganography only in the case of PNG and BMP images.

#### Installation

```
$ sudo apt install ruby
$ sudo gem install zsteg
```

#### Usage

```
$ zsteg <filename>
```

- If we run this we can find some meaningful data embedded in the LSBs of the PNG image. 
- This meaningful data can help us in solving the challenge.
- Among the LSB's we can see a line this, 

**This is the Flag --> NFXGG5DGNJ5TI3K7ORUDGX2MGNAVG5C7GVUUO3RRMYYWGNDOKRPWEVKUL4YV6YZUJZPXI4RQOVBEYM27LEYHKXZUL5WDAVD5**

- It is encoded in **Base32** format.
- We need to decode it to get the flag.
- **Online Tool -->** https://emn178.github.io/online-tools/base32_decode.html

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/37.jpeg?raw=true)

```
Flag --> inctfj{4m_th3_L3ASt_5iGn1f1c4nT_bUT_1_c4N_tr0uBL3_Y0u_4_l0T}
```

### Detailed View

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/38.jpeg?raw=true)

- Download the image.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/39.jpeg?raw=true)

- Hint is given as **there is more to know about this file** which symbolically means to look indepth detail of the image. 
- Meta data is the indepth information of the file.
- **Online Tool -->** https://exifinfo.org/detail/psTncqjsVTTZGxnzXzhDEQ

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/40.jpeg?raw=true)

- We can see a link in the **comment**
- **Link -->** https://pastebin.com/KudUCfTC
- If we open the link then we will be able to see the **Base64** encrypted flag.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/41.jpeg?raw=true)

- Next step is to decrypt it.
- **Online Tool -->** https://decode.urih.com/data/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/42.jpeg?raw=true)

```
Flag --> flag{M15sI0N_aCc0MPL15h3D}
```

### Con-The-Cat

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/43.jpeg?raw=true)

- Download the **PNG** image.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/44.jpeg?raw=true)

- Binwalk is a tool used mainly for searching embedded files and executable code within another data file.

#### Installation

```
$ sudo apt install binwalk
```

#### Usage

```
$ binwalk -e <file-name>
```

```
$ binwalk -e 1.png
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/45.jpeg?raw=true)

- Here in the above image, we see that there is a 'jpg image' that has a compressed 'images' in it and we see that it is, it is embedded within the jpg image file. 
- To extract it we can make use of a carving tool dd. 
- It can carve out data from specific offsets that are passed as arguments to the tool along the with the file that needs to be read. 

```
$ dd if=<filename> of=<filename> bs=1 skip=<offset>
```

- if = the file from which data has to be extracted is passed as an argument.
- of = has the name of the file that we give after extraction. 
- skip = is the offset of the file that has to be read.
- bs = i the byte skip argument that specifies the frequency of reading data from the given file.

```
$ dd if=1.png of=2.png bs=1 skip=7821

--> Here 7821 is one of the offsets of the file.
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/46.jpeg?raw=true)

```
Flag --> inctfj{y0u_c4nt_s33_m3!!}
```

### Reference --> https://wiki.bi0s.in/steganography/intro/