## Handshake Protocol

- Sender sends a connect request (which contains a pk and hash)
  - Recipient can very connect request with the public key
  - Recipient can send a rejection signed with the public key
  - Recipient can send an acceptance signed with sender's public key, and includes his own public key

