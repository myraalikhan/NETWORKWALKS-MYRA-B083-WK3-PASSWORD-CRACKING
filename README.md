# NETWORKWALKS-MYRA-B083-WK3-PASSWORD-CRACKING
Week 3 — Networkwalks Cybersecurity Internship. Cracking a password-protected PDF two ways: John the Ripper (CLI) and the Networkwalks web tools. Educational lab.

Project Overview

This project recovers the password of a protected PDF (My Locked PDF1.pdf) using two different methods that reach the same result:

Module W3-PM1 — John the Ripper: extract the PDF hash, then crack it with John the Ripper from the command line.
Module W3-PM2 — Networkwalks Tools: extract and crack the same hash using the browser-based Networkwalks Hash Calculator and Password Cracker.

Both methods follow the same logic — pull a crackable hash out of the file, then run a wordlist against it until a password matches.

🛠️ Tools Used
Tool	Role
John the Ripper (1.9.0-jumbo)	Command-line password cracker
pdf2john	Extracts the $pdf$ hash from a PDF
Networkwalks Hash Calculator	Browser tool to extract the PDF hash
Networkwalks Password Cracker	Browser tool to run a dictionary attack
rockyou.txt	Large wordlist (~14 million passwords)
🧩 Part 1 — Networkwalks Web Tools (W3-PM2)
Opened the Hash Calculator, uploaded the PDF, and copied the $pdf$ hash.
Pasted it into the Password Cracker and ran the built-in 100-password wordlist.
The tool tried each word and stopped on a match.

📸 Screenshots: hash_calculator.png, password_cracker.png

🧩 Part 2 — John the Ripper (W3-PM1)
Downloaded the John the Ripper jumbo build and located john in the run folder.
Extracted the PDF hash to a file:
bash
   pdf2john locked.pdf > hash1.txt
Cracked it:
bash
   john hash1.txt
   john --show hash1.txt

📸 Screenshots: hash1_txt.png, john_show.png

✅ Result

Opening the PDF with the recovered password revealed the "Congratulations — you captured your 1st flag" page, confirming the crack.

📸 Screenshot: flag.png



