# README

**Welcome to the Project README!**

This README serves as a comprehensive guide to our project, providing essential information and instructions for users, contributors, and anyone interested in this project. We'll walk you through the project's goals, features, installation steps, and usage guidelines. Please follow the instructions carefully to get started and make the most out of our project. If you encounter any issues or have suggestions for improvement, don't hesitate to reach out. Your feedback and contributions are highly valued and appreciated. Thank you for being a part of our project's community!
## Encryption Using Transformers

This code is designed to showcase the use of transformer-based tokenization in conjunction with standard cryptographic techniques to encrypt and then decrypt a given text.

### Overview

The code includes:
1. Required package installations for `transformers`, `datasets`, and `cryptography`.
2. Utility functions:
    - `text_to_key`: Converts a text into a 256-bit key using SHA-256 hashing.
    - `encrypt`: Encrypts a plain text using the AES-GCM cipher with a given key.
    - `decrypt`: Decrypts an encrypted text using the AES-GCM cipher with a given key and associated data (IV and authentication tag).
    - `whole_setup`: End-to-end function that tokenizes a text using a transformer, encrypts the tokenized text, then decrypts and detokenizes it.

### How to Use

1. Install the necessary packages.
    ```python
    !pip install transformers
    !pip install datasets
    !pip install cryptography
    ```

2. Import the necessary modules and define utility functions.

3. Generate a 256-bit key from a user-provided text:
    ```python
    text = input()
    key = text_to_key(text)
    print(key)
    ```

4. Provide a text to be encrypted and decrypted:
    ```python
    text_w = input()
    ```

5. Execute the `whole_setup` function to see the decrypted text:
    ```python
    print('decryption',whole_setup(key,text_w))
    ```

### Note

The original file is located at [https://colab.research.google.com/drive/1LTJRztvUuKclV7VfjsbvKAMXVorjIgHc](https://colab.research.google.com/drive/1LTJRztvUuKclV7VfjsbvKAMXVorjIgHc?usp=sharing).

### Dependencies

- `transformers`: For transformer-based tokenization.
- `datasets`: Although imported, it seems the code does not make use of this package.
- `cryptography`: For encryption and decryption using AES-GCM cipher.
- `pandas`, `os`, and `hashlib`: Utility libraries.

### Limitations

1. The tokenization is specific to the model "EleutherAI/pythia-70m".
2. The encryption mechanism uses the AES-GCM cipher, which requires the storage of both an IV (Initialization Vector) and an authentication tag for decryption. Not storing these securely can compromise the encryption.
3. The code assumes the input texts are in utf-8 encoding. Different encodings may lead to errors.

### Uses
This encryption technique, if used correctly, can provide robust security for a wide range of sensitive data, including text, photos, multimedia files, and more. In the context of text communication, such as emails or instant messaging, it ensures that confidential information remains private and protected from unauthorized access. For photos and multimedia files, this encryption can safeguard personal photos, videos, and audio recordings from prying eyes or data breaches, especially important in an era of increasing digital privacy concerns. In business settings, it can be employed to secure proprietary documents, financial records, and multimedia presentations, preserving competitive advantages and intellectual property. Overall, the application of this encryption methodology can instill a sense of trust and privacy in digital interactions, enabling individuals and organizations to confidently exchange sensitive information in an increasingly interconnected world.

