# AESCipher

This file is a custom implementation of the AES hashing technique for a cryptography-based application. The AESCipher class provides methods for encrypting and decrypting data using the AES algorithm in CBC (Cipher Block Chaining) mode. 

```markdown
## Features

- **AES Encryption**: Implements AES with CBC mode for secure encryption.
- **Base64 Encoding**: The encrypted output is Base64 encoded for easier transmission.
- **Hexadecimal Representation**: Supports converting encrypted data into a hexadecimal format prefixed with `0x`.
- **Padding and Unpadding**: Automatically handles padding of input data to ensure proper block size.

## Requirements

- Python 3.x
- `pycryptodome` or equivalent cryptography library

To install the required library, you can use pip (if applicable):

```bash
pip install pycryptodome
```

## Usage

### Initialization

Create an instance of the AESCipher class with a key:

```python
from aes_cipher import AESCipher

cipher = AESCipher("your_secure_key")
```

### Encryption

To encrypt a string and get the hexadecimal representation:

```python
encrypted = cipher.encrypt_bytes32("Hello world!")
print(encrypted)  # Example output: 0x0ee273a7affa4c0f6caa2c6be14fa0466ae6e314771e6561022a4b0de8bc1c69
```

### Decryption

To decrypt a previously encrypted hexadecimal string:

```python
decrypted = cipher.decrypt_bytes32("0x0ee273a7affa4c0f6caa2c6be14fa0466ae6e314771e6561022a4b0de8bc1c69")
print(decrypted)  # Output: Hello world!
```

## Example

Here’s a full example demonstrating encryption and decryption:

```python
if __name__ == "__main__":
    c = AESCipher("admin@123")
    input_string = "Hello world!"

    # Encrypt the input
    encrypted = c.encrypt_bytes32(input_string)
    print(f"Encrypted: {encrypted}")

    # Decrypt the previously encrypted value
    decrypted = c.decrypt_bytes32(encrypted)
    print(f"Decrypted: {decrypted}")
```

## Notes

- The key used for encryption should be kept secure and should be of adequate length (e.g., at least 16 characters).
- This implementation is intended for educational purposes and should not be used in production without further security measures.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
```
