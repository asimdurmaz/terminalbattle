# Terminal Battle

**everything was vibecoded with claude**

type terminal commands faster than your opponent

https://terminalbattle.netlify.app/

---

## what it is

competitive CLI typing game. type terminal commands as fast and accurately as you can. play solo vs AI, against a friend online via WebRTC, or grind survival mode for a leaderboard score.

## modes

**vs AI** — race an AI opponent through a fixed task list. difficulty sets AI speed and which command tiers appear. highest score wins, not who finishes first.

**multiplayer** — real-time 1v1 via WebRTC, no server needed.
- **create room**: generates a 4-char code, share it with your opponent
- **join room**: enter their code
- **find opponent**: matchmaking queue, falls back to AI if no one found

**daily challenge** — same fixed task list for everyone that day. score saved locally, button greys out after completion.

**survival** — no fixed endpoint. starts at 60s, tasks get harder as you go. correct answers add time back, skips and wrong answers drain it. eventually the math works against you no matter how fast you type.

## scoring

- correct command: **+1 pt**
- `skip`: next task, **−1 pt** (survival: also **−5s**)
- `help`: reveals ~55% of command, **−0.5 pt**
- wrong answer: streak reset (survival: also **−3s**)
- 3 correct in a row: **+0.5 streak bonus**
- fast answers: **+0.1 to +0.3 time bonus** (vs AI / daily only)

in survival, time reward per correct answer shrinks as you progress — starts at +8s, floors at +2s around task 12+.

## progression

wins in solo/AI mode unlock ranks: NOOB → POWER USER → ROOT → GOD MODE. tracked in localStorage.

survival scores post to a global leaderboard (Supabase).

## commands

covers Windows CMD and Linux Bash across 4 tiers:

| tier | examples |
|------|---------|
| beginner | `dir` / `ls`, `cd`, `whoami`, `mkdir` |
| intermediate | `cat`, `cp -r`, `mv`, `ps aux`, `grep` |
| sysadmin | `grep -r`, `tar -czf`, `chmod 755`, `du -sh`, `ss -tlnp` |
| god mode | `scp`, `curl -X POST`, `pkill -9`, `find -mtime`, `chown root:root` |

## stack

single HTML file — React 18, PeerJS (WebRTC), Web Audio API, Supabase (leaderboard). no build tools, no backend to host.
