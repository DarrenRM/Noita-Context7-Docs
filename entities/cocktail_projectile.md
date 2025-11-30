---
title: Cocktail Projectile
category: entities
---

# Cocktail Projectile

This document details the configuration of a "Cocktail" projectile entity in Noita, focusing on its physical properties, potion mechanics, and item-related attributes.

## Core Components

### Physics Components

These components define the physical behavior of the projectile.

*   **`PhysicsBodyComponent`**:
    *   `is_bullet`: `1` (Indicates it's a projectile).
    *   `allow_sleep`: `1` (Allows the body to sleep when not in motion).
    *   `linear_damping`, `angular_damping`: `0` (No damping applied).
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/items_gfx/potion_normals.png` (Visual representation).
    *   `material`: `potion_glass_box2d` (Physics material).
*   **`PhysicsThrowableComponent`**:
    *   `max_throw_speed`: `180`
    *   `throw_force_coeff`: `1.5`
*   **`ProjectileComponent`**:
    *   `lifetime`: `-1` (Indefinite lifetime unless destroyed by other means).
    *   `penetrate_entities`: `1` (Can pass through entities).
*   **`VelocityComponent`**: Standard velocity component for movement.

### Potion Logic Components

These components govern the behavior of the potion's contents and effects.

*   **`PotionComponent`**:
    *   `spray_velocity_coeff`: `75` (Controls the velocity of sprayed liquid).
*   **`MaterialInventoryComponent`**: Defines the materials contained within the potion and how they behave upon death or damage.
    *   `on_death_spill`: `1` (Materials spill out when the entity dies).
    *   `leak_on_damage_percent`: `1` (Materials leak when damaged).
    *   `leak_pressure_min`: `0.07` to `0.1` (Minimum pressure for leakage).
    *   **`count_per_material_type`**:
        *   `Material material="oil" count="200"`
        *   `Material material="liquid_fire_weak" count="201"`
*   **`MaterialSuckerComponent`**:
    *   `barrel_size`: `401`
    *   `num_cells_sucked_per_frame`: `0` (Not designed to suck materials).
*   **`DamageModelComponent`**: Defines how the projectile itself can deal damage and its resistances.
    *   `hp`: `0.5` (Low health).
    *   `materials_damage`: `1` (Can damage entities with specific materials).
    *   `materials_that_damage`: `lava` (Damages entities that are lava).
    *   `materials_how_much_damage`: `0.001` (Low damage amount).
    *   `fire_damage_amount`: `0.2` (Deals fire damage).
*   **`ExplodeOnDamageComponent`**: Configures the explosion behavior.
    *   `explode_on_death_percent`: `1` (Explodes upon death).
    *   `explode_on_damage_percent`: `0` (Does not explode when damaged).
    *   **`config_explosion`**:
        *   `damage`: `2.5`
        *   `camera_shake`: `20`
        *   `explosion_radius`: `20`
        *   `explosion_sprite`: `data/particles/explosion_032.xml`
        *   `load_this_entity`: `data/entities/particles/particle_explosion/main_small.xml`
        *   `audio_event_name`: `explosions/cocktail`
        *   `physics_explosion_power.max`: `5`
        *   `sparks_count_min`/`max`: `10`/`20`
        *   `stains_enabled`: `1`
*   **`PhysicsBodyCollisionDamageComponent`**:
    *   `speed_threshold`: `80.0` (Deals damage on collision above this speed).
*   **`LuaComponent`**:
    *   `script_death`: `data/scripts/items/potion_glass_break_temporary.lua` (Script executed on death).

### Item Components

These components define the entity's behavior as an item that can be held and used.

*   **`SpriteComponent`**:
    *   `image_file`: `data/items_gfx/potion.png` (Sprite when held in hand).
    *   `_enabled`: `0` (Likely disabled by default, controlled by other tags).
*   **`ItemComponent`**:
    *   `item_name`: `$item_cocktail` (Internal name).
    *   `is_pickable`: `1`
    *   `is_equipable_forced`: `1`
    *   `ui_sprite`: `data/ui_gfx/items/potion.png` (UI icon).
    *   `ui_description`: `$item_description_potion` (UI description).
    *   `preferred_inventory`: `QUICK`
*   **`AbilityComponent`**:
    *   `throw_as_item`: `1` (Can be thrown as an item).
*   **`UIInfoComponent`**:
    *   `name`: `$item_cocktail` (Name displayed in UI).