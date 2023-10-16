# Deep Reinforcement Learning Projects

Repository for deep reinforcement learning projects made during the completion of [Thomas Simioni's Hugging Face Course](https://huggingface.co/learn/deep-rl-course/unit0/introduction). The following projects were learned and uploaded:

## Frozen Lake (Non-slippery version)
Frozen lake involves crossing a frozen lake from start to goal without falling into any holes by walking over the frozen lake.

|  |    |
|:-----|:--------:|
| Action Space   | Discrete(4) |
| Observation Space   |  Discrete(16)  |

### Action and observation space
0: Move left

1: Move down

2: Move right

3: Move up

The observation is a value representing the player’s current position as current_row * nrows + current_col (where both the row and col start at 0).

### Rewards
- Reach goal: +1

- Reach hole: 0

- Reach frozen: 0

### Demo
<!-- <video src='frozen-video.mp4' width=780/> -->

## Taxi
There are four designated pick-up and drop-off locations (Red, Green, Yellow and Blue) in the 5x5 grid world. The taxi starts off at a random square and the passenger at one of the designated locations.

The goal is move the taxi to the passenger’s location, pick up the passenger, move to the passenger’s desired destination, and drop off the passenger. Once the passenger is dropped off, the episode ends.

The player receives positive rewards for successfully dropping-off the passenger at the correct location. Negative rewards for incorrect attempts to pick-up/drop-off passenger and for each step where another reward is not received.

|  |    |
|:-----|:--------:|
| Action Space   | Discrete(6) |
| Observation Space   |  Discrete(500)  |

### Action and observation space
0: Move south (down)

1: Move north (up)

2: Move east (right)

3: Move west (left)

4: Pickup passenger

5: Drop off passenger

There are 500 discrete states since there are 25 taxi positions, 5 possible locations of the passenger (including the case when the passenger is in the taxi), and 4 destination locations.

Destination on the map are represented with the first letter of the color.

Passenger locations:

0: Red

1: Green

2: Yellow

3: Blue

4: In taxi

Destinations:

0: Red

1: Green

2: Yellow

3: Blue

An observation is returned as an int() that encodes the corresponding state, calculated by ((taxi_row * 5 + taxi_col) * 5 + passenger_location) * 4 + destination

### Rewards
- -1 per step unless other reward is triggered.

- +20 delivering passenger.

- -10 executing “pickup” and “drop-off” actions illegally.

### Demo
<!-- <video src='taxi-video.mp4' width=780/> -->