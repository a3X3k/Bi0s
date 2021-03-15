# Forensics
### Barcode Scanner

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/1.png?raw=true)
 - Download the Image given.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/2.jpg?raw=true)

- Use Stegsolve and invert the colors.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/3.png?raw=true)

- This will be the final image which u get.
- Then use `zbarimg` tool to extract text from the `Barcode`.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/4.png?raw=true)

```sh
Flag --> vishwaCTF{5oo_3ASy}
```

### Peace

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/5.png?raw=true)

- Download the `rar` file given.
- Crack the `rar` `password` using `rar2john`.

```
rar2john morse.rar > ki.txt
```

- `unrar` the `rar` file using password `india`

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/6.png?raw=true)

- We will get a `morse` `encrypted` `audio` file.
- Use `morse decoder` to `decode` the content.

```sh
76 69 73 68 77 61 63 74 66 7B 37 68 33 79 5F 34 72 45 5F 46 30 72 33 66 65 37 31 6E 67 7D
```

- We will get the `hexadecimal` values.
- Decode it to get the `ASCII` text.

```sh
Flag --> vishwactf{7h3y_4rE_F0r3fe71ng}
```

### Sherlock

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/7.png?raw=true)

- Download the Image File given.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/8.jpg?raw=true)

- From the `Magic Numbers` we shall find that the given image is actually a `png` format.
- But we get it as `jpg`.
- So `change` its `format` to `png`.
- Use `zsteg` tool to extract the hidden information.

```sh
zsteg -a decode.png
```

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/9.png?raw=true)

```sh
Flag --> vishwaCTF{@w3s0Me_sh3Rl0cK_H0m3s}
```

### Comments

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/10.png?raw=true)

- Download the given `docx` file.
- Use `cat` command with `pipe` and `grep` to see the `contents`.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/12.png?raw=true)

```sh
Flag --> vishwaCTF{comm3nts_@r3_g00d}
```

### Bubblegum

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/13.png?raw=true)

- Download the given `Audio` File.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/14.png?raw=true)

- Open the given audio file in `audacity`.
- Upon analysing it, we find this `0.55-1.07` which could be a hint.
- Searched for the given audio in [youtube](https://youtu.be/5x441jo1-sg ) and found out that the lyrics of `0.55-1.07` portion of this video is the flag:

```sh
Flag --> vishwaCTF{oh bubble gum dear im yours forever i would never let them take your bubblegum away}
```

### Remember

- Download the files given.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/16.png?raw=true)

- Download the files given.
- Using `registry viewer` `analyse` the file2.
- Go through the `accounts` folder.
- In key `properties` tab we can see the `last password updated time`.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/19.png?raw=true)

```sh
Flag --> vishwaCTF{thursday_january_10_08_24_36_2013}
```

### Recovery

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/.png?raw=true)

- `Download` the `files` given.
- Using `registry viewer` `analyse` the file2.
- Go through the `accounts` folder.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/21.png?raw=true)

- Under `users` we can see `shreyas account` details but we will not able see the `password hash` without uploading the `syskey` file.

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/20.png?raw=true)

- The `file1` is the `syskey` for the `file2` after uploading the `syskey` in `registry viewer` we will able to see the the `hash key` and more details in `key properties`.
- So using `samdump2` dump all the `username` and `password` `hash`.

```
samdump2 file1 file2 > hashes.txt
```

![](https://github.com/abhishekabi2002/Bi0s/blob/master/Vishwa_Ctf/Assets/23.png?raw=true)

