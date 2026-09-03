# Encryption - Crypto 101

## Lab Overview

Hands-on cryptography lab completed on TryHackMe as part of my CompTIA
Security+ SY0-701 preparation.

The lab covered encryption fundamentals, symmetric and asymmetric
cryptography, RSA, SSH key security, digital signatures, certificates,
Diffie-Hellman key exchange, and GPG encryption/decryption.

## Lab Information

| Field | Details |
|---|---|
| Platform | TryHackMe |
| Room | Encryption - Crypto 101 |
| Difficulty | Medium |
| Focus | Cryptography |
| Security+ Domain | Domain 1 - General Security Concepts |
| Status | Completed |

## Key Concepts

### Symmetric Encryption

Symmetric encryption uses the same key for encryption and decryption.

Examples:

- AES
- DES
- 3DES

### Asymmetric Encryption

Asymmetric cryptography uses a public/private key pair.

Examples:

- RSA
- ECC

### Hashing

Hashing is a one-way process that produces a fixed-length digest.

It is commonly used for integrity verification and secure password storage
mechanisms.

### Encoding

Encoding changes the representation of data and does not provide
confidentiality.

Example:

- Base64

## Practical Exercises

### 1. Modular Arithmetic

Practiced modulo calculations used in cryptographic mathematics.

```text
118613842 % 9091 = 3565
```

### 2. RSA Fundamentals

Practiced the mathematical concepts behind RSA using prime numbers and
modular arithmetic.

Example values used in the lab:

```text
p = 4391
q = 6659

n = p × q
n = 29239669
```

The exercise demonstrated how RSA relies on mathematical operations involving
large numbers and the difficulty of factoring large composite numbers.

### 3. SSH Private-Key Security

Worked with a password-protected SSH private key and converted it into a
format that could be analyzed using John the Ripper.

```bash
python ssh2john.py id_rsa.id > task9.txt
```

Used John the Ripper with a wordlist to perform a dictionary-based password
audit:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt task9.txt
```

**Security takeaway:** Weak passphrases protecting private SSH keys can be
vulnerable to dictionary-based attacks. Strong and unique passphrases should
be used to protect private keys.

### 4. Digital Signatures and Certificates

Studied how digital signatures can help provide:

- Integrity
- Authenticity
- Non-repudiation

Also explored how digital certificates establish trust between identities
and public keys.

A simplified certificate trust chain is:

```text
Root CA
   ↓
Intermediate CA
   ↓
Server Certificate
   ↓
Trusted HTTPS Connection
```

### 5. Diffie-Hellman Key Exchange

Studied how two parties can establish a shared secret over a public
communication channel without directly transmitting the final shared secret.

This demonstrated the concept of secure key establishment used in secure
communication systems.

### 6. GPG / PGP Encryption

Practiced working with an encrypted GPG file and a provided private key.

Imported the private key:

```bash
gpg --import tryhackme.key
```

Decrypted the encrypted file:

```bash
gpg --output message.txt --decrypt message.gpg
```

Verified the decrypted output:

```bash
cat message.txt
```

**Security takeaway:** Private keys must be securely protected because
unauthorized access to a private key can potentially allow decryption or
authentication.

## Tools Used

- Kali Linux
- Python
- ssh2john
- John the Ripper
- GPG
- Linux command line

## Security+ Relevance

**CompTIA Security+ SY0-701 — Domain 1: General Security Concepts**

Topics reinforced:

- Symmetric cryptography
- Asymmetric cryptography
- RSA
- Hashing
- Digital signatures
- Digital certificates
- PKI
- Diffie-Hellman
- Key management
- Confidentiality
- Integrity
- Authentication
- Non-repudiation

## Key Takeaways

- Symmetric encryption uses a shared secret key.
- Asymmetric cryptography uses public and private key pairs.
- Encryption primarily provides confidentiality.
- Hashing and encryption serve different purposes.
- Encoding does not provide confidentiality.
- Private keys must be securely protected.
- Weak key passphrases can be vulnerable to dictionary attacks.
- Digital signatures help provide integrity and authenticity.
- Digital certificates help establish trust between identities and public keys.
- Diffie-Hellman provides a method for establishing shared secrets.
- GPG can be used for encrypted-file operations.

## Evidence

Selected screenshots from the practical exercises are included in the
`screenshots/` directory.

Evidence includes:

- Modular arithmetic
- RSA calculations
- SSH key conversion
- John the Ripper execution
- GPG key import
- GPG decryption

Challenge-specific secrets and answers are intentionally not included.

## Lab Source

[TryHackMe - Encryption - Crypto 101](https://tryhackme.com/room/encryptioncrypto101)
