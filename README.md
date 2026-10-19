# Secrets

A [wedgie](https://wedgie.dev) app: chat where only your wedgie can read what you get.

1. **Make a key:** press green. The secure chip makes it and never lets it out (Trust M key slot 3, or
   ATECC608 slot 2; not the Safe Signer's key). The screen shows its ID, like `e95f d78e`.
2. **Share it:** at https://wedgie.dev/secret, Copy my link. Anyone with the link can write to you.
3. **Chat:** open their link and add them. You type at wedgie.dev/secret; it's sealed in your browser
   to their key and goes through a mailbox there that holds only sealed text (gone after 7 days).
4. **Read:** their messages show only on your wedgie's screen. Every message asks for a green press first;
   the wedgie never shows who it says it is from (only the computer says that). Up/down pages, red closes.

No wedgie? Open someone's link and write to them once. They can't reply.

The computer you type on still sees what you type, and keeps what you sent so the chat reads both ways. Who a message says it's from isn't proven: anyone with your link can claim a name. The wedgie keeps the key safe and keeps messages
off the computer when you read them. The key never changes, so anyone who later gets your wedgie (and
presses green) can read old messages.

Format (`secret_box.py`): P-256 ECDH with a new key per message, HKDF-SHA256, AES-256-CBC, HMAC-SHA256.

Save: `key` (the public half, its chip, its ID).

MIT.
