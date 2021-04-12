## Forensics

### 1597

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/1.jpeg?raw=true)

- Clone the Repository http://git.ritsec.club:7000/1597.git/
- We can see list the branches using `git branch` command (the asterisk denotes the current branch).
- Now lets view the files in the branch.
- There is a `flag.txt` which has the `flag`.

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/2.png?raw=true)

```
Flag --> RS{git_is_just_a_tre3_with_lots_of_branches}
```

### Blob

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/5.png?raw=true)

- Clone the Repository http://git.ritsec.club:7000/blob.git/
- From the challenge name we shall understand that this challenge is related to `blob`.
- Blob is an abbreviation for `Binary large object`.
- A `blob` in `Git` will contain the same exact data as a file.
- It's just that a blob is stored in the Git object database, and a file is stored on the filesystem. 
- A “blob” is used to store file data- it is generally a file.
- If we take a look at our .git directory we can see that the .git/objects directory has some subdirectories and files.
- So lets navigate to .`git/objects` directory.
- It contains a list of all files in our project with a pointer to the blob object assigned to them (this is how git associates your files with their blob objects).
- Notice that every directory name is two characters long. 
- Git generates a 40- character checksum `(SHA-1) hash` for every object and the first two characters of that checksum are used as the directory name and other 38 as a file (object) name.
- The first kind of object that git creates when we commit some files are blob objects.
-  Let's use the command `git cat-file` to show the contents of the hashed files in `.git/objects`.
-  `git cat-file` provides content or type and size information for repository objects.
-  The tree object contains one line per file or subdirectory, with each line giving file permissions, object type, object hash, and filename. 
-  An object type is usually one of `blob` for a file or `tree` for a subdirectory.
-  Now use `-p` to view the object contents.
-  In our case the third directory `d0` contains the flag. 

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/4.png?raw=true)

```
Flag --> RS{refs_can_b3_secret_too}
```

## Inception CTF

### Dream 1

- Extract the Zip.
- `InceptionCTF` contains `Reality.7z` .
- Extract it to get `Reality` folder.
- Two files will be extracted.
- Suspicious.txt and `Vanchaze.7z`.
- Suspicious.txt contains reversed file.
- Reversing the contents will give the flag.

```
InceptionCTF --> Reality --> Suspicious.txt

Flag --> RITSEC{Dreamland}
```

#### Dream 2

- Extracting `Vanchase.7z` will give `kidnap.txt`.
- It contains Hex code and decoding it will give the flag.

```
InceptionCTF --> Reality --> Vanchase --> kidnap.txt

Hex code : "52 49 54 53 45 43 7b 57 61 74 65 72 55 6e 64 65 72 54 68 65 42 72 69 64 67 65 7d".

Flag --> RITSEC{WaterUnderTheBridge} 
``` 

#### Dream 3

- Extracting `TheHotel.7z` will give `ThePointman.txt`.
- It contains `Base64` encoded text and decoding it will give the flag.

```
InceptionCTF --> Reality --> Vanchase --> THEHotel --> ThePointman.txt 
 
 Flag --> RITSEC{F@!!ingElev@tor}
```

#### Dream 4

- Extracting `Snowfortress.7z` will give `Passwordpath.exe`.

```
InceptionCTF  --> Reality --> Vanchase --> THEHotel --> Snowfortress --> Passwordpath.exe
```

- Now `cat` the Passwordpath.exe and we shall see the `Java Script code`.
- Decoding the `JS` gives `Morsecode`.
- Decoding the `Morse code` gives the flag.

```
Flag --> RITSEC{DIVERSION}
```

#### Dream 5

- Extracting `Limbo.7z` will give `Inception.jpg`.

```
 --> Reality --> Vanchase --> THEHotel --> Snowfortress --> Limbo --> Inception.jpg
```

- Doing `strings` in `Inception.jpg` gives Base64 encoded text `UklUU0VDezUyODQ5MX0g`.
- Decode it to get the flag.

```
Flag --> RITSEC{528491}
```

### Birdthief : FYSA

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/6.png?raw=true)

- Trying `Binwalk` in the given `PDF` shows many files.
- Extracting them gives image files.
- One of the images has the flag.
- Alternative - https://www.extractpdf.com/

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/9.png?raw=true)

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/10.png?raw=true)

![Bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/7.jpg?raw=true)

```
Flag --> RS{Make_sure_t0_read_the_briefing}
```

### Parcel

![bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/8.png?raw=true)

- `File format` is not known.
- So lets see the file type with `file` command.
- We shall see that the file format is `gzip`.

![bi0s](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/11.png?raw=true)

- So lets rename the file to `.gzip`.
- Now if we extract it we shall see that there is an file inside with unknown format.
- Just changing the file format to `txt` will open it.

[Txt](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/Parcel.txt)
[GZ File](https://github.com/a3X3k/Bi0s/blob/master/CTFs/RITSEC21/Assets/Parcel.gz)

- In txt file we shall see the Base64 encoded texts.
- [Decoding](https://www.base64decode.org/) it will give the `PNG` Image header.
- So decoding all texts will give multiple images.
- Use [Online Tool](https://base64.guru/converter/decode/image/png) to extract the images directly. 
- Concatenating all images will yeild the flage.

```
Flag --> RS{Im_doing_a_v1rtual_puzzl3}
```

