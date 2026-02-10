# 🏁 PicoCTF Writeup — RiddleRegistry (Hidden Confidential Document)

## 🏷 Category:
- Digital Forensics
- Level - Easy

## 🎯 Objective:
The objective of this challenge was to analyze a provided PDF file and uncover the hidden flag within its metadata.

The challenge description indicated that the PDF contained garbled or meaningless content, suggesting that the actual flag was not visible directly in the document but hidden in the file’s metadata.

## 🛠 Tools Used:
- PDF metadata viwer:  Metadata2go
- Decoder: Base64Decode

## 🧠 Steps / Method:

### Step 1: Download the PDF file

The provided link in the challenge contained a downloadable PDF named “Hidden Confidential Document”.

After downloading the file, opening it normally showed only random or unreadable text.
This indicated that the visible content was not important.

### Step 2: Understand the hint

### Step 3: Extract metadata using PDF Metadata viwer

Used the Metadata2go to extract the metadata, the metadata of the author stood out. Copied it.

### Step 4: Decode the Metadata

Inserted the copied Metadata onto a decoding tool, Base64decode. click decode and then found the hidden flag.

## 🏳 Flag:

picoCTF{xxxxxxxxxxxxxxxx} [REDACTED FOR ETHICAL REASONS]

## 📸 Screenshots:

<img width="355" height="250" alt="image" src="https://github.com/user-attachments/assets/c1904e0e-1644-4d1f-946b-2e1e4d62af85" />

## 📚 What I Learned:

- Files can contain hidden metadata with sensitive information
- Metadata analysis is an important digital forensics technique
- Attackers or developers may accidentally leave confidential data inside files

## 🔐 Real-World Relevance:

In real-world cybersecurity and digital forensics investigations, metadata analysis helps investigators:

- Trace document origins
- Identify authors
- Discover hidden information
- Detect data leaks

This challenge demonstrated how easily sensitive data can be exposed through file metadata.
