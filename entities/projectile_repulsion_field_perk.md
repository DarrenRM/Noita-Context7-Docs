---
title: Projectile Repulsion Field Perk
category: entities
---

---

# Projectile Repulsion Field Perk

This entity defines the "Projectile Repulsion Field" perk in Noita. When acquired, it creates a field around the player that repels projectiles.

## Key Components

### InheritTransformComponent

This component handles the positioning of the entity relative to the player.

*   **`only_position="1"`**: Indicates that only the position is inherited, not rotation or scale.
*   **`Transform`**:
    *   **`position.x="0"`**: The entity is positioned directly in front of the player horizontally.
    *   **`position.y="-8"`**: The entity is positioned slightly above the player vertically.

### LuaComponent

This component links the entity to a Lua script that governs its behavior.

*   **`script_source_file="data/scripts/perks/projectile_repulsion.lua"`**: Specifies the Lua script responsible for the repulsion field's logic.
*   **`execute_every_n_frame="2"`**: The script's logic will be executed every 2 frames, providing a relatively smooth and responsive effect.

## Associated Script

The behavior of the projectile repulsion field is managed by the script located at `data/scripts/perks/projectile_repulsion.lua`. This script likely contains the logic for detecting incoming projectiles and applying a force to push them away from the player.