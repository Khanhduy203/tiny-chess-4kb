# Tiny Chess — 4 KB engine

A 0x88 alpha-beta chess engine in a single `main.py` (<= 4096 bytes, lzma-packed).

- Negamax alpha-beta + transposition table + quiescence (captures, evasions in check)
- Null-move pruning, killer-move + MVV-LVA ordering
- Material + mirrored piece-square tables
- Fixed 50,000-node budget per move: deterministic, replay-safe, no clock, no randomness

Entry for make.fun competition `tiny-chess-01`. MIT licensed.
