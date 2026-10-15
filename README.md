# Secrets

A [wedgie](https://wedgie.dev) app: messages only your wedgie can read.

1. **Make a key:** press green. The secure chip makes it and never lets it out (Trust M key slot 3, or
   ATECC608 slot 2; not the Safe Signer's key). The screen shows its ID, like `e95f d78e`.
2. **Share it:** at https://wedgie.dev/secret, Copy my link. Anyone with the link can write to you.
3. **They write:** they open your link, type, press Seal (in their browser, no wedgie needed), and
   send you the `wedgie1.…` text over any chat.
4. **You read:** paste it at wedgie.dev/secret, Open on wedgie, press green. It shows on the wedgie's
   screen, never on the computer. Up/down pages, red closes.

The computer you type on still sees what you type. The wedgie keeps the key safe and keeps messages
off the computer when you read them. The key never changes, so anyone who later gets your wedgie (and
presses green) can read old messages.

Format (`secret_box.py`): P-256 ECDH with a new key per message, HKDF-SHA256, AES-256-CBC, HMAC-SHA256.

Save: `key` (the public half, its chip, its ID).

MIT.
