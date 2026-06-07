# Void Striker — Pong Clone

## What it is
A single-player, space-themed Pong clone playable in any browser. The player controls the bottom paddle against a CPU opponent on the top. First to 7 points wins.

## How to run
Open `index.html` directly in a browser — no server, no build step, no dependencies.

## GitHub
https://github.com/edo-tm/pong-clone (branch: master)

## Tech stack
- Plain HTML + CSS + Canvas API + vanilla JavaScript
- Single file: `index.html`

## Controls
- `←` / `→` — move paddle left/right
- `Space` — launch ball (at game start and after each point)

## Key decisions
- **Alternate orientation** — paddles on top/bottom, ball moves vertically
- **CPU uses prediction** — it calculates where the ball will land, but with a random error offset (`CPU_ERROR_RANGE`) so it's beatable
- **CPU speed = player speed** (`PADDLE_SPEED`) — fairness; error range is the only handicap
- **Ball speed-up** — increases by `BALL_SPEED_INCREMENT` per paddle hit, resets to base after each point
- **Space-to-launch** — ball waits at center between points for player to press Space

## Key constants (in index.html)
| Constant | Value | Purpose |
|---|---|---|
| `BALL_BASE_SPEED` | 3.0 | Starting ball speed |
| `BALL_SPEED_INCREMENT` | 0.35 | Speed added per paddle hit |
| `PADDLE_SPEED` | 5.5 | Player and CPU paddle speed |
| `CPU_ERROR_RANGE` | 18px | How far off the CPU can aim (difficulty tuning) |
| `WIN_SCORE` | 7 | Points needed to win |

## File structure
```
pong-clone/
├── index.html       # entire game
└── CLAUDE.md        # this file
```

## Known issues / future ideas
- Could add difficulty selector (adjusts CPU_ERROR_RANGE)
- Mobile touch controls
- Sound effects
