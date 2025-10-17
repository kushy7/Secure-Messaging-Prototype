# Project 1 — Secure Communication Prototype (Authenticity and Integrity)

A comprehensive Python secure messaging prototype featuring textbook RSA digital signatures, Diffie–Hellman key exchange, SHA-256-based session key derivation, cryptographically secure PRNG, and authenticated encryption using Encrypt-then-MAC with HMAC-SHA256. Implements public-key infrastructure, key agreement, message integrity, tamper detection, and end-to-end encryption—all with Python’s standard library. Ideal for learning, research, and demonstrating modern cryptography, secure communication, and cybersecurity best practices:

Task 1: RSA (textbook) — keygen, hash, sign, verify

Task 2: Diffie–Hellman + signatures on exchanged values

Task 3: Key Derivation Function (KDF) (iterated SHA-256) to derive a session key

Task 4: PRNG with seed/reseed/generate (SHA-256 based)

Task 5: Authenticated Encryption (Encrypt-then-MAC) with a SHA-256 CTR keystream and HMAC-SHA256 (sym_enc / sym_dec)

Task 6: Tampering demo (bit flip → MAC failure → no decrypt)

# How to Run (single command)

Make sure you have Python 3.9+

From the repo root, run the script directly:

> python3 Project1-Secure-Communication


That’s it. The built-in demo code runs all tasks in order and prints:

Task 1: public keys and signature verification (1 with correct key, 0 with wrong)

Task 2: DH parameters/values, signatures & verification, shared secret match

Task 3: derived session keys (hex) and equality check

Task 4: PRNG sequences (same seed ⇒ same output; different seed ⇒ different)

Task 5 (EtM):

Alice: inputs to sym_enc, outputs (nonce, ciphertext), HMAC input (nonce||ciphertext), tag, and the final packet (nonce||ciphertext)||tag

Bob: recomputed HMAC equals Alice’s tag; successful decryption

Task 6: tampered ciphertext → HMAC mismatch → sym_dec returns None
