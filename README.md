# Encrypted itinerary viewer

This repository contains only a generic password screen and an encrypted payload. The unencrypted itinerary source is kept separately in a private repository. No password or decryption key is stored here.

Encryption: PBKDF2-HMAC-SHA-256 (600,000 iterations, random 16-byte salt), AES-256-GCM (random 12-byte IV, 128-bit authentication tag), gzip before encryption. The payload format is 8-byte TRIPENC1 header, salt, IV, ciphertext and authentication tag.

Use a long, unique sharing password. Anyone can download the ciphertext and attempt password guesses offline; this is not server authentication or rate limiting. Changing the password cannot revoke already downloaded/decrypted copies or erase earlier Git versions.

Published with GitHub Pages from main/root. Keep the owner and repository name unchanged to retain the link.
