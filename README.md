# rd-sync

Transport bucket for an encrypted payload.

A local job writes `bundle.b64` here: an AES-256-CBC ciphertext, base64 encoded.
A scheduled job elsewhere fetches it and decrypts it with a key that is not in
this repository and never will be.

Nothing here is readable without that key, which is why the repository can be
public. `stamp.txt` carries only the generation time, so an observer can tell
whether the bundle is current without learning anything about its contents.

No credentials, tokens or plaintext are committed. If you found this repo by
accident, there is nothing here for you.
