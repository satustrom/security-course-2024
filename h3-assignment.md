# H3 assignment

## X. Summaries

#### **[Schneier 2015: Applied Cryptography](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec004):**

**2.3 One-way Fuctions**

- One-way functions are crucial in public-key cryptography, they are easy to compute but it's very difficult (almost impossible..) to reverse (like breaking a plate)
- A trapdoor one-way function is a one-way function with a twist: it is yet very hard to reverse unless you know the hidden secret (trapdoor). With the secret reversing is as easy as computing

**2.4 One-Way Hash Functions**

- One-Way hash function means the same as compression function, contraction function, message digest, fingerprint, cryptographic checksum, message integrity check (MIC) and manipulation detection code (MDC)
- Hash function means converting a string (=pre-image) into fixed-length output string (=hash value)
- A message authentication code (MAC) is a one-way hash function with an addition of secret key: Someone who has the secret key, can vrify the hash value.

Reference: Schneier 2015. Applied Cryptography. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec004. Accessed: 10 November 2024.

#### **[Karvinen 2020: Cracking Passwords with Hashcat](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/):**

- Instead of storing original passwords, systems store the hash of them
- Hashcat is a hash cracking program
-

Reference: Karvinen 2020. Cracking Passwords with Hashcat. URL: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/. Accessed: 10 November 2024.
