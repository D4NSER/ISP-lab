# Lab 02 — Vigenère cipher (Viženeris)

> ✅ Done. Variant 5. See [`atsakymas.txt`](atsakymas.txt).

## Task

Two parts: (1) decrypt a Vigenère cipher with a given key; (2) recover the key
used for a second ciphertext. Lithuanian alphabet
`aąbcčdeęėfghiįyjklmnoprsštuųūvzž`; non-alphabet symbols stay unchanged **and
the key is skipped over them** (only letters advance the key); uppercase is part
of the alphabet (case preserved). Full brief: [`task.txt`](task.txt).

Variant = student ID number mod 10 + 1.

## Solution

[`vigenere.py`](vigenere.py) — pure Python, no dependencies.

- Part 1 (decrypt): Vigenère decryption with the given key `mūša`
  → `Auksinis plaktukas ir geležines duris prakala.`
- Part 2 (recover key): cryptanalysis — key length from the index of
  coincidence (14), then each key letter by per-column frequency analysis.
  Recovered key: **`viešasisraktas`**. Verified across all 10 variants (each
  yields a meaningful Lithuanian key and readable plaintext).

## How to run

```bash
python3 vigenere.py 5      # your variant
python3 vigenere.py all    # all variants
```

## Files

- `vigenere.py` — solution
- `variantai/1.txt … 10.txt` — task data (part-1 cipher+key, part-2 cipher)
- `atsakymas.txt` — final answer for variant 5
- `task.txt` — assignment text
- `ISP_L2_Viženeris.pdf` — original brief
