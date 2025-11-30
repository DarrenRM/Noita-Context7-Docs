---
title: Egg Monster Item
category: entities
---

# Egg Monster Item

This document details the `egg_monster.xml` entity, which represents a throwable egg item in Noita that spawns a monster upon breaking.

## Core Functionality

The `egg_monster.xml` entity defines a pickup item with physics properties, damage handling, and a unique behavior upon destruction.

### Key Components

*   **`PhysicsBodyComponent`**: Manages the physical presence of the egg, including its interaction with the game world, damping, and collision properties.
    *   `is_bullet="1"`: Indicates it can be treated as a projectile.
    *   `hax_fix_going_through_ground="1"`: A specific fix for preventing the egg from clipping through the ground.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation of the egg using `egg.png` and assigns it a `bone_box2d` material for physics.
*   **`PhysicsThrowableComponent`**: Enables the egg to be thrown with defined speed and force coefficients.
*   **`DamageModelComponent`**: Handles how the egg takes damage. It has low HP and can be damaged by lava.
    *   `hp="0.6"`: The egg has a low health pool.
    *   `materials_that_damage="lava"`: Lava is the primary material that damages the egg.
    *   `materials_how_much_damage="0.001"`: Lava deals minimal damage per tick.
*   **`ExplodeOnDamageComponent`**: This is the core component for the egg's unique behavior. When its health reaches a certain threshold, it explodes and spawns a new entity.
    *   `explode_on_death_percent="1"`: The explosion occurs when the egg is destroyed.
    *   `physics_body_destruction_required="0.61"`: The explosion is triggered when approximately 61% of the egg's physics body is destroyed.
    *   `load_this_entity="data/entities/projectiles/egg_monster.xml"`: **Crucially, this specifies that upon breaking, the egg will spawn an entity defined in `data/entities/projectiles/egg_monster.xml`.** This is where the actual monster spawning logic resides.
    *   `camera_shake="10"`: The explosion causes significant camera shake.
    *   `explosion_radius="3"`: The explosion has a radius of 3 units.
    *   `physics_explosion_power.min="5"`, `physics_explosion_power.max="10"`: The explosion imparts physics force.
    *   `sparks_enabled="1"`, `spark_material="bone"`: Sparks are generated from the explosion, using the "bone" material.
*   **`ItemComponent`**: Defines the egg as a pickup item.
    *   `item_name="$item_egg"`: The internal name for the item.
    *   `is_pickable="1"`: Allows the player to pick it up.
    *   `is_equipable_forced="1"`: Can be equipped directly.
    *   `ui_sprite="data/ui_gfx/items/egg.png"`: The UI icon for the egg.
    *   `ui_description="$item_description_egg"`: The in-game description.
*   **`AbilityComponent`**: Grants the egg the ability to be thrown as an item.
*   **`SpriteParticleEmitterComponent`**: Creates visual particle effects when the egg is active, contributing to its visual flair.
*   **`AudioComponent`**: Plays sound effects associated with throwing the egg.

## Summary of Key Attributes

| Component                     | Key Attribute(s)