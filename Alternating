# Alternating

#### Category: DefCamp 2024 Quals, Forensics
#### Difficulty: Entry Level
#### Points: 500

## Description

The challenge provides us with a "Flag.rar" file. First step is to run *file* and *exiftool* to find information on the file type and metadata of the structure.

Next step is to install 7zip and running the *7z x* command, where x extracts files with full paths. We do get a "flag.txt:real-flag.txt" file but we cannot read it. We know of the existence of a file that we did not see with *exiftool*.

<img width="780" height="586" alt="Screenshot from 2026-09-12 00-32-44" src="https://github.com/user-attachments/assets/e07d1c5c-2f65-4493-8850-02898fb9553e" />

*7z l*, the command for listing the contents of the archive, identifies an alternate stream which indicates hidden data with in a file. we refer here to the Alternate Data Stream, a feature of the NTFS in Windows that allows multiple streams of data to be stored within a single file without changing its visible size or primary content.

<img width="793" height="604" alt="Screenshot from 2026-09-12 09-43-19" src="https://github.com/user-attachments/assets/07367b27-9b45-481d-bfe2-df11f548b7be" />

With the help of Wine and WinRAR, we run winrar64.exe with Wine and specify the challenge folder. *ls* in the directory will show all the new contents within. Again we use Wine on the newly added WinRAR.exe file and open the WinRAR application in the directory.

<img width="1332" height="752" alt="Screenshot from 2026-09-12 10-01-51" src="https://github.com/user-attachments/assets/7288d2ea-cc28-498e-9261-2c5ae3b1ae33" />

Last step is to right click or SUPER+R on the Flag.rar file, extracting without confirmation. Now we see an extracted file from that .rar with a size of 74 so we can confirm there is contents within the file. Opening the file reveals the flag.

<img width="1332" height="752" alt="Screenshot from 2026-09-12 10-06-38" src="https://github.com/user-attachments/assets/b05d2b75-90f9-40ec-bfad-8e9538596140" />

References and Links:
https://app.cyber-edu.co/challenges/9d17e0b4-9949-4062-979d-1a45deb3db17?tenant=cyberedu
https://community.owasp.org/attacks/Windows_alternate_data_stream
https://www.win-rar.com/download.html?L=0
https://www.winehq.org/
