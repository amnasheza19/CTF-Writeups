# 🏁 PicoCTF Writeup — Corrupted File

## 🏷 Category:

- Digital Forensics
- Level Easy

## 🎯 Objective:

The objective of this challenge was to analyze a corrupted file and recover the hidden flag by repairing the file structure.

The downloaded file appeared damaged or unreadable, indicating that the file header or format had been altered.

## 🛠 Tools Used:

- Hex Editor
- File signature knowledge (JPEG header)
- Online file converter (to JPG/JPEG)

## 🧠 Steps / Method:

### Step 1: Download the file

The provided file was downloaded from the challenge link.
When attempting to open it normally, the file would not display correctly, indicating corruption.

### Step 2: Inspect file in hex editor

The file was opened using a hex editor to analyze its raw binary structure.

While examining the file, it became clear that the file signature (header) did not match a valid image format.

### Step 3: Identify correct file format

By analyzing the file structure and challenge hints, it was suspected that the file should be a JPEG image.

A valid JPEG file begins with the hexadecimal header:

```
FF D8 FF
```

However, this header was missing or altered in the corrupted file.

### Step 4: Repair the file header

Using the hex editor:

* The incorrect header bytes were edited
* Replaced with correct JPEG header format
* File structure adjusted to match JPEG standards

After correcting the header, the file was exported/saved.

### Step 5: Convert repaired file

The repaired file was then uploaded to an online converter to ensure proper JPEG formatting.

Once converted/opened successfully, the hidden flag became visible within the image.

## 🏳 Flag:

picoCTF{xxxxxxxxxxxxxxxx} [REDACTED FOR ETHICAL REASONS]

## 📸Screenshot
<img width="344" height="239" alt="image" src="https://github.com/user-attachments/assets/102ecb56-d69d-4440-9fcd-5ffbbb519892" />

## 📚 What I Learned:

* How file signatures determine file types
* Importance of headers in digital files
* How hex editors are used in digital forensics
* Techniques to repair corrupted files
* Real-world relevance of file recovery in investigations

## 🔐 Real-World Relevance:

Digital forensics investigators often encounter corrupted or manipulated files.
By analyzing file headers and binary structure, investigators can:

* Recover damaged evidence
* Identify real file types
* Restore hidden or deleted data

This challenge demonstrated how file header manipulation can hide important information and how forensic techniques can recover it.
