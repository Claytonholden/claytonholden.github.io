# NCL — Crypto Playbook

## Common challenge types
- Caesar/ROT shifts
- substitution hints
- tiny RSA puzzles (n, e, ciphertext list)
- “password dumps” with simple encoding

## Workflow
1) Identify cipher type by clues:
   - looks like shifted letters → Caesar/ROT
   - numbers + (n,e,c) → RSA-like
2) Try quick wins:
   - CyberChef: ROT13, Caesar brute force, Base64, etc.
3) Validate:
   - output should be readable / match flag format

## RSA (small n) mindset
- If n is small, it might be factorable
- Convert numeric blocks back to bytes/text after decrypting
- Always confirm padding/encoding expectations

## Tooling
- CyberChef for rapid trials
- Python for custom math
