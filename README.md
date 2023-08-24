#README
#Encryption Using Transformers
This code is designed to showcase the use of transformer-based tokenization in conjunction with standard cryptographic techniques to encrypt and then decrypt a given text.

#Overview
The code includes:

Required package installations for transformers, datasets, and cryptography.
#Utility functions:
text_to_key: Converts a text into a 256-bit key using SHA-256 hashing.
encrypt: Encrypts a plain text using the AES-GCM cipher with a given key.
decrypt: Decrypts an encrypted text using the AES-GCM cipher with a given key and associated data (IV and authentication tag).
whole_setup: End-to-end function that tokenizes a text using a transformer, encrypts the tokenized text, then decrypts and detokenizes it.
How to Use
Install the necessary packages.

#python
Copy code
!pip install transformers
!pip install datasets
!pip install cryptography
Import the necessary modules and define utility functions.

Generate a 256-bit key from a user-provided text:

python
Copy code
text = input()
key = text_to_key(text)
print(key)
Provide a text to be encrypted and decrypted:

python
Copy code
text_w = input()
Execute the whole_setup function to see the decrypted text:

python
Copy code
print('decryption',whole_setup(key,text_w))
#Note
#The original file is located at https://colab.research.google.com/drive/1LTJRztvUuKclV7VfjsbvKAMXVorjIgHc.

#Dependencies
transformers: For transformer-based tokenization.
datasets: Although imported, it seems the code does not make use of this package.
cryptography: For encryption and decryption using AES-GCM cipher.
pandas, os, and hashlib: Utility libraries.
#Limitations
The tokenization is specific to the model "EleutherAI/pythia-70m".
The encryption mechanism uses the AES-GCM cipher, which requires the storage of both an IV (Initialization Vector) and an authentication tag for decryption. Not storing these securely can compromise the encryption.
The code assumes the input texts are in utf-8 encoding. Different encodings may lead to errors.
