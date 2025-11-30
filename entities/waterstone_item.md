---
title: Waterstone Item
category: entities
---

---

# Waterstone Item

This document details the `waterstone.xml` entity, which defines the Waterstone item in Noita.

## Core Attributes

The Waterstone is an item that can be picked up and used by the player. It has several unique properties related to its interaction with liquids and materials.

### `Entity` Tags

*   `hittable`: Can be damaged by projectiles.
*   `teleportable_NOT`: Cannot be teleported.
*   `item_physics`: Behaves like a physical item in the world.
*   `item_pickup`: Can be picked up by the player.
*   `waterstone`: A custom tag for this specific item.

### `PhysicsBodyComponent`

Manages the physical properties of the Waterstone when it's in the world.

*   `uid`: 1
*   `allow_sleep`: 1 (Allows the physics body to sleep when inactive)
*   `is_bullet`: 1 (Treats it as a projectile for physics purposes)
*   `hax_fix_going_through_ground`: 1 (A fix for potential ground clipping issues)

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the Waterstone.

*   `image_file`: `data/items_gfx/waterstone.png`
*   `material`: `rock_box2d_hard` (Determines its physical interaction properties)

### `PhysicsThrowableComponent`

Controls how the Waterstone behaves when thrown.

*   `max_throw_speed`: 180
*   `throw_force_coeff`: 1.5

### `ItemComponent`

Defines the item's properties for inventory and gameplay.

*   `item_name`: `$item_waterstone` (Localized name)
*   `ui_description`: `$item_description_waterstone` (Localized description)
*   `ui_sprite`: `data/ui_gfx/items/waterstone.png` (Icon for UI)
*   `is_pickable`: 1 (Can be picked up)
*   `is_equipable_forced`: 1 (Can be equipped directly)
*   `preferred_inventory`: `QUICK` (Defaults to the quick inventory slot)

## Game Effects

These components grant the Waterstone its unique abilities.

### `GameEffectComponent` (x2)

*   **Effect 1:**
    *   `effect`: `BREATH_UNDERWATER` (Grants infinite breath underwater)
    *   `frames`: -1 (Effect is permanent while held)
*   **Effect 2:**
    *   `effect`: `STAINS_DROP_FASTER` (Causes stains to spread faster)
    *   `frames`: -1 (Effect is permanent while held)

## Material Conversion

The Waterstone can convert certain materials into others.

### `MagicConvertMaterialComponent` (x4)

These components define the material conversion abilities.

*   **Conversion 1 (Hot to Smoke):**
    *   `from_material_tag`: `[hot]`
    *   `to_material`: `smoke`
    *   `radius`: 64
    *   `loop`: 1 (Continues converting)
*   **Conversion 2 (Lava to Lavarock):**
    *   `from_material_tag`: `[lava]`
    *   `to_material`: `lavarock_static`
    *   `radius`: 64
    *   `loop`: 1
*   **Conversion 3 (Molten to Rock):**
    *   `from_material_tag`: `[molten]`
    *   `to_material`: `rock_static`
    *   `radius`: 64
    *   `loop`: 1
*   **Conversion 4 (Extinguish Fire):**
    *   `extinguish_fire`: 1
    *   `radius`: 64
    *   `loop`: 1

## Visual Effects (VFX)

The Waterstone has several particle emitters for visual flair.

### `SpriteParticleEmitterComponent` (x3)

*   **Ray Effect:**
    *   `sprite_file`: `data/particles/ray.xml`
    *   `lifetime`: 1.5
    *   `color`: Reddish-purple
    *   `scale_velocity.y`: 3 (Scales up over time)
    *   `randomize_velocity`: Significant random velocity applied.
*   **Halo Effect:**
    *   `sprite_file`: `data/particles/waterstone_bubble.xml`
    *   `lifetime`: 0.35
    *   `color`: White with transparency
    *   `gravity.y`: 10 (Slight upward pull)
    *   `emission_interval_min_frames`: 2, `emission_interval_max_frames`: 2 (Frequent emission)
*   **Drops Effect:**
    *   `sprite_file`: `data/particles/waterstone_drop.xml`
    *   `lifetime`: 0.5
    *   `color`: White with transparency
    *   `velocity_always_away_from_center`: 10 (Particles spread outwards)
    *   `randomize_rotation`: Full rotation range.

### `ParticleEmitterComponent` (x2)

These emitters create cosmetic particles.

*   **Water/Sweat Effect:**
    *   `emitted_material_name`: `water`
    *   `gravity.y`: 35 (Falls downwards)
    *   `lifetime_min`: 1.0, `lifetime_max`: 5.0
    *   `emission_interval_min_frames`: 8, `emission_interval_max_frames`: 40
*   **Plasma Fading Effect:**
    *   `emitted_material_name`: `plasma_fading`
    *   `gravity.y`: 35
    *   `lifetime_min`: 1.0, `lifetime_max`: 5.0
    *   `emission_interval_min_frames`: 12, `emission_interval_max_frames`: 60

## Scripting

### `LuaComponent`

*   `script_source_file`: `data/scripts/items/waterstone.lua`
*   `execute_every_n_frame`: 5 (The associated Lua script runs periodically)