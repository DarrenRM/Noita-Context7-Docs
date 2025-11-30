---
title: Beamstone Item
category: data/entities/items/pickup
---

# Beamstone Item

This document details the `beamstone.xml` entity, which defines the Beamstone item in Noita.

## Core Components

The Beamstone is an item that can be picked up, thrown, and has unique visual and functional properties.

### `PhysicsBodyComponent`

Manages the physical properties of the Beamstone when it's in the world.

*   **`allow_sleep`**: `1` - Allows the physics body to sleep when inactive.
*   **`is_bullet`**: `1` - Indicates it's a projectile-like entity.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the Beamstone.

*   **`image_file`**: `data/items_gfx/beamstone.png` - The sprite used for the Beamstone in the world.
*   **`material`**: `gem_box2d_opal` - The physics material applied, influencing its interaction with the environment.

### `PhysicsThrowableComponent`

Enables the Beamstone to be thrown by the player.

*   **`max_throw_speed`**: `180` - The maximum speed it can be thrown.
*   **`throw_force_coeff`**: `1.5` - The coefficient determining the force applied when throwing.

### `LuaComponent`

Handles the item's unique logic and behavior.

*   **`script_kick`**: `data/scripts/items/beamstone_kick.lua` - The script file that governs its specific actions.

### `SpriteComponent`

Defines the visual appearance of the Beamstone when held in the player's hand.

*   **`image_file`**: `data/items_gfx/in_hand/beamstone.png` - The sprite for when it's equipped.
*   **`offset_x`, `offset_y`**: `5` - Adjusts the position of the sprite in hand.

### `ItemComponent`

Defines the item's properties within the game's inventory and UI.

*   **`item_name`**: `$item_mega_beam_stone` - The localized name of the item.
*   **`ui_description`**: `$itemdesc_mega_beam_stone` - The localized description.
*   **`ui_sprite`**: `data/ui_gfx/items/beamstone.png` - The sprite used in the UI.
*   **`is_pickable`**: `1` - Allows the player to pick it up.
*   **`is_equipable_forced`**: `1` - Forces it to be equipped when picked up.
*   **`preferred_inventory`**: `QUICK` - Indicates it should go into the quick inventory.

### `UIInfoComponent`

Provides information for the UI, primarily the item's name.

*   **`name`**: `$item_mega_beam_stone` - The name displayed in UI elements.

### `SpriteParticleEmitterComponent`

Responsible for generating visual particle effects associated with the Beamstone.

*   **`sprite_file`**: `data/particles/ray.xml` - The particle effect definition.
*   **`lifetime`**: `1.5` - How long the particles last.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: Defines the initial color of the particles.
*   **`color_change`**: Defines how the color fades over time.
*   **`scale.x`, `scale.y`**: Initial scale of particles.
*   **`scale_velocity.x`, `scale_velocity.y`**: How the scale changes over time.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Controls the rate of particle emission.
*   **`emissive`**: `1` - Particles emit light.
*   **`additive`**: `1` - Particles use additive blending.
*   **`randomize_position`**: Adds slight random offsets to particle spawn points.
*   **`randomize_velocity`**: Adds random velocity to particles.
*   **`velocity_always_away_from_center`**: Particles are pushed away from the emitter's center.

### `AbilityComponent`

Grants the item specific abilities, in this case, the ability to be thrown.

*   **`throw_as_item`**: `1` - Allows the item to be thrown.

### `LightComponent`

Adds a light source to the Beamstone.

*   **`radius`**: `12` - The radius of the light.
*   **`r`, `g`, `b`**: Defines the color of the light.
*   **`fade_out_time`**: `0.1` - How quickly the light fades.