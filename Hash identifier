#!/usr/bin/env python3

import re
import sys

# Dictionary of hash types with their lengths and patterns
HASH_TYPES = {
    "MD5": {"length": 32, "pattern": r"^[a-fA-F0-9]{32}$"},
    "SHA-1": {"length": 40, "pattern": r"^[a-fA-F0-9]{40}$"},
    "SHA-224": {"length": 56, "pattern": r"^[a-fA-F0-9]{56}$"},
    "SHA-256": {"length": 64, "pattern": r"^[a-fA-F0-9]{64}$"},
    "SHA-384": {"length": 96, "pattern": r"^[a-fA-F0-9]{96}$"},
    "SHA-512": {"length": 128, "pattern": r"^[a-fA-F0-9]{128}$"},
    "SHA3-224": {"length": 56, "pattern": r"^[a-fA-F0-9]{56}$"},
    "SHA3-256": {"length": 64, "pattern": r"^[a-fA-F0-9]{64}$"},
    "SHA3-384": {"length": 96, "pattern": r"^[a-fA-F0-9]{96}$"},
    "SHA3-512": {"length": 128, "pattern": r"^[a-fA-F0-9]{128}$"},
    "RIPEMD-160": {"length": 40, "pattern": r"^[a-fA-F0-9]{40}$"},
    "Whirlpool": {"length": 128, "pattern": r"^[a-fA-F0-9]{128}$"},
    "CRC32": {"length": 8, "pattern": r"^[a-fA-F0-9]{8}$"},
    "NTLM": {"length": 32, "pattern": r"^[a-fA-F0-9]{32}$"},
    "LM": {"length": 32, "pattern": r"^[a-fA-F0-9]{32}$"},
    "Bcrypt": {"length": 60, "pattern": r"^\$2[aby]?\$[0-9]{2}\$[./A-Za-z0-9]{53}$"},
    "Argon2": {"length": None, "pattern": r"^\$argon2(id|d|i)\$[v=0-9]+\$m=[0-9]+,t=[0-9]+,p=[0-9]+\$.+"}
}

def identify_hash(hash_value):
    hash_value = hash_value.strip()
    results = []
    
    for hash_type, properties in HASH_TYPES.items():
        if properties["length"] and len(hash_value) != properties["length"]:
            continue
        if re.match(properties["pattern"], hash_value):
            results.append(hash_type)
    
    return results

def main():
    if len(sys.argv) != 2:
        print(f"Usage: {sys.argv[0]} <hash>")
        sys.exit(1)

    hash_value = sys.argv[1]
    matches = identify_hash(hash_value)

    if matches:
        print(f"Hash: {hash_value}")
        print(f"Possible Types: {', '.join(matches)}")
    else:
        print(f"Hash: {hash_value}")
        print("Type: Unknown")

if __name__ == "__main__":
    main()
