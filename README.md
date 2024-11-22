# Hash Identifier Script

This Python script helps identify the type of a given hash value by comparing it against a predefined list of common cryptographic hash algorithms and formats. It uses regular expressions to match the input hash to known patterns associated with different hash types.

## Features
- Identifies common hash types such as MD5, SHA-1, SHA-256, and more.
- Supports hashing algorithms like SHA-224, SHA-3, RIPEMD-160, Bcrypt, Argon2, NTLM, and others.
- Uses regular expressions to match hash patterns to their corresponding types.
- Prints the hash value and possible matching types, or marks it as "Unknown" if no match is found.

## Requirements
- Python 3.x
- No external libraries are required.

## Usage
1. Download or clone this repository.
2. Run the script from the command line, passing a hash value as an argument:

```bash
python hash_identifier.py <hash_value>```
 
Example
python hash_identifier.py e99a18c428cb38d5f260853678922e03

Output
Hash: e99a18c428cb38d5f260853678922e03
Possible Types: MD5


## Hash Types Supported
-MD5
-SHA-1
-SHA-224
-SHA-256
-SHA-384
-SHA-512
-SHA3-224
-SHA3-256
-SHA3-384
-SHA3-512
-RIPEMD-160
-Whirlpool
-CRC32
-NTLM
-LM
-Bcrypt
-Argon2
## Notes
The script supports hash formats with specific lengths and patterns. If a hash does not match any known pattern or length, it will be labeled as "Unknown".
The script is case-insensitive for most hash types, except for the Bcrypt and Argon2 hashes, which require exact formatting.
## License
This script is provided for educational purposes and personal use. You can modify and distribute it under the terms of the MIT License.

