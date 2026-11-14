# Tiny Chess — 4 KB engine

A 0x88 alpha-beta chess engine in a single `main.py` (<= 4096 bytes, lzma-packed).

- Negamax alpha-beta + transposition table + quiescence (captures, evasions in check)
- Null-move pruning, killer-move + MVV-LVA ordering
- Material + mirrored piece-square tables
- Fixed 75,000-node budget per move: deterministic, replay-safe, no clock, no randomness
- Fast engine (e8): 1.84x speedup over the base via pin-skip legality, incremental eval, fast at(), alignment

Round-3 results (official kit scorer, 3 practice trials): t0 1290, t1 1396, t2 1326, mean 1337 — beats the submitted e8_50k (mean 1249) by 88 Elo. Max move 3.59 s locally (7.2 s at server slowdown 2.0, inside the 10 s limit). Eval fixes (hanging-piece penalty, king safety, RFP+LMR) all tested and rejected — the budget ladder, not eval, is what lifts the mean.

Entry for make.fun competition `tiny-chess-01`. MIT licensed.
