# stug-reference

#### Category: D-CTF 2020 Online, Steganography
#### Difficulty: Entry Level
#### Points: 10

## Description

Do you have your own stug pass hidden within?

Flag format: ctf{sha256}

The challenge was proposed by BIT SENTINEL.

## MITRE ATT&CK
### T1204 - User Execution
### T1027 - Obfuscated Files or Information

## CWE
### CWE-201 - Insertion of Sensitive Information Into Sent Data
### CWE-312 - Cleartext Storage of Sensitive Information
### CWE-319 - Cleartext Transmission of Sensitive Information

## Walkthrough

This challenge provides us with the "stug.jpg" file on which we have to perform steganography techniques in order to find the flag.


<img width="921" height="600" alt="Screenshot from 2026-09-10 12-33-38" src="https://github.com/user-attachments/assets/784018f5-b657-4045-9b41-43d8f0fea452" />


First step is to *file stug.jpg* in order to find out what type of file this is. Next step is to use *exiftool* a tool that provides metadata information on the file. Using the command *exiftool stug.jpg* we are given information on file size, image size, modification and access times, extension type, encoding type and other information.


<img width="924" height="204" alt="Screenshot from 2026-09-10 12-46-13" src="https://github.com/user-attachments/assets/93e9bc67-a496-4421-a8c5-135706a17b50" />


*steghide* is a steganography tool used to encrypt information within files but we are using it to do the opposite, so decrypt hidden information within the hidden file. With the command *steghide extract -sf stug.jpg* we are specifying that we want to extract from the given file. Next we are given a *Enter passphrase* prompt and I entered "stug" as the password, getting back a *flag.txt* file in the same directory. *cat flag.txt* shows the flag in clear text.

References and Links:
https://attack.mitre.org/techniques/T1204/
https://attack.mitre.org/techniques/T1027/
https://cwe.mitre.org/data/definitions/201.html
https://cwe.mitre.org/data/definitions/312.html
https://cwe.mitre.org/data/definitions/319.html
https://exiftool.org/
https://steghide.com/
