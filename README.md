# vaultfs — encrypted file store

This repository holds **ciphertext only**. Every file here is
zlib-compressed and Fernet-encrypted (AES-128-CBC + HMAC) before upload.

- `blobs/*.bin` — encrypted file contents under random names.
- `manifest.json.enc` — encrypted index mapping aliases to blobs.
  Filenames live only inside this encrypted manifest.

Browsing this repo you will see nothing but noise. It is managed by the
`encrypted-github-fs` skill; the decryption key exists only on the owner's
machine and is never committed here.

`blobs/**` is routed through Git LFS (see `.gitattributes`) for future
git-based workflows; API sync uploads go through the GitHub Contents API.
