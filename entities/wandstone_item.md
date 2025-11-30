---
title: Wandstone Item
category: entities
---

# Wandstone Item

This document details the `wandstone.xml` entity, which represents the Wandstone item in Noita. This item grants the player the ability to edit wands anywhere and has unique material conversion properties.

## Core Components

### `PhysicsBodyComponent`
Manages the physical properties of the Wandstone when it's in the world.
- `is_bullet`: `1` (Indicates it can be a projectile)
- `auto_clean`: `0` (Prevents automatic removal)
- `hax_fix_going_through_ground`: `1` (A fix for physics glitches)

### `PhysicsImageShapeComponent`
Defines the visual shape and material of the Wandstone's physical representation.
- `image_file`: `data/items_gfx/goldnugget_01.png` (Uses a gold nugget graphic for its physical form)
- `material`: `gem_box2d_turquoise` (Specifies the physics material)

### `PhysicsThrowableComponent`
Enables the Wandstone to be thrown.
- `max_throw_speed`: `180`
- `throw_force_coeff`: `1.5`

### `ItemComponent`
Defines the Wandstone as an item within the game.
- `item_name`: `$item_wandstone` (Localized name)
- `ui_description`: `$itemdesc_wandstone` (Localized description)
- `ui_sprite`: `data/ui_gfx/items/wandstone.png` (Sprite used in UI)
- `is_pickable`: `1`
- `is_equipable_forced`: `1` (Can be equipped directly)
- `preferred_inventory`: `QUICK` (Defaults to the quick inventory)

## Special Abilities

### `GameEffectComponent`
Grants the primary effect of the Wandstone.
- `effect`: `EDIT_WANDS_EVERYWHERE` (Allows wand editing from anywhere)
- `frames`: `-1` (Effect is permanent while held)

### `MagicConvertMaterialComponent`
Allows the Wandstone to convert liquids.
- `from_material_tag`: `[liquid_common]` (Converts common liquids)
- `to_material`: `magic_liquid_mana_regeneration` (Converts to mana regeneration liquid)
- `radius`: `64` (Conversion radius)
- `loop`: `1` (Continues conversion)

## Visuals and Effects

### `SpriteComponent`
Defines the sprite when the Wandstone is held in hand.
- `image_file`: `data/items_gfx/wandstone.png`
- `_enabled`: `0` (This sprite is likely overridden by particle effects or other visual components when active)

### `SpriteParticleEmitterComponent`
Creates visual particles when the Wandstone is active.
- `sprite_file`: `data/particles/ray.xml` (Uses ray-like particles)
- `lifetime`: `1.5`
- `color`: `(1, 1, 1, 0.5)` (White, semi-transparent)
- `scale_velocity.y`: `4` (Particles expand vertically)
- `emissive`: `1`, `additive`: `1` (Particles emit light)
- `randomize_position`, `randomize_velocity`: Various settings for particle spread.

### `ParticleEmitterComponent`
Emits cosmetic particles for visual flair.
- `emitted_material_name`: `plasma_fading`
- `x_vel_min/max`, `y_vel_min/max`: Controls particle velocity.
- `area_circle_radius`: `5`
- `gravity.y`: `35`
- `lifetime_min/max`: `1.0` to `5.0`
- `emit_cosmetic_particles`: `1`
- `render_on_grid`: `1`