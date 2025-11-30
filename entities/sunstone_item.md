---
title: Sunstone Item
category: entities
---

# Sunstone Item

This document details the `sunstone.xml` entity, which represents the Sunstone item in Noita. The Sunstone is a unique item with powerful environmental manipulation and damage-dealing capabilities.

## Core Attributes

The Sunstone is defined as an `item_pickup` with several key tags: `hittable`, `teleportable_NOT`, `item_physics`, `seed_b`. It inherits its base functionality from `base_item_projectile.xml`.

## Physics and Visuals

### Physics Components

*   **`PhysicsBodyComponent`**: Manages the physical presence of the Sunstone, allowing it to interact with the game world. Key attributes include `is_bullet="1"` and `hax_fix_going_through_ground="1"`.
*   **`PhysicsKeepInWorldComponent`**: Ensures the Sunstone remains within the game world boundaries.
*   **`PhysicsImageShapeComponent`**: Defines the visual shape and material of the Sunstone.
    *   `image_file`: `data/items_gfx/goldnugget_9px.png`
    *   `material`: `gem_box2d_red_float`
*   **`PhysicsThrowableComponent`**: Enables the Sunstone to be thrown with specific force parameters.
    *   `max_throw_speed`: `180`
    *   `throw_force_coeff`: `1.5`
*   **`VelocityComponent`**: Manages the velocity of the Sunstone.

### Visual Components

*   **`SpriteComponent` (in hand)**:
    *   `image_file`: `data/items_gfx/sunseed_2.png`
    *   `offset_x`: `4`, `offset_y`: `4`
*   **`SpriteComponent` (in world)**:
    *   `image_file`: `data/particles/fog_of_war_hole_big.png`
    *   `fog_of_war_hole`: `1` (This sprite creates a visible hole in the fog of war)

## Item Functionality

### `ItemComponent`

This component defines the Sunstone as an item that can be picked up and used.
*   `item_name`: `$item_seed_c` (Localized name)
*   `ui_description`: `$itemdesc_seed_c` (Localized description)
*   `ui_sprite`: `data/ui_gfx/items/sunseed_2.png` (UI icon)
*   `is_pickable`: `1`
*   `is_equipable_forced`: `1`
*   `preferred_inventory`: `QUICK`

### `UIInfoComponent`

Provides UI information, primarily the item name.
*   `name`: `$item_seed_c`

### `AbilityComponent`

Grants the Sunstone the ability to be thrown as an item.
*   `throw_as_item`: `1`

## Special Effects and Abilities

### `GameEffectComponent`

*   `effect`: `REMOVE_FOG_OF_WAR` (When held, it removes fog of war)
*   `frames`: `-1` (Indicates the effect is permanent while held)

### `AreaDamageComponent`

Deals damage to nearby entities.
*   `aabb_min/max`: Defines the area of effect.
*   `damage_per_frame`: `0.06`
*   `entities_with_tag`: `mortal` (Affects entities tagged as mortal)
*   `death_cause`: `$damage_sun`
*   `damage_type`: `DAMAGE_CURSE`

### `MagicConvertMaterialComponent`

These components are responsible for transforming materials in the environment. The Sunstone has three such components:

1.  **Converts Sand to Fire**:
    *   `from_material_tag`: `[sand_ground]`
    *   `to_material`: `liquid_fire`
    *   `radius`: `72`
    *   `loop`: `1`
2.  **Converts Other Sand to Fire**:
    *   `from_material_tag`: `[sand_other]`
    *   `to_material`: `liquid_fire`
    *   `radius`: `72`
    *   `loop`: `1`
3.  **Ignites Materials**:
    *   `ignite_materials`: `1`
    *   `fan_the_flames`: `1` (Causes a chain reaction of ignition)
    *   `radius`: `72`
    *   `loop`: `1`

### `ParticleEmitterComponent`

Generates cosmetic particles to visually represent the Sunstone's effect.
*   `emitted_material_name`: `spark`
*   `count_min/max`: `1` to `4`
*   `lifetime_min/max`: `1.0` to `5.0`
*   `emission_interval_min_frames/max_frames`: `2` to `5`
*   `render_ultrabright`: `1` (Particles are very bright)

### `MaterialAreaCheckerComponent`

Checks for specific materials within its area and triggers an action.
*   `area_aabb.min/max`: Defines the area of check.
*   `update_every_x_frame`: `36`
*   `material`: `lava`
*   `material2`: `lava` (Checks for lava specifically)

### `LuaComponent`

Executes a Lua script for additional functionality.
*   `script_source_file`: `data/scripts/buildings/sun/spot_2.lua`
*   `execute_every_n_frame`: `10`

### `CameraBoundComponent`

Manages how the camera behaves relative to the Sunstone.
*   `max_count`: `5`
*   `distance`: `2000`