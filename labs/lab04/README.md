# Lab 04 — Password storage / dictionary attack

> ✅ Main task done. Variant 5. See [`atsakymas.txt`](atsakymas.txt).
> Optional task (leaked-DB write-up) is left to do by hand — see note below.

## Task

Recover the plaintext passwords behind provided hashes via a dictionary attack:
MD5, SHA-256, bcrypt, scrypt (N=2^16, r=2, p=1), Argon2. MD5/SHA-256 use
`rockyou.txt`; bcrypt/scrypt/Argon2 use `rockyou_1000.txt`. Full brief:
[`task.txt`](task.txt). Variant = student ID mod 10 + 1.

## Solution

[`crack.py`](crack.py) — Python. Requires `bcrypt` and `argon2-cffi`:

```bash
pip install bcrypt argon2-cffi
python3 crack.py 5
```

Salt scheme (determined empirically, consistent for MD5/SHA-256/scrypt):
`hash(password + salt)` with the salt as its ASCII-hex string. bcrypt and
Argon2 carry the salt inside the encoded hash.

Variant 5 results: MD5 `3584975`, SHA-256 `rodenia4`, bcrypt `master`,
scrypt `manuel`, Argon2 `soccer`.

## Optional task (up to 5 pts) — not done here

Finding a real leaked password database and cracking 20+ of its hashes is a
research + write-up task (deliverable in .docx/.pdf). It involves sourcing real
breach data, so it's left for you to do directly rather than automated here.

## Files

- `crack.py` — solution
- `variantai/1.txt … 10.txt` — per-variant hashes
- `rockyou_1000.txt` — trimmed wordlist (committed)
- `rockyou.txt` — **not in git** (145 MB); download separately
- `atsakymas.txt` — final answer for variant 5
- `task.txt`, `ISP_L4_Slaptažodžių_saugojimas.pdf` — assignment
