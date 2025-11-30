---
title: Contact Damage Perk
category: entities
---

# Contact Damage Perk

This entity defines the "Contact Damage" perk in Noita, which applies a small amount of melee damage to nearby enemies when the player is in contact with them.

## Key Components

### InheritTransformComponent
This component ensures the perk's visual and functional elements inherit the transform of its parent entity (typically the player).

*   `_tags`: "enabled_in_hand" - Indicates this perk is active when held.
*   `use_root_parent`: "1" - The transform is inherited from the root parent.

### AreaDamageComponent
This is the core component responsible for applying damage.

*   `aabb_min.x`, `aabb_min.y`, `aabb_max.x`, `aabb_max.y`: Defines the damage area's bounding box relative to the entity's position. In this case, it's a 32x32 pixel square centered on the entity.
*   `damage_per_frame`: "0.14" - The amount of damage dealt per frame.
*   `update_every_n_frame`: "1" - The damage calculation is performed every frame.
*   `entities_with_tag`: "enemy" - Only entities tagged as "enemy" will take damage.
*   `damage_type`: "DAMAGE_MELEE" - The type of damage applied.

### LuaComponent
This component executes a Lua script to manage the perk's behavior.

*   `script_source_file`: "data/scripts/perks/contact_damage.lua" - The path to the associated Lua script.
*   `execute_every_n_frame`: "10" - The Lua script runs every 10 frames.

### SpriteComponent
This component defines the visual representation of the perk.

*   `_enabled`: "1" - The sprite is enabled.
*   `image_file`: "data/particles/area_indicator_032_purple.png" - The texture used for the sprite.
*   `offset_x`, `offset_y`: "16" - Offsets the sprite's position.
*   `z_index`: "1.1" - Controls the sprite's rendering order.