# WEEK 3 – PASSWORD CRACKING LABS (NetworkWalks Cybersecurity Internship)

This repo documents the Week 3 project modules for the NetworkWalks internship, covering two approaches to password cracking: the classic command-line tool John the Ripper (JTR), and the browser-based NetworkWalks (NW) Password Cracker tool.
 
# 📌 W3-PM1: Password Cracking with John the Ripper (JTR)

# Objective

Crack a password-protected file's hash using John the Ripper, a widely-used offline password cracking tool built into Kali Linux.

# Tools Used

online hashcrack (to extract a crackable hash from a password-protected PDF)

John the Ripper ( john )

Wordlist: JTR_default_password.txt: /rockyou.txt / fasttrack.txt 


# Methodology
1.	Extracted the hash from the target file using pdf2john.pl target.pdf > hash.txt .
2.	Ran John the Ripper against the hash: john -wordlist=<wordlist>.txt hash.txt .
3.	Retrieved the cracked password using john -show hash.txt .

# Result
 	Add your cracked password / screenshot here.
<img width="1162" height="881" alt="image" src="https://github.com/user-attachments/assets/078b3bab-fed2-450a-ac21-de43efe559be" />

pdf1-01-hash-extraction.png







# Key Takeaways

JTR automatically detects the hash type and tries wordlist entries at high speed.
 
 Wordlist choice matters — smaller, frequency sorted lists (fasttrack, JTR default) often crack common passwords faster than brute-forcing a massive list like rockyou.
 
# 📌 W3-PM2: Password Cracking with NW (NetworkWalks) Tools

# Objective

Perform the same style of dictionary attack using NetworkWalks' own browser-based tools, to compare workflow and results against JTR.

# Tools Used

NetworkWalks Hash Calculator (extracts the $pdf$... hash)

NetworkWalks Password Cracker (Dictionary Attack Lab)
 	
Wordlists tested: built-in 100-password list → JTR_default_password.txt → 

Methodology

1.	Extracted the $pdf$ hash using the NetworkWalks Hash Calculator.

2.	Pasted the hash into the Password Cracker tool and ran the built-in 100-word list — no match.

3.	Uploaded progressively larger wordlists (fasttrack.txt, then JTR_default_password.txt) until a match was found.


# Result
	Add your cracked password / screenshot here.

# Key Takeaways

Starting with a small, high-probability wordlist before escalating to a massive one (rockyou) saves significant cracking time.

The NW tool mirrors JTR's dictionary-attack logic in a simplified, browser-based interface — useful for understanding the concept before working with the real CLI tool.
 
# 🔑 Lessons Learned
Password strength directly correlates with wordlist size needed to crack it — weak/common passwords fall to small lists in seconds.

Both JTR and browser-based tools rely on the same core idea: hash every candidate password and compare it to the target hash.

# 🙏 Credits
NetworkWalks Academy | Cybersecurity & Ethical Hacking with AI — internship led by Waqas Karim.
