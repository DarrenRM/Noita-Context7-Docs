---
title: Player Amulet and Hat Logic
category: scripts
---

# Player Amulet and Hat Logic

This script handles the logic for enabling specific player components (amulets and hats) based on persistent game flags.

## Core Functionality

The script checks for the presence of certain persistent flags and, if found, enables corresponding components on the player entity.

### Persistent Flags and Enabled Components

| Persistent Flag           | Enabled Component Tag | Description                                                                 |
| :------------------------ | :-------------------- | :-------------------------------------------------------------------------- |
| `secret_amulet`           | `player_amulet`       | Enables the player's secret amulet.                                         |
| `secret_amulet_gem`       | `player_amulet_gem`   | Enables a special gem effect on the player's amulet.                        |
| `secret_hat`              | `player_hat2`         | Enables a specific secret hat for the player.                               |

### Conditional Hat Activation

The `secret_hat` is conditionally activated based on a combination of two other persistent flags:

*   `moon_is_sun`
*   `darkmoon_is_darksun`

If both of these flags are true, the `secret_hat` flag is added, which then triggers the enabling of the `player_hat2` component.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()

-- Enable secret amulet if the flag is set
if HasFlagPersistent( "secret_amulet" ) then
	EntitySetComponentsWithTagEnabled( entity_id, "player_amulet", true )
end

-- Enable secret amulet gem if the flag is set
if HasFlagPersistent( "secret_amulet_gem" ) then
	EntitySetComponentsWithTagEnabled( entity_id, "player_amulet_gem", true )
end

-- Conditionally add the secret hat flag
if HasFlagPersistent( "moon_is_sun" ) and HasFlagPersistent( "darkmoon_is_darksun" ) then
	AddFlagPersistent( "secret_hat" )
end

-- Enable secret hat if the flag is set
if HasFlagPersistent( "secret_hat" ) then
	EntitySetComponentsWithTagEnabled( entity_id, "player_hat2", true )
end
```