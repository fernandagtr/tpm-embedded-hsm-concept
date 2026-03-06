# ⛓ TPM-Based Hardware Rooted Encryption

- Overview

 This project explores the limits of hardware and demonstrates a somewhat more expensive possibility of intrusion using a common encryption model but in a different storage location, namely the Trusted Platform Module, but in a more robust way, being a "TPM 2.0".

 The proposal aims to investigate how encrypted messages can be transformed into cryptographic keys and securely stored within a TPM, acting as a secure hardware-backed vault.

 Traditional encryption systems rely on software, but these can suffer from memory attacks or malware.

 The purpose of this project is to consider:
 Would it be possible to transform a message into a cryptographic key and securely store it on hardware that is not as easily acquired as a USB drive?

  The project was designed as follows:

   1. A message is encrypted using a derived key.

   2. The encrypted message is transformed into a key representation.

   3. The key is stored within the TPM.
       
Where:
 
    RootKey → Hardware protected key inside TPM
    BootMeasurement → Secure boot measurement from the platform

This ensures the key can only be derived if the platform state is trusted. When the system is shut down, the TPM maintains the protected storage.

Decryption is only performed when the TPM releases the protected, completely random key.

Security Goals
Hardware-backed key protection
Resistance against memory extraction attacks
Secure storage of encryption material
Platform integrity validation before key release

- Potential Applications

Secure messaging systems
Hardware-bound encryption
Secure document storage
Anti-tampering systems
Zero-trust device authentication


- This architecture attempts to mitigate:

1. Malware attempting to extract encryption keys
2. Memory scraping attacks
3. Unauthorized system access
4. Software-only key storage vulnerabilities

- Limitations
This project is a conceptual research model, not a ready-to-run implementation.
Therefore, it presents some challenges, such as:

TPM storage limitations
Key lifecycle management
Platform compatibility
Hardware dependency

- Future Work
Possible future improvements:

Prototype implementation
TPM API integration
Secure enclave comparison
Hardware-backed key rotation model
