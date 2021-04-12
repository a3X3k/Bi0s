# Forensics

## Inception CTF

#### Dream 1

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

## Birdthief : FYSA

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

## Parcel

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

