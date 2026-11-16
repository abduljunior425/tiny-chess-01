# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/abduljunior425/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/abduljunior425/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A tiny chess engine in one Python file, packed to fit in 4,096
bytes. Negamax with alpha-beta, quiescence on captures, a
transposition table, and killer, history, and null-move ordering.

Each turn it reads the position and legal moves from the game
server, searches to a fixed node budget, and answers with one
move. No clock is used, so the same position always gets the
same answer.

Local practice trial: 3.0/6 against the house gauntlet, a
practice Elo of 1279 — above the 1154 floor for the final.

## Try it

```sh
python3 main.py
```

---

Built for the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01) · referral code `z8dqtwbf`
