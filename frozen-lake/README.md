# Frozen Lake (Non-slippery version)
Frozen lake involves crossing a frozen lake from start to goal without falling into any holes by walking over the frozen lake.

|  |    |
|:-----|:--------:|
| Action Space   | Discrete(4) |
| Observation Space   |  Discrete(16)  |

## Action and observation space
0: Move left

1: Move down

2: Move right

3: Move up

The observation is a value representing the player’s current position as current_row * nrows + current_col (where both the row and col start at 0).

## Rewards
- Reach goal: +1

- Reach hole: 0

- Reach frozen: 0

## Demo
<video src='../frozen-video.mp4' width=780/>