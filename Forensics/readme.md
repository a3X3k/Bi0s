# Set 2 Forensics Challenges


- Initially the file will be encrypted.
- Use frcrack Zip to crack the Password.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/91.jpeg?raw=true)
![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/92.jpeg?raw=true)

### B Challenge

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/97.jpeg?raw=true)

#### Installation

```
$ sudo apt install binwalk
```


#### Usage

```
$ binwalk -e <file-name>
$ binwalk -e 1.jpg
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/93.jpeg?raw=true)

- Here in the above image, we see that there is a jpeg image and a ZIP in it and we see that, it is embedded within the jpeg image file.
- To extract it we can make use of a carving tool dd.
- It can carve out data from specific offsets that are passed as arguments to the tool along the with the file that needs to be read.

```
$ dd if=<filename> of=<filename> bs=1 skip=<offset>
```

- `if = the file from which data has to be extracted is passed as an argument.`
- `of = has the name of the file that we give after extraction.`
- `skip = is the offset of the file that has to be read.`
- `bs = i the byte skip argument that specifies the frequency of reading data from the given file.`


![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/94.jpeg?raw=true)

- If we try to extract all files we will get a `Zip File`.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/95.jpeg?raw=true)

- Now we get the `flag` inside the Image.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/96.jpeg?raw=true)

```
Flag --> inctf{fr33dom_w4s_n0t_w0n_0v3rnit3}
```

### E Challenge

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/98.jpeg?raw=true)

- Here when we analyze using `bin walk` we cant find anything. 
- So Next option is to look into the `Hex Dump`.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/99.jpeg?raw=true)

- Online Tool --> https://hexed.it/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/100.jpeg?raw=true)

- Here at last we shall see that there are some `Hex Encrypted Text`.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/101.jpeg?raw=true)

- We have to decode it to get the `ASCII` Text.

```
696e6374667b337831663730304c5f69735f673030645f215f67756573735f2121217d
```

- Online Tool --> https://www.convertstring.com/EncodeDecode/HexDecode

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/102.jpeg?raw=true)

```
Flag --> inctf{3x1f700L_is_g00d_!_guess!!!}
```

### S Challenge

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/103.jpeg?raw=true)

- When we analyze using `bin walk` we cant find anything. 
- So Next option is to look into the `Hex Dump`.
- Online Tool --> https://hexed.it/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/104.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/100.jpeg?raw=true)

- Here at last we shall see that there are some `Base 64 Encrypted` text.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/105.jpeg?raw=true)

- We have to decode it to get the `ASCII Text`.

```
aW5jdGZ7c3RyaW5nc19hcmVfdXNlZnVsfQ==
```

- Online Tool --> https://www.base64decode.org/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/106.jpeg?raw=true)

```
Flag --> inctf{strings_are_useful}
```

### S_H Challenge

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/107.jpeg?raw=true)

- When we analyze using `bin walk` we cant find anything. 
- So Next option is to look into the `Hex Dump`.
- Online Tool --> https://hexed.it/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/108.jpeg?raw=true)

- Here at last we shall see that there are some Hex Encrypted Text.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/109.jpeg?raw=true)

- We have to decode it to get the ASCII Text.

```
526d7868636d564a626c526f5a5568766247554b
```

- Online Tool --> https://www.rapidtables.com/convert/number/hex-to-ascii.html

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/110.jpeg?raw=true)

- We shall see that there are some Base 64 Encrypted text.
- We have to decode it to get the ASCII Text.

```
RmxhcmVJblRoZUhvbGUK
```

- Online Tool --> https://www.base64decode.org/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/111.jpeg?raw=true)

```
FlareInTheHole
```

- We shall understand that this is an Password for the file.
- Now if we try to extract with **StegHide** we shall extract the hidden file.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/112.jpeg?raw=true)

[Click me to view the File](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/flag.txt)

```
Flag --> inctf{1_l0ve_c0unt3r_str1ke_1.6}
```

### Z Challenge

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/114.jpeg?raw=true)

- We can see that there is an `QR Code`.
- We shall get the `flag` if we decode it.
- Zbarimg is a tool used to scan and decode QR codes from image files

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/113.jpeg?raw=true)

#### Installation

```
$ sudo apt-get install zbar-tools
```

#### Usage

```
$ zbarimg <file-name>
```

```
Flag --> flag{N0w_y0u_a_little_about_zbarimg}
```

### SS Challenge

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/115.jpeg?raw=true)

- In this challenge we shall use the `StegSolve Tool` to decode the `Hidden text`.
- `Stegsolve` is used to `analyze images` in `different planes` by taking off `bits` of the image.

#### Installation

```
$ wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
$ chmod +x stegsolve.jar
$ mkdir bin
$ mv stegsolve.jar bin/
```

#### Usage

- `Stegsolve` can be invoked by placing the image in the `/bin` folder and running stegsolve.

```
$ java -jar stegsolve.jar
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/116.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/117.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/118.jpeg?raw=true)

```
Flag --> pctf{st3gs0lv3_1s_u53ful}
```

### FS Challenge

- The given `PNG` shows error since its `hex dumps` are in wrong format.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/119.jpeg?raw=true)

- So we have to edit the `Hex Chunks`.
- Online Tool --> https://hexed.it/

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/d0e0757f2c0bfa48732ccf712da95ad9a948a2f0/Forensics/Assets/120.jpeg?raw=true)

 - We have to edit the header and add extra `00` Bytes in that.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/121.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/122.jpeg?raw=true)

- Finally we get the `Flag`.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/123.jpeg?raw=true)

```
Flag --> inctfj{4Ye@aRr4mbB4_u_g0T_m3!}
```

### Pattern Printing 1

[Pattern Printing 1](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/Pattern_1.sh)

```
#!/bin/bash

for(( i = 5 ; i > 0 ; i--))
do
	for(( j = 0 ; j < $i ; j++))
	do
		echo -n "*"
	done
	echo ""
	
done
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/128.jpeg?raw=true)


### Pattern Printing 2

[Pattern Printing 2](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/Pattern_2.sh)

```
#!/bin/bash

space=4
star=1
for(( i = 1 ; i <= 5 ; i++))
do
	for((j=0;j<space;j++))
	do
		echo -n " "
	done
	
	space=$(( space-1 ))
	
	for((j=0;j<$star;j++))
	do
		echo -n "*"
	done
	star=$(( star+2 ))
	echo ""
done
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/129.jpeg?raw=true)

### Revers Me

- Using the `Python Script` we can `reverse` the contents of the file.

```
filename = 'revers.me'
f = open("1.txt", "w")

with open(filename, 'rb') as fopen:
    line = fopen.read()
    line1 = line[::-1] 
    f.writelines(line1) 

f.close()
```

- Then we can `print` all `printable characters` from the File using `strings` command and `filter` the output using `grep`.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/124.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/127.jpeg?raw=true)

[Python File](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/1.py)

[Revers File](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/revers.me)

[Text File](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/1.txt)

[Bash Script File](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/1.sh)

```
Flag --> inctf{Y0u_ar3_g00d_4t_rev3rs1ng_1_gu3ss}
```

### Stranger Things

- `Download` the `Challenge` File.
- We shall `Extract` the `text` from the `file` using `strings` command.

```
Obviously, this is not the flag, but I can give you the flag format.
inctf{s0m3_l33t_str1ng}
PS: "inctf" in the flag is also case insensitive. Find three flags in the file.
```

- First try with `case sensitive` command.

```
strings find-flags-in-me | grep 'inctf'
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/130.jpeg?raw=true)

 - Now try with `case insensitive` command.

```
strings find-flags-in-me | grep -i 'inctf'
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/131.jpeg?raw=true)

- Now we have `Extracted` `Two` `Flags`.
- One more flag is there to be Extracted.
- Now lets try some random `Error and Trial Method` kind of thing.

```
#!/bin/sh
strings find-flags-in-me | grep -i 'i'
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/132.jpeg?raw=true)

- Lets `Replace` the `dots` with `Empty Space`.

```
tr "Character to be Replaced" "Replacement Character"

$ tr '.' ' '
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/133.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/134.jpeg?raw=true)

- We shall see that there are Empty Spaces.
- So next lets try to `Remove` the `White Space`.
- [Reference](https://www.toolbox.com/tech/programming/question/sed-command-to-replace-whitespace-with-comma-032411/#:~:text=Simple%20SED%20commands%20are%3A,space%20with%20a%20single%20comma.)

```
sed 's/ //g'

$ tr '.' ' '
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/135.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/136.jpeg?raw=true)

- Now lets try to `grep` for `flag` format.
- When we try with different `inctf` combinations we shall get some outputs.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/138.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/137.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/139.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/140.jpeg?raw=true)

- After trying some `combinations` we shall find that the flag is `scattered` in `different places`. 

```
#!/bin/sh

strings find-flags-in-me | grep -i 'ctf'

# s/ //g means to remove the whitespace
xxd find-flags-in-me | tr '.' ' ' | sed 's/ //g' | grep -i 'inc'

# grep -i is for case insensitive
xxd find-flags-in-me | tr '.' ' ' | sed 's/ //g' | grep -i 't'
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/142.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/141.jpeg?raw=true)

[Bash Script](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/2.sh)

```
Flags :

inctf{y4yy!!!_found_th3_fir5t_fl4g}
InCtF{G00d_jobb!!This_is_the_2nd_on3}
inctf{th1s_1s_th3_l4st_0ne}
```

### Twins Challenge

- `Download` the `Challenge` Files.

```
I Hope These files are as same as twins. But find it yourself.
```

- Initially tried to `Analyze` through `various Tools` and found out that there are some differences in some `Byte``positions`.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/159.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/161.jpeg?raw=true)

- Then `finally` ended up with the `Bash` Script.

```
#!/bin/sh

f1=Twin1
f2=Twin2

size=$(stat -c%s $f1)
i=0
while [ $i -lt $size ]; do
  if ! r="`cmp -n 1024 -i $i -b $f1 $f2`"; then
    printf "%8x: %s\n" $i "$r"
  fi
  i=$(expr $i + 1024)
done
```

[Reference](https://stackoverflow.com/questions/12118403/how-to-compare-binary-files-to-check-if-they-are-the-same)

- This `output's` the `lines` with the `different` `bytes`. 
- But the `output` contains `offset` and other `informations` too.
- For my convenience I am `formatting` it to get the `proper flag`.
- We shall use the sed to remove the spaces between the `bytes` to properly get our `flag`.
- `sed 's/ //g'` does the `job`.

```
sed 's/ //g'
```

- After `Removing` the `white spaces` lets only `Display` the `Character` at the `Position` where the `Characters` are `Different`.
- `sed -e 's/\(^.*\)\(.$\)/\2/'`  `displays` only the `Last Character` of the `Line`.

```
sed -e 's/\(^.*\)\(.$\)/\2/'
```

- After making `several formats` in the `Bash Output` we get the `Flag` as expected.

```
#!/bin/sh

f1=Twin1
f2=Twin2

size=$(stat -c%s $f1)
i=0

echo -n "The Flag is : "

while [ $i -lt $size ]; do
  if ! r="`cmp -n 1024 -i $i -b $f1 $f2`"; then
    printf "%8x: %s\n" $i "$r" | sed 's/ //g' | sed -e 's/\(^.*\)\(.$\)/\2/' | tr '\n' ' ' | sed 's/ //g'
  fi
  i=$(expr $i + 1024)
done

echo ""
```

[Bash Script](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/4.sh)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/160.jpeg?raw=true)

`                                                                                   `

- One of the other way of finding the difference by `GUI` is with the `vimdiff` tool.
- [Reference](https://superuser.com/questions/125376/how-do-i-compare-binary-files-in-linux)


```
--> Converting to Hex

$ xxd Twin1 > Twin1.hex
$ xxd Twin2 > Twin2.hex
```

- Then Analyze using Vimdiff

```
$ vimdiff Twin1.hex Twin2.hex
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/143.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/144.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/145.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/146.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/147.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/148.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/149.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/150.jpeg?raw=true)

- We shall see the `Comparisons` at each `Bytes`.
- Now lets Analyse the differences at `Each Byte` seperately using `xxd` and `grep` commands alike the previous challenge.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/151.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/152.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/153.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/154.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/155.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/156.jpeg?raw=true)


```
#!/bin/sh

xxd Twin1 > Twin1.hex
xxd Twin2 > Twin2.hex

xxd Twin1 | grep 0023b990
xxd Twin2 | grep 0023b990

echo ""

xxd Twin1 | grep 0023be20
xxd Twin2 | grep 0023be20

echo ""

xxd Twin1 | grep 0023c200
xxd Twin2 | grep 0023c200

echo ""

xxd Twin1 | grep 0023c640
xxd Twin2 | grep 0023c640

echo ""

xxd Twin1 | grep 0023c960
xxd Twin2 | grep 0023c960

echo ""

xxd Twin1 | grep 0023ce50
xxd Twin2 | grep 0023ce50

echo ""

xxd Twin1 | grep 0023d3c0
xxd Twin2 | grep 0023d3c0

echo ""

xxd Twin1 | grep 0023d830
xxd Twin2 | grep 0023d830

echo ""

xxd Twin1 | grep 0023dca0
xxd Twin2 | grep 0023dca0

echo ""

xxd Twin1 | grep 0023dfd0
xxd Twin2 | grep 0023dfd0

echo ""

xxd Twin1 | grep 0023e620
xxd Twin2 | grep 0023e620

echo ""

xxd Twin1 | grep 0023eab0
xxd Twin2 | grep 0023eab0

echo ""

xxd Twin1 | grep 0023f190
xxd Twin2 | grep 0023f190

echo ""

xxd Twin1 | grep 0023f6d0
xxd Twin2 | grep 0023f6d0

echo ""

xxd Twin1 | grep 0023fb90
xxd Twin2 | grep 0023fb90

echo ""

xxd Twin1 | grep 00240020
xxd Twin2 | grep 00240020
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/157.jpeg?raw=true)

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/158.jpeg?raw=true)

- Here we shall see that at `Each Byte position` `One` `letter` `Differs`.
- Now if we try to `Concatenate` all the characters at `Different` `Positions` then we shall get the `Final` `String`.

[Bash Script File](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/3.sh)

```
Flag --> inctf{y0uGotm3}
```


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

- Here in the above image, we see that there is a 'jpg image' that has a compressed 'images' in it and we see that, it is embedded within the jpg image file. 
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

### Snow Man

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/47.jpeg?raw=true)

- Download the file and we can understand that it comes under **Whitespace Steganography**.
- Stegsnow is a tool for concealing messages in text files by appending tabs and whitespaces at the end of lines.
- The encoding used by snow relies on the fact that whitespaces and new lines won't be displayed in text editors.

#### Installation

```
$ sudo apt install stegsnow
```

#### Decryption

```
$ stegsnow -C -p "<Password>" <Txt File>
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/48.jpeg?raw=true)

- After decrypting we will get a flag which is **BASE-64** Encoded.
- Using online tool we shall decrypt it.
- **Online Tool --> https://www.dcode.fr/base-64-encoding**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/49.jpeg?raw=true)

```
Flag --> inctfj{h4h4_st3gsn0w_i5_c00000001}
```

### The Office Trouble II

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/50.jpeg?raw=true)

- In this challenge we need to crack the pdf password and find the **flag**
- PDF Crack is a tool for recovering the pass for Encrypted PDF files. 
- Encrypted files means the metadata of the file was encrypted with some characters.

**It has some special features like:**

- Checks with the system password and also the user provided password.
- It can crack password by brute-forcing method only for character sets and only when we provide the maximum and minimum length of the password.
- Searches the password from the wordlist.
- Optimized search for owner-password when user-password is known.

#### Installation

```
$ sudo apt-get install pdfcrack
```

#### Usage

**Brute-forcing**

```
$ pdfcrack -f <file_name>
```

**Wordlist Cracking**

```
$ pdfcrack -f <file_name> -w <wordlist_file>
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/51.jpeg?raw=true)

- After decryption we get a password and now we will be able to open the pdf.

```
Password --> fear420
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/52.jpeg?raw=true)

### Traffic 13

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/53.jpeg?raw=true)

- As given we have to analyze the network packages sent and received.
- Wireshark is the most commonly used network protocol analyser and the de facto standard across many commercial and non-profit enterprises.
- It shows the protocol of each packet captured and also the protocol hierarchy of the network whose pcap was made.
- The hex buffer of each packet can be analysed separately and layer by layer.

#### Installation

```
$ sudo apt install wireshark-qt
```

- Open **WireShark** and analyze the **TCP** packages.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/54.jpeg?raw=true)

- After analyzing various **TCP** packages we shall find the **flag**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/55.jpeg?raw=true)

- But the flag is encryted.

```
Encrypted Flag --> vapgsw{o3j4er_0s_plO3E_GUe3ng5}
```

- So we have to decrypt it using the online Tool. 
- **Online Tool --> https://www.dcode.fr/caesar-cipher**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/56.jpeg?raw=true)

```
Flag --> inctfj{b3w4re_0f_cyB3R_THr3at5}
```

### Crack FDP

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/57.jpeg?raw=true)

- Download the **PDF**. 
- In this challenge we need to crack the pdf password and find the **flag**
- PDF Crack is a tool for recovering the pass for Encrypted PDF files. 
- Encrypted files means the metadata of the file was encrypted with some characters.

**It has some special features like:**

- Checks with the system password and also the user provided password.
- It can crack password by brute-forcing method only for character sets and only when we provide the maximum and minimum length of the password.
- Searches the password from the wordlist.
- Optimized search for owner-password when user-password is known.

#### Installation

```
$ sudo apt-get install pdfcrack
```

#### Usage

**Brute-forcing**

```
$ pdfcrack -f <file_name>
```

**Wordlist Cracking**

```
$ pdfcrack -f <file_name> -w <wordlist_file>
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/58.jpeg?raw=true)

```
Password --> diosayudameenelesut
```

- After decryption we get a password and now we will be able to open the pdf.
- We can see the **flag** inside the file.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/59.jpeg?raw=true)

```
Flag --> flag{1ae06a29a7abd6c07dba8976698f756b987f734d}
```

### S3cr3t

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/60.jpeg?raw=true)

- Download the **AUDIO** file.
- Using **Online decoder** we shall decode the **Morse Audio**.

**Online Morse Code Decoder --> https://morsecode.world/international/decoder/audio-decoder-adaptive.html**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/61.jpeg?raw=true)

```
Flag --> inctfj{M0RS3C0D3I5C001}
```

### Signal Messenger

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/62.jpeg?raw=true)

- Download the **AUDIO** file.
- Using **Online decoder** we shall decode the **Morse Audio**.

**Online Morse Code Decoder --> https://morsecode.world/international/decoder/audio-decoder-adaptive.html**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/63.jpeg?raw=true)

```
Flag --> flag{Y0UG0T7HES3CRE7ENC0DEDS7RING}
```

### Hidden Data

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/64.jpeg?raw=true)

- Download the Zip FIle.
- The zip file is **corrupted**.
- So edit the **Hex** chunks and then try to open the zip file.
- First start with the **Header--Magic Values** and then **Footer**.

**Online Tool --> https://hexed.it/**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/65.jpeg?raw=true)

- After editing the **Header and Footer** we will be able to open the Zip file.

```
Flag --> inctfj{GR3aT_m155i0n_4Cc0mpL15h3D}
```

### Corrupted File

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/66.jpeg?raw=true)

- Download the Zip FIle.
- The zip file is **corrupted**.
- So edit the **Hex** chunks and then try to open the zip file.
- First start with the **Header--Magic Values** and then **Footer**.

**Online Tool --> https://hexed.it/**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/67.jpeg?raw=true)

- Here we will be able to see the **Secret Information**.
- The given information in encrypted in **Base 64** format.
- SO we shall decrypt it back to the ASCII.

**Online Tool --> https://www.base64decode.org/**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/68.jpeg?raw=true)

```
Flag --> flag{9e360084196a092a15c5c44b54934bfc}
```

### Dig Deep

- Download the image given.
- If we try to open we wont be able to find anything.
- So we have to analyze the chunks.
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
$ binwalk -e 1.jpg
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/72.jpeg?raw=true)

- Here in the above image, we see that there is a **jpg image** and a **ZIP** in it and we see that, it is embedded within the jpg image file. 
- To extract it we can make use of a carving tool dd. 
- It can carve out data from specific offsets that are passed as arguments to the tool along the with the file that needs to be read. 

```
$ dd if=<filename> of=<filename> bs=1 skip=<offset>
```

- if = the file from which data has to be extracted is passed as an argument.
- of = has the name of the file that we give after extraction. 
- skip = is the offset of the file that has to be read.
- bs = i the byte skip argument that specifies the frequency of reading data from the given file.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/73.jpeg?raw=true)

- If we try to extract all files we will get three files. 

**PART - 1 --> Image 1**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/70.jpeg?raw=true)

**PART - 2 --> Text from the Zip FIle**

```
Here is the part2 202015ed269630d
```

**PART - 3 --> Image 2**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/71.jpeg?raw=true)

- If we combine **3 Parts** we can get the **Flag**.

```
Flag --> flag{7b560d81c0202015ed269630d2b8b1993d2e7788}
```

### Mysterious File

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/74.jpeg?raw=true)

- If we change the **Extension** of the file we will get the **Flag**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/75.jpeg?raw=true)

### Angry Steve

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/77.jpeg?raw=true)

- Lets Analyze te **Chunks**

**Online Tool --> https://hexed.it/**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/78.jpeg?raw=true)

```
Flag --> inctfj{string5_m4keth_fl4gs}
```

### Noice

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/79.jpeg?raw=true)

- Now we shall analyze the Audio using **Sonic Visualizer**.
- Sonic-Visualiser is also a GUI based tool. 
- It is similar to Audacity but a bit more powerful than it. 
- It is an application software for viewing and analysing the contents of audio files.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/80.jpeg?raw=true)

```
Flag --> inctfj{y0u_b3tt3r_l00k_cl0s3ly}
```

### Deeper..

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/81.jpeg?raw=true)

- Lets download the image.
- If we try to open we wont be able to find anything.
- So we have to analyze the chunks.
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
$ binwalk -e 1.jpg
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/76.jpg?raw=true)

- Here in the above image, we see that there is a **ZIP** in it and we see that, it is embedded within the jpg image file. 
- To extract it we can make use of a carving tool dd. 
- It can carve out data from specific offsets that are passed as arguments to the tool along the with the file that needs to be read. 

```
$ dd if=<filename> of=<filename> bs=1 skip=<offset>
```

- if = the file from which data has to be extracted is passed as an argument.
- of = has the name of the file that we give after extraction. 
- skip = is the offset of the file that has to be read.
- bs = i the byte skip argument that specifies the frequency of reading data from the given file.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/82.jpeg?raw=true)

- Now we open the **ZIP** file then we will be able to find the **Audio**.
- Next step is to analyze the Audio.

**Online Tool --> https://databorder.com/transfer/morse-sound-receiver/**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/83.jpeg?raw=true)

```
Flag --> inctf{H34R_W1TH_Y0UR_3Y35}
```

### Winter Sport

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/84.jpeg?raw=true)

- After downloading the pdf file we wont be able to find anything.
- Hence we have to analyze the embeded data in it.
- Peepdf is a Python based tool to explore PDF files in order to find out if the file can be harmful or not. 
- The aim of this tool is to provide all the necessary components that a security researcher could need in a PDF analysis without using 3 or 4 tools to make all the tasks. 
- With peepdf it's possible to see all the objects in the document showing the suspicious elements, supports all the most used filters and encodings, it can parse different versions of a file, object streams and encrypted files.

#### Usage

```
$ ./peepdf.py -i pdffile.pdf
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/85.jpeg?raw=true)

- As we can see there is an embedded file in the pdf.
- So now we need to extract the embedded file using the stream command

```
$ PDF> stream 8 > <Filename>
$ xdg-open <Filename>

--> File Name --> f1

$ PDF> stream 8 > f1
$ xdg-open f1
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/86.jpeg?raw=true)

- After opening the zip file we shall get a pdf.
- If we open the **PDF** then we will be able to find that there is something hidden in the **whitespace**.
- We shall understand that its **White Space Steganography**.
- Reference --> **https://wiki.bi0s.in/steganography/stegsnow/** 
- By refering the **wiki.bi0s.in** we can get to know that there is a tool named Stegsnow which conceals messages in text files by appending tabs and whitespaces at the end of lines.
- Download the txt file which has to be decrypted.

#### Installation

```
$ sudo apt install stegsnow
```

#### Decryption

```
$ stegsnow -C <Filename>

--> Filename = omg.pdf

$ stegsnow -C omg.pdf
```

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/87.jpeg?raw=true)

```
Flag --> inctf{w3lcom3_t0_7h3_w0rld_0f_whit3sp4c3}
```

### Hidden Message

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/88.jpeg?raw=true)

- We are provided with the **Python Script** and **JPEG Image**

```
--> Python Script 

import string
import base64

def encode(x):
    return x.encode("hex") 

if _name=="main_":
	print("63486c306147397561584e6d6457343d")
	print("decode this to get the pass")
	encoded_data = encode(base64.b64encode(""))
	print(encoded_data)
```

- We have to debug it to make it excute to get the necessary output.
- First Change the **encode()** function to **decode()**
- Then in order to pass the **Parameter** to the decode function it should be in **ASCII** format.
- But we have **Hex** here.
- So we have to convert the given hex to ASCII format.

**Online Tool --> https://www.rapidtables.com/convert/number/hex-to-ascii.html**

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/89.jpeg?raw=true)

- After several debuging we shall get the final script.

```
import string
import base64

def decode(x):
    return x.decode('utf8') 

if _name=="main_":
	print("63486c306147397561584e6d6457343d")
	print("decode this to get the pass")
	encoded_data = decode(base64.b64decode("cHl0aG9uaXNmdW4="))
	print(encoded_data)
```

- Next Step is to run the script.

```
--> pythonisfun
```

- Steghide is used to embed and extract secret messages in images. 
- It supports all the general formats of images like .png, .jpg etc.

#### Installation

```
$ sudo apt install steghide
```

#### Usage

```
$ steghide extract -sf <Filename>
Enter passphrase : ********
wrote extracted data to "<Filename>.txt".
```

- We have to enter the password which we got from the **Python Script**.

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/90.jpeg?raw=true)


### Mariana_Trench_Deep

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/125.jpeg?raw=true)

- `Download` the given files.
- But we could'nt find anything in the Audio and Video Files.
- After a long analysis we shall understand that the `Txt` file which was given was the only useful file.
- `Ook. Ook! Ook?` was the hint given there. 
- `Ook` is a rewriting of the `BrainFuck`, an already `obfuscated esoteric programming language`, designed to be `writable` and `readable` by `orang-utans` (which would communicate by pronouncing the `onomatopoeia` 'ook, ook'). 

```
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook. Ook? Ook. Ook. Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook? Ook. Ook? Ook. Ook? Ook. Ook! Ook! Ook? Ook! Ook. Ook? Ook. Ook? Ook. Ook? Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook? Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook? Ook. Ook. Ook. Ook. Ook! Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook! Ook. Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook? Ook. Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook. Ook? Ook. Ook! Ook! Ook! Ook. Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook! Ook. Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook! Ook. Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook.
```

- We have to `Decode` it now.
- Use `Online Tool` --> https://www.dcode.fr/ook-language

![Bi0s](https://github.com/abhishekabi2002/Bi0s/blob/master/Forensics/Assets/126.jpeg?raw=true)

```
Flag --> inctfj{l4ngu4g35_d0nt_m4k3_s3ns3}
```


#### Reference 1 --> https://wiki.bi0s.in/steganography/intro/

#### Reference 2 --> https://wiki.bi0s.in/forensics/roadmap/
