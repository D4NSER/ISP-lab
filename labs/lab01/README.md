# Lab 01 — Caesar cipher (Cezaris)

> ✅ Done. Variant 5. See [`atsakymas.txt`](atsakymas.txt).

## Task

Encrypt a text with the Caesar cipher for a given shift, and decrypt a
Caesar-encrypted text. Lithuanian alphabet `aąbcčdeęėfghiįyjklmnoprsštuųūvzž`
(32 letters); non-alphabet symbols stay unchanged; uppercase is part of the
alphabet (case preserved). Full brief: [`task.txt`](task.txt) / `ISP_L1_Cezaris.pdf`.

Variant = student ID number mod 10 + 1.

## Solution

[`caesar.py`](caesar.py) — pure Python, no dependencies.

- Part 1 (encrypt): shifts the variant's plaintext by the given key.
- Part 2 (decrypt): the shift is **not** given, so the program recovers it by
  frequency analysis (picks the shift whose plaintext scores most Lithuanian
  under a letter log-likelihood model). Verified to recover the correct shift
  for all 10 variants — each decrypts to a real Lithuanian proverb.

## How to run

```bash
python3 caesar.py <variant>   # e.g. python3 caesar.py 3
python3 caesar.py all         # all 10 variants
```

## Files

- `caesar.py` — solution
- `variantai.txt` — task data (encrypt section with shifts, decrypt section)
- `task.txt` — assignment text
- `ISP_L1_Cezaris.pdf` — original brief
- `atsakymas.txt` — final answer for your variant (added once variant is known)
