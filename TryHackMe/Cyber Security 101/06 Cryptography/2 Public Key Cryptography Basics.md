# 2 Public Key Cryptography Basics

## 2.1 Introduction
### Learning Objectives
To cover asymmetric cryptosystems and applications that use them:
- RSA
- Diffie-Hellman
- SSH
- SSL / TLS Certificates
- PGP and GPG

## 2.2 Common Use of Asymmetric Encryption

## 2.3 RSA
### The Math That Makes RSA Secure
- based on a mathematical problem of `factoring a large number`
- `modular arithmetic`
    - `n = p x q`
    - `mod(n) = n - p - q + 1`
    - `e` how do you determine what number?
    - `d` how do you determine what number?
    - `e x d = 1 mod(n)`
    - medj magulo pero maiintindihan din natin 'yan lol
### RSA in CTFs
- variables of RSA in CTFs
    - `p and q` are large prime numbers
    - `n` is the product of `p and q`
    - `n and e` is the public key
    - `n and d` is the private key
    - `m` represents the original message (plaintext)
    - `c` represents the encrypted message (ciphertext)

## 2.4 Diffie-Hellman Key Exchange
- `Key Exchange` aims to establish a shared secret between two parties
- allows the two parties to establish a shared secret over `insecure communication channel` without requiring pre-existing shared secret without an observer to get this key
- a shared key that they can use for symmetric encryption in subsequent communications
