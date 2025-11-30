---
title: Radar Moon Perk
category: scripts
---

---

# Radar Moon Perk

This script implements the functionality for the "Radar Moon" perk in Noita. When acquired, it visually indicates the direction and approximate distance to the Moon on the player's screen.

## Key Functionality

### Moon Position Calculation
The script defines the Moon's position in the game world. This is a fixed offset from the player's starting position.

```lua
local moon_x = 0 + 256
local moon_y = -26112 + 256
```

### Indicator Distance
A constant `indicator_distance` is used to determine how far from the player the visual indicator will be drawn.

```lua
local indicator_distance = 32
```

### Directional Vector Calculation
The script calculates a normalized vector pointing from the player's current position towards the Moon's position.

```lua
local dir_x = moon_x - pos_x
local dir_y = moon_y - pos_y

-- sprite positions around character
dir_x,dir_y = vec_normalize(dir_x,dir_y)
```

### Indicator Sprite Creation
A sprite is created at a calculated position relative to the player, along the directional vector towards the Moon, at the specified `indicator_distance`. This sprite serves as the visual marker for the Moon.

```lua
local indicator_x = pos_x + dir_x * indicator_distance
local indicator_y = pos_y + dir_y * indicator_distance

GameCreateSpriteForXFrames( "data/particles/radar_moon.png", indicator_x, indicator_y )
```