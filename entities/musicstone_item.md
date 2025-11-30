---
title: Musicstone Item
category: entities
---

# Musicstone Item

This document details the `musicstone.xml` entity, which defines the Musicstone item in Noita.

## Core Attributes

The Musicstone is an item that can be picked up and thrown. When held, it emits particles and light, and affects the game's music based on its proximity to danger.

### `Entity` Tags

*   `hittable`: Can be hit by projectiles or other entities.
*   `teleportable_NOT`: Cannot be teleported.
*   `item_physics`: Behaves like a physics-enabled item.
*   `item_pickup`: Can be picked up by the player.
*   `moon_energy`: Related to moon energy mechanics.

### `PhysicsBodyComponent`

Defines the physical properties of the Musicstone when it's in the world.

*   `allow_sleep`: `1` (Allows the physics body to sleep when inactive).
*   `is_bullet`: `1` (Treats it as a projectile for physics interactions).
*   `auto_clean`: `0` (Does not automatically clean up the physics body).
*   `on_death_leave_physics_body`: `1` (Leaves a physics body behind when destroyed).
*   `hax_fix_going_through_ground`: `1` (A fix for potential ground clipping issues).

### `PhysicsImageShapeComponent`

Determines the visual representation and collision shape of the Musicstone.

*   `image_file`: `data/items_gfx/musicstone.png` (The sprite used for the item's physical form).
*   `material`: `gem_box2d_turquoise` (The physics material, influencing friction and other properties).

### `PhysicsThrowableComponent`

Enables the Musicstone to be thrown.

*   `max_throw_speed`: `180`
*   `throw_force_coeff`: `1.5`

## Effects and Visuals

### `MusicEnergyAffectorComponent`

This component is responsible for the Musicstone's effect on the game's music.

*   `energy_target`: `1.0` (The target value for music energy).
*   `trigger_danger_music`: `1` (Triggers danger music when conditions are met).
*   `is_enemy`: `0` (Indicates this is not an enemy effect).
*   `fog_of_war_threshold`: `255` (Likely related to how visibility affects the music).

### `SpriteParticleEmitterComponent` (Notes)

Emits small musical notes when the item is held.

*   `sprite_file`: `data/particles/note_$[1-4].xml` (Uses a set of note sprites).
*   `lifetime`: `1.5` (Duration of each particle).
*   `color`: `r="0.8" g="1" b="1" a="1"` (Light blue/white color).
*   `color_change`: `a="-1"` (Alpha fades out).
*   `emission_interval_min_frames`/`max_frames`: `15`/`30` (Controls the rate of emission).
*   `count_min`/`max`: `1`/`1` (Emits one particle at a time).
*   `randomize_velocity`: Emits particles with a spread of velocities.

### `SpriteParticleEmitterComponent` (Ray)

Emits a "ray" effect, likely a visual indicator of its energy.

*   `sprite_file`: `data/particles/ray.xml`
*   `lifetime`: `1.5`
*   `color`: `r="1" g="0.5" b="1" a="1.0"` (Pinkish color).
*   `color_change`: `a="-3.5"` (Alpha fades out quickly).
*   `scale_velocity`: `x="-0.3" y="3"` (Particles expand and shrink).
*   `emission_interval_min_frames`/`max_frames`: `3`/`6`
*   `emissive`: `1` (Emits light).
*   `additive`: `1` (Adds to existing light).
*   `velocity_always_away_from_center`: `1` (Particles move outwards).

### `LightComponent`

Provides a light source when the item is in the world or held.

*   `radius`: `12`
*   `r`, `g`, `b`: `255`, `255`, `255` (White light).
*   `fade_out_time`: `0.1`

## Item Properties

### `ItemComponent`

Defines the item's identity and behavior within the inventory system.

*   `item_name`: `$item_musicstone` (Localization key for the item's name).
*   `ui_description`: `$itemdesc_musicstone` (Localization key for the item's description).
*   `ui_sprite`: `data/ui_gfx/items/musicstone.png` (The sprite used in the UI).
*   `is_pickable`: `1` (Can be picked up).
*   `is_equipable_forced`: `1` (Can be equipped directly).
*   `preferred_inventory`: `QUICK` (Defaults to the quick inventory).

### `AbilityComponent`

Grants the item the ability to be thrown.

*   `ui_name`: `$item_musicstone` (Name displayed in ability UI).
*   `throw_as_item`: `1` (Allows it to be thrown as an item).

### `UIInfoComponent`

Provides basic UI information.

*   `name`: `$item_musicstone` (Localization key for the name).