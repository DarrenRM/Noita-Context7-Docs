---
title: Contact Damage Enemy Perk
category: entities
---

# Contact Damage Enemy Perk

This entity defines a perk that applies contact damage to enemies when the player is near them. It's designed to be attached to the player character.

## Key Components

### InheritTransformComponent
This component ensures the perk's transform is inherited from its parent, typically the player.

*   `_tags`: "enabled_in_hand" - Indicates this perk is active when held or equipped.
*   `use_root_parent`: "1" - The transform is based on the player's root.
*   `Transform`:
    *   `position.x`: "0"
    *   `position.y`: "-4" - Slightly offsets the perk's effect area relative to the player.

### AreaDamageComponent
This component handles the application of damage to nearby entities.

*   `aabb_min.x`, `aabb_min.y`, `aabb_max.x`, `aabb_max.x`: "-16", "-16", "16", "16" - Defines a square area of effect around the player (32x32 pixels).
*   `damage_per_frame`: "0.14" - The amount of damage dealt per frame to entities within the area.
*   `update_every_n_frame`: "1" - The damage is applied every frame.
*   `entities_with_tag`: "prey" - Only applies damage to entities tagged as "prey" (typically enemies).
*   `damage_type`: "DAMAGE_MELEE" - The type of damage inflicted.

### LuaComponent
This component links to a Lua script that likely handles the logic for activating and managing the perk's effects.

*   `script_source_file`: "data/scripts/perks/contact_damage.lua" - The path to the associated Lua script.
*   `execute_every_n_frame`: "10" - The Lua script's logic is executed every 10 frames.

### SpriteComponent
This component defines the visual representation of the perk, likely an indicator.

*   `_enabled`: "1" - The sprite is active.
*   `image_file`: "data/particles/area_indicator_032_purple.png" - The image used for the indicator.
*   `offset_x`, `offset_y`: "16", "16" - Offsets the sprite's position.
*   `z_index`: "1.1" - Controls the rendering layer.
*   `never_ragdollify_on_death`: "1" - Prevents the sprite from ragdolling when the entity dies.