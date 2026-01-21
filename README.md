# Elevatelabs_cybersec_task4
# 1.Prerequisites
- Use a Linux environment(Kali VM).
- Install free tools: Hashcat.​
- Download wordlists like rockyou.txt for dictionary attacks (available on GitHub or Kali Linux repos).
# 2.Hashing VS encrypt
  <h5>Hashing</h5>
- Hashing is a one-way process that transforms data into a fixed-length hash value.  It cannot be reversed.

    - bcrypt
    - SHA-256
    - MD5
  <h5>Encrypt</h5>
  Encryption is reversible and protects data confidentiality using keys.
  
    - AES-256
    - RSA
    - TLS/HTTPS 
<h5> </h5>   Identify and Generate Hashes

Common Hash Types:
- MD5: 128-bit, fast but insecure due to collision vulnerabilities. 
- SHA-1: 160-bit, deprecated and not recommended for security use. 
- bcrypt: Strong, salted, and slow by design—ideal for password hashing. 
Generate Hashes in Python:
```bash import hashlib
# MD5 hash
print(hashlib.md5(b'password').hexdigest())
# Output: 5f4dcc3b5aa765d61d8327deb882cf99

# SHA-1 hash
print(hashlib.sha1(b'password').hexdigest())
# Output: 5baa61e4c9b93f3f0682250b6cf8331b7ee68fd8

# SHA-256 hash
print(hashlib.sha256(b'password').hexdigest())
# Output: 5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8
```
For Secure Password Hashing (e.g., bcrypt):
```
import bcrypt

# Hash with salt
password = b'password'
salt = bcrypt.gensalt()
hashed = bcrypt.hashpw(password, salt)
print(hashed)

# Verify
if bcrypt.checkpw(password, hashed):
    print("Password matches!")
```
And i Have Gained Hand On Practice 
  - hashcat
  - MFA  
