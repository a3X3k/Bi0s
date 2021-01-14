## INTRODUCTION
&nbsp;
| Challenge No | Challenge Name |
| ------ | ------ |
| **1** | Finding Flags |
| **2** | Great Snakes |
| **3** | Network Attacks |
&nbsp;
### Finding Flags

- As mentioned just paste the flag **crypto{y0ur_first_fl4g}** as an answer.

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/4.jpeg?raw=true)

##### Flag = crypto{y0ur_first_fl4g}
&nbsp;
### Great Snakes

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/3.jpeg?raw=true)

- Just we need to run the python program to get the flag and the python version is python3 which is mentioned in the challenge. 

```sh
$ python3 filename
$ File Name = 1.py
$ python3 1.py
```

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/1.jpeg?raw=true)

##### Flag = crypto{z3n_0f_pyth0n}
&nbsp;

### Network Attacks

- Download the file whihc is mentioned in the challenge or connect using netcat.
```sh 
$ nc socket.cryptohack.org 11112
```
- As mentioned change the JSON object with the key buy and value flag in **line 31**.
&nbsp;
![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/9.jpeg?raw=true)

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/10.jpeg?raw=true)

- Now run the Program.

```sh
$ python3 filename
$ File Name = 2.py
$ python3 2.py
```

##### Flag = crypto{sh0pp1ng_f0r_fl4g5}
&nbsp;

## GENERAL
#### Encoding
&nbsp;

| Challenge No | Challenge Name |
| ------ | ------ |
| **1** | ASCII |
| **2** | Hex |
| **3** | Base64 |
| **4** | Bytes and Big Integers |
&nbsp;

### ASCII 

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/7.jpeg?raw=true)
- Just convert the ASCII into Characters either using ASCII table or Online Tool https://www.dcode.fr/ascii-code

##### Flag = crypto{ASCII_pr1nt4bl3}
&nbsp;

### Hex

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/8.jpeg?raw=true)

- As we know, a byte contains 8 bits. Therefore, we need two hexadecimal digits to create one byte.
- First of all, we'll convert each hexadecimal digit into binary equivalent separately.
- And then, we need to concatenate the two four bit-segments to get the byte equivalent
- We need to check if the length of the hexadecimal String is an even number. 
- This is because a hexadecimal String with odd length will result in incorrect byte representation.
- Now, we'll iterate through the array and convert each hexadecimal pair to a byte.
- Use online tool https://www.scadacore.com/tools/programming-calculators/online-hex-converter/ to decode it.

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/11.jpeg?raw=true)

##### Flag = crypto{You_will_be_working_with_hex_strings_a_lot}
&nbsp;

### Base64

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/12.jpeg?raw=true)

- First convert Hexadecimal to Bytes using Online Tool https://www.alterlinks.com/byte-converter/byte-converter.php

```sh
$ Hex - 72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf
$ Bytes - 564501339853374515179229284425
```

- Then convert Bytes to base64

```sh
$ Bytes - 564501339853374515179229284425
$ Base64 - crypto/Base+64+Encoding+is+Web+Safe/
```

- Use https://cryptii.com/pipes/binary-to-base64 Online Tool to directly convert Hex to Base64.

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/13.jpeg?raw=true)

##### Flag - crypto/Base+64+Encoding+is+Web+Safe/
&nbsp;

### Bytes and Big Integers

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/16.jpeg?raw=true)

- Simply convert long to byte with the respectively function to get the flag.

```sh
from Crypto.Util.number import bytes_to_long
from Crypto.Util.number import long_to_bytes
data = 11515195063862318899931685488813747395775516287289682636499965282714637259206269
bytes = long_to_bytes(data)
print(bytes)
```

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/15.jpeg?raw=true)

```sh
$ python3 filename
$ File Name = 3.py
$ python3 3.py
```

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/14.jpeg?raw=true)

##### Flag - crypto{3nc0d1n6_4ll_7h3_w4y_d0wn}
&nbsp;

### Bytes and Big Integers

![Drag Racing](https://github.com/abhishekabi2002/Bi0s/blob/master/Cryptography/Assets/17.jpeg?raw=true)

- Convert Char to Decimal.
- Convert Decimal to Binary.
- Now XOR with decimal 13 whose Binary equivalent is 00001101

&nbsp;
#### XOR Table
&nbsp;
| A | B | A XOR B |
| - | - | - | 
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 | 
| 1 | 1 | 0 |

&nbsp;

```sh

Original String - label
Characters Of String To Decimal - 108 097 098 101 108
Decimal To Binary - 01101100 01100001 01100010 01100101 01101100

## XOR OPERATION

01101100
00001101
--------
01100001
--------

01100001
00001101
--------
01101100
--------

01100010
00001101
--------
01101111
--------

01100101
00001101
--------
01101000
--------

01101100
00001101
--------
01100001
--------

Binary after Xoring with (13) 00001101 --> 01100001 01101100 01101111 01101000 01100001

Binary To Decimal - 097 108 111 104 097

Decimal to ASCIi - aloha
```

- Use https://www.branah.com/ascii-converter to convert using Online Tool.

##### Flag - crypto{aloha}
