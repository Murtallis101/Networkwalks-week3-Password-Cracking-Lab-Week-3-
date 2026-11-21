Networkwalks-week3-password-cracking-lab Week 3 

Cybersecurity Internship Project: Authorized PDF hash extraction and dictionary-based password recovery using John the Ripper (Kali Linux) and NetworkWalks web security utilities.
Password Cracking & Hash Recovery Lab (Week 3 Project)
This repository documents the completion of Week 3 (Modules W3-PM1 and W3-PM2) for the NetworkWalks Cybersecurity Internship. The lab demonstrates authorized cryptographic hash extraction from password-protected PDF files and evaluates password resilience through offline dictionary attacks, comparing Linux command-line tools (John the Ripper on Kali Linux) with NetworkWalks' browser-based security utilities.

Tools & Environment Used
•	Operating Systems: Kali Linux (Oracle VirtualBox VM) & Windows 11 Host
•	Command-Line Utilities: pdf2john, John the Ripper
•	Web Security Utilities:
o	NetworkWalks Hash Calculator
o	NetworkWalks Password Cracker
o	NetworkWalks Lab Portal
________________________________________
Methodology & Execution
Module 1: CLI Hash Extraction & Dictionary Attack in Kali Linux (W3-PM1)
Target files (My Locked PDF1.pdf, My Locked PDF2.pdf, and My Locked PDF3.pdf) were processed locally inside the Kali Linux environment to extract their embedded cryptographic hashes and recover the plain-text credentials.
# Navigate to target directory
cd ~/Downloads

# Extract cryptographic hashes from locked PDFs
pdf2john "My Locked PDF1.pdf" > hash1.txt
pdf2john "My Locked PDF2.pdf" > hash2.txt
pdf2john "My Locked PDF3.pdf" > hash3.txt



# Execute dictionary-based password recovery
john hash1.txt
john hash2.txt
john hash3.txt
john --show hash1.txt
john --show hash2.txt
john --show hash3.txt 
Module 2: Browser-Based Hash Extraction & Recovery (W3-PM2)
Target file My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf was analyzed on the Windows host using the NetworkWalks web suite:
1.	Uploaded the encrypted PDF to the NetworkWalks Hash Calculator (https://networkwalks.com/hash-calculator/) to isolate the full $pdf$... cryptographic hash string.
2.	Submitted the extracted hash to the NetworkWalks Password Cracker (https://networkwalks.com/password-cracker/) to run an automated wordlist recovery attack.
3.	Verified the recovered credential by unlocking the PDF and capturing the verification flag.
________________________________________
Results Summary
Module	Target File	Tool / Platform	Status
W3-PM1	My Locked PDF1.pdf	pdf2john + John the Ripper (Kali Linux)	Cracked & Flag Verified
W3-PM1	My Locked PDF2.pdf	pdf2john + John the Ripper (Kali Linux)	Cracked & Flag Verified
W3-PM1	My Locked PDF3.pdf	pdf2john + John the Ripper (Kali Linux)	Cracked & Flag Verified
W3-PM2	My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf	NetworkWalks Hash Calculator & Password Cracker	Cracked & Flag Verified
(Note: Plain-text passwords, raw hash strings, and captured flags are intentionally redacted from this public repository to maintain lab integrity and follow operational security best practices.)



Evidence
1. Kali Linux Hash Extraction & John the Ripper Execution (W3-PM1)
 
2. Kali Linux Flag Verification (W3-PM1)
 3. NetworkWalks Hash Calculator Output (`W3-PM2`)   
4. NetworkWalks Password Cracker & Flag Verification (W3-PM2)
•	
 
________________________________________
Authorized Permission & Ethical Disclaimer
All password-cracking exercises, hash extractions, and verification tests documented in this repository were conducted strictly within an isolated lab environment on designated training files provided by NetworkWalks Academy under explicit written authorization for educational and internship evaluation purposes. No external, unauthorized, or live production systems were targeted.
________________________________________
Author
•	Name: Murtallis Marcus Roux
•	Program / Batch: NetworkWalks Cybersecurity Internship (Batch 084)
•	Module: Week 3 — Password Cracking & Hash Recovery (W3-PM1 & W3-PM2)
•	LinkedIn: [linkedin.com/in/murtallis-roux-02b030270]

