# Hash Identifier Tool

This tool is a simple Python script designed to identify the type of a given hash by comparing it to common hash formats and lengths. It supports several common hash types such as MD5, SHA-1, SHA-256, SHA-512, NTLM, Bcrypt, and Argon2.

## Features
- Identifies commonly used hash types.
- Simple and lightweight.
- Works with a single command-line argument.

## Requirements
- Python 3.x
- No additional libraries required.

## Installation
1. Clone or download this repository.
2. Save the script to your preferred directory, e.g., `identify_hash.py`.
3. Make the script executable:
   ```bash
   chmod +x identify_hash.py
   ```

## Usage
To identify the type of a hash, run the script with the hash string as an argument:

```bash
./identify_hash.py <hash_value>
```

### Example:
```bash
./identify_hash.py 5d41402abc4b2a76b9719d911017c592
```
Output:
```bash
Hash Type: MD5
```

### Supported Hash Types:
- **MD5**: 32-character hexadecimal.
- **SHA-1**: 40-character hexadecimal.
- **SHA-256**: 64-character hexadecimal.
- **SHA-512**: 128-character hexadecimal.
- **NTLM**: 32-character hexadecimal (context needed for accurate detection).
- **Bcrypt**: Matches `$2[ayb]$`-formatted strings.
- **Argon2**: Matches `$argon2[id]{1,2}$`-formatted strings.

## How It Works
The script uses regular expressions to match the input hash against known patterns for various hash types. If a match is found, it returns the name of the hash type. If no match is found, it returns `Unknown or custom hash`.

## Extending the Tool
You can add more hash types by updating the `HASH_PATTERNS` dictionary in the script. For each new hash type, add its name as the key and a corresponding regular expression as the value.

Example:
```python
HASH_PATTERNS["NewHash"] = r"<regex_pattern_here>"
```

## Troubleshooting
1. **Error: `Permission Denied`**
   - Ensure the script is executable:
     ```bash
     chmod +x identify_hash.py
     ```

2. **Script doesn’t recognize a hash**
   - Verify the hash format and ensure it is supported by the script.
   - Update the script with additional hash patterns if needed.

## License
This tool is open-source and distributed under the MIT License. You are free to modify and use it as needed.

---
**Disclaimer:** This tool is provided as-is without any warranties. Ensure compliance with applicable laws when using it for security or research purposes.

