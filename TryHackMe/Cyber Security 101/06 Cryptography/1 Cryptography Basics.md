# 1 Cryptography Basics

## 1.2 Importance of Crytogprahy
- ultimate purpose is to `secure communication in the presence of adversaries`
- can be defined as the `practice and study of techniques for secure communication and data protection` where we expect the presence of adversaries and third-parties

## 1.3 Plaintext to Ciphertext
- `Plaintext`: the original, readable message or data before it's encrypted
- `Ciphertext`: the scrambled, unreadable version of the message after encryption
- `Cipher`: an algorithm or method to convert plaintext into ciphertext and vv. Usually developed by a Mathematician
- `Key`: string of bits the cipher uses to encrypt or decrypt data.
- `Encryption`: the process of converting plaintext into ciphertext using a cipher and a key
- `Decryption`: the reverse process of encryption, converting ciphertext back into plaintext using a cipher and a key

## 1.4 Historical Ciphers
- Cryptography history started back to ancient Egypt in 1900 BCE
- Simplest historical cipher is the `Caesar Cipher`. The idea is simple: `shift each letter by a certain number to encrypt the message`
- More historical ciphers:
    - The Vigenere Cipher from the 16th century
    - The Enigma Machine from World War II
    - The One-Time Pad from the Cold War
- tool to explore: https://cryptii.com/

## 1.5 Types of Encryption
### Symmetric Encryption
- also known as *Symmetric Cryptography* or *Private Key Cryptography*
- uses the `same key` to encrypt and decrypt the data, thus keeping the key **secret** is a must
- communicating the key can be more challenging as it will require as `secure communication channel`
- examples of symmetric encryption:
    - `DES (Data Encryption Standard)`: standard in 1977 and uses a 56-bit key. With the advancement during 1999, DES was successfully broken in 24 hours, shifting to 3DES
    - `3DES (Triple DES)`: key size is 168 bits, though effective security is 112 bits. 3DES is a more of an `ad-hoc solution`. It deprecated in 2019 and replaced by AES. However, it can still be found in some legacy systems
    - `AES (Advanced Encryption Standard)`: adopted standard in 2001. Key size can be 128, 192, or 256 bits
- there are many more symmetric encryption ciphers used in applications, but they are not adopted as standards
### Asymmetric Encryption
- also known as *Asymmetric Cryptography* or *Public Key Cryptography*
- uses a `pair of keys`, one to encrypt (public key) and one to decrypt (private key)
- to protect `Confidentiality`, the public key is used to encrypt the data
- examples of asymmetric encryption:
    - `RSA (Rivest-Shamir-Adleman)`: relies on the difficulty of factoring large number
    - `Diffie-Hellman`
    - `Elliptic Curve Cryptography (ECC)`: encrypt data using smaller keys while still providing strong security. It is based on the Math of elliptic curves
- Asymmetric encryption tends to be `slower`, as many use `larger keys`. RSA uses 2048-bit, 3072-bit, and 4096-bit keys; Having 2048-bit as the recommended min key size
- Asymmetric encryption is based on a `particular group of mathematical problems` that is easy to compute in one direction but difficult to reverse

## 1.6 Basic Math
- the building blocks of modern cryptography lie in the Mathematics
### XOR Operation
- short for `exclusive OR`
- compares two bits and returns 1 if the bits are different and 0 if they are the same
### Modulo Operation
- commonly written as `%` or `mod`
- the `remainder`
- always returns a `non-negative` result. The result will also be in the range of 0 to n-1
- tool to explore: https://www.wolframalpha.com/

