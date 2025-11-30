---
title: Hollow Egg Item
category: entities
---

# Hollow Egg Item

This document details the `egg_hollow.xml` entity, representing a throwable "Hollow Egg" item in Noita.

## Core Functionality

The Hollow Egg is a projectile item with physics-based interactions and a unique explosion effect upon taking sufficient damage.

### Key Components

*   **`PhysicsBodyComponent`**: Defines the physical properties of the egg, including its collision behavior, damping, and how it interacts with the world.
    *   `is_bullet="1"`: Indicates it's a projectile.
    *   `hax_fix_going_through_ground="1"`: A fix to prevent it from falling through terrain.
*   **`PhysicsImageShapeComponent`**: Renders the egg's visual representation in the world using `egg_slime.png`.
    *   `material="bone_box2d"`: Defines the physical material for collision.
*   **`PhysicsThrowableComponent`**: Enables the egg to be thrown with specific speed and force characteristics.
    *   `max_throw_speed="180"`
    *   `throw_force_coeff="1.5"`
*   **`DamageModelComponent`**: Manages the egg's health and how it reacts to damage.
    *   `hp="0.4"`: Low health, making it susceptible to damage.
    *   `materials_damage="lava"`: Takes damage from lava.
    *   `materials_how_much_damage="0.001"`: Low damage taken from materials.
*   **`ExplodeOnDamageComponent`**: Triggers an explosion when the egg's health is depleted.
    *   `explode_on_death_percent="1"`: Guarantees an explosion upon death.
    *   `physics_body_destruction_required="0.61"`: The explosion is triggered when 61% of its physics body is destroyed.
    *   **`config_explosion`**: Defines the parameters of the explosion.
        *   `damage="0.2"`: The damage dealt by the explosion.
        *   `camera_shake="10"`: The intensity of camera shake.
        *   `explosion_radius="3"`: The radius of the explosion.
        *   `physics_explosion_power.min="5"`, `physics_explosion_power.max="10"`: The force of the physics-based explosion.
        *   `sparks_enabled="1"`, `spark_material="bone"`: Generates bone sparks.
*   **`ItemComponent`**: Defines the item's properties for inventory and pickup.
    *   `item_name="$item_egg_hollow"`: The internal name for localization.
    *   `is_pickable="1"`: Can be picked up by the player.
    *   `is_equipable_forced="1"`: Can be equipped.
    *   `ui_sprite="data/ui_gfx/items/egg_slime.png"`: The sprite shown in the UI.
    *   `ui_description="$itemdesc_egg_hollow"`: The internal description for localization.
*   **`AbilityComponent`**: Grants the item projectile-like abilities.
    *   `throw_as_item="1"`: Allows it to be thrown as an item.

### Visuals

*   **World Sprite**: `data/items_gfx/egg_slime.png`
*   **UI Sprite**: `data/ui_gfx/items/egg_slime.png`

### Audio

*   **Sound Bank**: `data/audio/Desktop/projectiles.bank`
*   **Event Root**: `player_projectiles/throwable`