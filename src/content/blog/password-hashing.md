---
title: 'Password Hashing'
description: 'Best practices for securely storing passwords'
pubDate: 'May 10 2025'
heroImage: '/password-hashing.png'
---

Password hashing is a crucial technique for securing user passwords in your applications. Instead of storing plain-text passwords, hashing transforms them into an unreadable format, making it much harder for attackers to steal user credentials.

## What Is Password Hashing?

Hashing is a one-way function that converts a password into a fixed-length string. Good hashing algorithms make it practically impossible to reverse the hash back into the original password.

---

## Why Not Store Plain-Text Passwords?

If an attacker gains access to your database and you stored passwords in plain text, every user's password would be immediately compromised. Hashing protects users even if your database is breached.

---

## Hashing vs. Encryption

| Method      | Description                                  |
| ----------- | -------------------------------------------- |
| Hashing     | One-way, irreversible, used for verification |
| Encryption  | Two-way, reversible with a secret key        |

Use **hashing** for passwords, not encryption.

---

## How to Hash Passwords

A common and secure way to hash passwords in modern applications is using libraries like **bcrypt**.

### Example with bcrypt in Node.js

```javascript
import bcrypt from 'bcrypt';

async function hashPassword(password) {
  const saltRounds = 10;
  const hash = await bcrypt.hash(password, saltRounds);
  return hash;
}

async function verifyPassword(password, hash) {
  const isMatch = await bcrypt.compare(password, hash);
  return isMatch;
}
