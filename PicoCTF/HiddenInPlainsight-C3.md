# 🏁 PicoCTF Writeup — Hidden in Plain Sight

## 🏷 Category:

- Digital Forensics / Steganography
- Level Easy
  
## 🎯 Objective:

The objective of this challenge was to analyze an image file and uncover the hidden flag embedded within it. The challenge hinted that important information could be found within the file’s metadata.

## 🛠 Tools Used:

* Online metadata viewer : metadata2go
* Base64 decoder
* PicoCTF Webshell
* Steghide tool (steganography extraction)
* Linux terminal commands

## 🧠 Steps / Method:

### Step 1: Download and inspect the image

The provided image was downloaded and opened.
At first glance, it appeared to be an ordinary image with no visible flag.

The challenge hint suggested checking metadata, indicating that hidden information might be stored inside the file properties.

### Step 2: Analyze metadata

The image was uploaded to an online metadata viewer (metadata2go) to inspect hidden metadata.

While reviewing metadata fields, a suspicious encoded string was found inside the comments section:

```
steghide:cEF6endvcmQ=
```

### Step 3: Decode Base64 string

The encoded string `cEF6endvcmQ=` was copied and decoded using a Base64 decoder.

After decoding, it revealed a password required to extract hidden data from the image.

### Step 4: Use PicoCTF webshell

Opened the PicoCTF webshell and downloaded the image using:

```
wget <image_link>
```

### Step 5: Use steghide to extract hidden data

Steghide is a tool used to hide and extract data from images.

Command used:

```
steghide --extract -sf img.jpg
```

When prompted for a passphrase, the decoded password from metadata was entered.

### Step 6: Retrieve hidden file

After entering the correct passphrase, a hidden file was extracted (flag.txt).

Used commands:

```
ls
cat flag.txt
```

The flag was successfully displayed.

## 🏳 Flag:
picoCTF{xxxxxxxxxxxxxxxx} [REDACTED FOR ETHICAL REASONS]

## 📸 Screenshots:
<img width="747" height="707" alt="image" src="https://github.com/user-attachments/assets/41845b5f-5677-47a4-8074-3c6c03d0c52d" />
<img width="342" height="241" alt="image" src="https://github.com/user-attachments/assets/5213274f-b832-435f-b357-b68e375a9b5c" />

## 📚 What I Learned:

* How metadata can reveal hidden clues
* Base64 encoding and decoding techniques
* Basics of steganography
* Using steghide to extract hidden files
* Importance of investigating files thoroughly in digital forensics

## 🔐 Real-World Relevance:

Attackers often hide sensitive data inside images using steganography.
Digital forensics investigators must analyze:

* File metadata
* Encoded strings
* Hidden embedded files

This challenge demonstrated how hidden information can exist in seemingly harmless files and how forensic tools can uncover it.
