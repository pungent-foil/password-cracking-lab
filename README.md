# Password Cracking Lab

---

## Objective 
Crack a set of sample MD5 hashed passwords using John the Ripper and the rockyou.txt wordlist.

---

## Steps Taken 

1. Created a file 'hashes.txt' with three MD5 hashed passwords.
2. Used 'hash-identifier' to confirm the hash type as MD5.
3. Ran John the Ripper with the rockyou.txt wordlist to crack the hashes:

john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

---

## Results

- Succesfully identified the hash type as Raw-MD5 using John the Ripper's auto-detection and hash identifiers.
- Cracked 3 password hashes from the provided hashes.txt file using the rockyou.txt wordlist:
  💠 Password

  💠 123

  💠 admin

- The cracking process completed within seconds, demonstrating the weakness of common and simple passwords.
- This highlights the critical need for strong, complex passwords and proper hashing algorithms. 

---

## Hiccups

- Initially encountered hash type ambiguity warnings, where John the Ripper detected multiple possible hash fromats (e.g. LM, MD5, HAVAL-128). This was resolved by explicitly specifying the hash format with the --format=raw-md5 option.
- The rockyou.txt wordlist was missing on the Kali Linux system by default. Therefore I had to install it using: sudo apt install wordlists, sudo gunxip/usr/share/wordlists/rockyou.txt.gz
- This showed me the importance of verifying wordlist paths and specifying correct hash formats to avoid cracking failures.
- I gained familiarity with John the Ripper's output commands and how to redirect cracked passwords into a seperate file for reporting.

