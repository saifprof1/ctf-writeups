# Textbook Leak

**Category:** Cryptography

## Challenge Description

This challenge provided the RSA public parameters (`n` and `e`) along with a list of ciphertext blocks. The goal was to recover the hidden secret by analyzing how RSA had been implemented.

## Investigation

I first read the challenge description and then examined the provided `intercepted_rsa.txt` file.

While reading the file, I noticed the following information:

- RSA public modulus (`n`)
- Public exponent (`e`)
- A list of encrypted ciphertext blocks

The challenge description also mentioned that the data was encrypted **one byte at a time** without any padding (Textbook RSA). This suggested that the implementation was insecure and vulnerable to cryptographic analysis.

The next step was to determine whether the RSA modulus could be factored. Using publicly available cryptographic resources and Python, I factored the modulus into its two prime numbers. After obtaining the prime factors, I calculated the private exponent (`d`) and reconstructed the private key.

Finally, I decrypted each ciphertext block individually and converted the resulting byte values back into readable text.

## Solution

After reconstructing the RSA private key and decrypting each ciphertext block, the original plaintext was successfully recovered.

The recovered plaintext matched the required flag format.

## Lessons Learned

This challenge demonstrates why Textbook RSA should never be used in real-world applications. Encrypting data without padding and processing one byte at a time makes RSA vulnerable to attacks once the modulus can be factored. Modern implementations should always use secure padding schemes such as OAEP.

## Tools Used

- Python
- Visual Studio Code
- Public Cryptography References
