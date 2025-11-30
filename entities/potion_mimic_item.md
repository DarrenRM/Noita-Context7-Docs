---
title: Potion Mimic Item
category: entities
---

# Potion Mimic Item

This document describes the `potion_mimic.xml` entity, which represents a special type of potion in Noita that mimics other potions.

## Core Functionality

The Potion Mimic is an item that, when picked up, will transform into a random potion. This is achieved through its `LuaComponent` which triggers scripts on various events.

## Key Components and Attributes

### `UIInfoComponent`

*   **`name`**: `$item_potion_mimic` - The internal name for the UI and game systems.

### `PhysicsBodyComponent`

*   **`is_bullet`**: `1` - Allows the item to interact with physics as a projectile.
*   **`hax_fix_going_through_ground`**: `1` - A specific physics adjustment.

### `PhysicsImageShapeComponent`

*   **`image_file`**: `data/items_gfx/potion_normals.png` - The visual asset used for the mimic's default appearance.
*   **`material`**: `potion_glass_box2d` - The physics material defining its interaction properties.

### `ItemComponent`

*   **`item_name`**: `$item_potion_mimic` - Links to the UI name.
*   **`stats_count_as_item_pick_up`**: `0` - This item does not count towards the player's item pickup statistics.
*   **`play_pick_sound`**: `0` - No specific sound is played when this item is picked up.

### `LuaComponent`

This is the core of the mimic's behavior. It executes Lua scripts to handle its transformation.

*   **`script_physics_body_modified`**: `data/scripts/items/potion_mimic.lua` - Script executed when the physics body is modified.
*   **`script_item_picked_up`**: `data/scripts/items/potion_mimic.lua` - Script executed when the player picks up the item. This is where the transformation logic likely resides.
*   **`script_collision_trigger_hit`**: `data/scripts/items/potion_mimic.lua` - Script executed when a collision trigger is hit.
*   **`execute_times`**: `1` - The scripts are intended to execute only once.

### `CollisionTriggerComponent`

*   **`width`**, **`height`**, **`radius`**: `30` - Defines the trigger area for detecting player interaction.
*   **`required_tag`**: `player_unit` - The trigger only activates when the player is involved.

### `LightComponent`

*   **`r`, `g`, `b`**: `255, 255, 255` - Emits white light.
*   **`radius`**: `64` - The range of the light.

### `SpriteParticleEmitterComponent`

This component defines a particle effect that appears around the mimic, likely a visual indicator of its magical nature.

*   **`sprite_file`**: `data/particles/ray.xml` - Uses a ray-like particle.
*   **`lifetime`**: `1.5` - The duration of the particle effect.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 0.5, 1, 1.0` - Initial color (pinkish-white).
*   **`color_change.a`**: `-3.5` - The alpha value decreases over time, making particles fade out.
*   **`scale_velocity.x`, `scale_velocity.y`**: `-0.3, 3` - Particles shrink horizontally and grow vertically.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `3, 6` - Controls the rate of particle emission.
*   **`emissive`, `additive`**: `1` - Particles are emissive and use additive blending for a glowing effect.
*   **`randomize_velocity`**: Various settings to give particles a randomized outward burst.

### `PotionComponent`

*   **`custom_color_material`**: `magic_liquid_hp_regeneration` - This attribute is interesting. While the mimic transforms into a *random* potion, this component might influence the *initial* visual appearance or a default state before transformation, or it could be a remnant from a previous iteration. The actual transformation logic is handled by the Lua script.