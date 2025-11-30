---
title: Plague Rats Perk Initialization
category: scripts
---

# Plague Rats Perk Initialization

This script initializes the "Plague Rats" perk, dynamically adjusting the stats of the spawned rat entities based on game progression and the number of times the perk has been picked up.

## Key Attributes and Logic

The core functionality revolves around calculating `extra_hp` and `extra_damage` for the spawned rats. These values are influenced by two main factors:

1.  **Vertical Position (`pos_y`):** As the player descends deeper into the world (higher `pos_y` values), the rats gain more health and damage.
2.  **Perk Pickup Count:** Each time the "Plague Rats" perk is acquired, the rats receive a further boost to their health and damage.

### Stat Calculation

*   **`extra_hp`**:
    *   Base increase: `pos_y * 0.0002`
    *   Perk pickup bonus: `(pickup_count - 1) * 4`
    *   Ensures a minimum of 0 health bonus.

*   **`extra_damage`**:
    *   Base increase: `pos_y * 0.0001`
    *   Perk pickup bonus: `(pickup_count - 1) * 0.4`
    *   Ensures a minimum of 0 damage bonus.

### Entity Modifications

The script targets the spawned rat entity and modifies its components:

*   **`DamageModelComponent`**:
    *   The `max_hp` and `hp` values are increased by the calculated `extra_hp`.

*   **`AnimalAIComponent`**:
    *   The `attack_melee_damage_min`, `attack_melee_damage_max`, and `attack_dash_damage` are all increased by the calculated `extra_damage`.

### Tag Removal

The spawned rat entity has the following tags removed to prevent unintended interactions:

*   `"homing_target"`
*   `"enemy"`

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local flag_name = "RAT_PERK_TOTAL_COUNT"
local pickup_count = tonumber( GlobalsGetValue( flag_name, "0" ) )
	
local extra_hp = math.max( 0, pos_y * 0.0002 ) + ( pickup_count - 1 ) * 4
local extra_damage = math.max( 0, pos_y * 0.0001 ) + ( pickup_count - 1 ) * 0.4
	
EntityRemoveTag( entity_id, "homing_target" )
EntityRemoveTag( entity_id, "enemy" )

edit_component( entity_id, "DamageModelComponent", function(comp,vars)
	local hp = tonumber(ComponentGetValue( comp, "hp"))
	vars.max_hp = hp + extra_hp
	vars.hp = hp + extra_hp
end)

edit_component( entity_id, "AnimalAIComponent", function(comp,vars)
	local damage_min = tonumber(ComponentGetValue( comp, "attack_melee_damage_min"))
	local damage_max = tonumber(ComponentGetValue( comp, "attack_melee_damage_max"))
	local damage_dash = tonumber(ComponentGetValue( comp, "attack_dash_damage"))
	
	vars.attack_melee_damage_min = damage_min + extra_damage
	vars.attack_melee_damage_max = damage_max + extra_damage
	vars.attack_dash_damage = damage_dash + extra_damage
end)
```