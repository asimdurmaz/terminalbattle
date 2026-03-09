
# Terminal Battle

**everything was vibecoded with claude**

competitive cli typing game
type terminal commands faster than your opponent

https://terminalbattle.netlify.app/

---

## what it is

two-player competitive typing game. both players get a list of terminal commands to type — whoever scores the most points wins. play solo against an AI or against someone online via WebRTC (no server needed).

## how to play

pick Windows CMD or Linux Bash, enter a username, and start typing the commands shown in the task panel. you don't need to know what the commands do, just type them accurately.

- correct command: +1 point
- `skip`: move to next task, -1 point
- `help`: reveals ~55% of the command, -0.5 points
- 3 correct in a row: +0.5 streak bonus

highest score wins, not who finishes first.

## multiplayer

- **create room**: generates a 4-char code, share it with your opponent
- **join room**: enter their code
- **find opponent**: drops you in a matchmaking queue

if no opponent is found, falls back to AI.

## commands

covers Windows CMD and Linux Bash across 4 tiers:

| tier | examples |
|------|---------|
| beginner | `dir` / `ls`, `cd`, `whoami`, `mkdir` |
| intermediate | `type` / `cat`, `copy` / `cp`, `tasklist` / `ps aux` |
| sysadmin | `findstr` / `grep`, `ipconfig` / `ip addr`, `netstat` |
| god mode | `tracert` / `traceroute`, `nslookup` / `dig`, `arp -a` |

## stack

single HTML file — React 18, PeerJS (WebRTC), Web Audio API. no build tools, no backend.
