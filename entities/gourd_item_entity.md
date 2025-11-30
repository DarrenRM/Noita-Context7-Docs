---
title: Gourd Item Entity
category: entities
---

# Gourd Item Entity

This document details the `gourd.xml` entity, which defines the behavior and appearance of the Gourd item in Noita.

## Core Functionality

The Gourd is a throwable item that, upon impact or destruction, triggers an explosion with a regeneration aura effect.

## Key Components and Attributes

### Physics Components

*   **`PhysicsBodyComponent`**: Defines the physical properties of the gourd.
    *   `hax_fix_going_through_ground="1"`: A specific fix to prevent the gourd from falling through the ground.
*   **`PhysicsImageShapeComponent`**: Renders the gourd's visual representation.
    *   `image_file="data/items_gfx/gourd.png"`: The texture used for the gourd in the game world.
    *   `material="meat_fruit"`: The material type, influencing interactions with other game elements.
*   **`PhysicsThrowableComponent`**: Enables the gourd to be thrown.
    *   `max_throw_speed="180"`: The maximum speed the gourd can be thrown.
    *   `throw_force_coeff="1.5"`: The coefficient determining the force applied when throwing.
*   **`ProjectileComponent`**: Configures the gourd as a projectile.
    *   `penetrate_entities="1"`: Allows the projectile to pass through other entities.
*   **`VelocityComponent`**: Manages the gourd's velocity.

### Damage and Destruction

*   **`DamageModelComponent`**: Defines how the gourd takes damage and its resistance.
    *   `hp="0.6"`: The health of the gourd before it's considered "damaged" for destruction purposes.
    *   `fire_damage_amount="0.2"`: The amount of fire damage it can sustain.
    *   `materials_that_damage="lava"`: Specifies materials that will damage the gourd.
    *   `materials_how_much_damage="0.001"`: The rate at which specified materials damage the gourd.
*   **`ExplodeOnDamageComponent`**: Manages the explosion effect when the gourd is damaged or destroyed.
    *   `explode_on_death_percent="1"`: Guarantees an explosion upon reaching 0 HP.
    *   `physics_body_destruction_required="0.4"`: The percentage of HP loss required to trigger physics body destruction.
    *   **`config_explosion`**: Detailed configuration for the explosion.
        *   `damage="0"`: The explosion itself does no direct damage.
        *   `camera_shake="10"`: The intensity of camera shake upon explosion.
        *   `explosion_radius="3"`: The radius of the explosion effect.
        *   `load_this_entity="data/entities/projectiles/deck/regeneration_aura.xml"`: **Crucially, this loads the entity responsible for the regeneration aura effect.**
        *   `physics_explosion_power.min="5"` / `physics_explosion_power.max="10"`: The minimum and maximum force of the physics-based explosion.
        *   `sparks_enabled="1"`: Enables visual sparks from the explosion.
        *   `spark_material="bone"`: The material used for the sparks.
        *   `stains_enabled="1"`: Enables stain effects on the ground.
*   **`PhysicsBodyCollisionDamageComponent`**: Deals damage to other entities upon collision if the gourd reaches a certain speed.
    *   `speed_threshold="60.0"`: The speed at which collision damage is applied.

### Item Properties

*   **`SpriteComponent`**: Defines the visual representation of the gourd when held by the player.
    *   `image_file="data/items_gfx/in_hand/gourd_in_hand.png"`: The texture for the gourd in the player's hand.
*   **`ItemComponent`**: General properties for the item.
    *   `item_name="$item_gourd"`: The internal name for the item, linked to localization.
    *   `is_pickable="1"`: Allows the player to pick up the item.
    *   `is_equipable_forced="1"`: Can be equipped directly.
    *   `ui_sprite="data/ui_gfx/items/gourd.png"`: The icon displayed in the UI.
    *   `ui_description="$itemdesc_gourd"`: The descriptive text for the item, linked to localization.
    *   `preferred_inventory="QUICK"`: Suggests the quick inventory for storage.
*   **`UIInfoComponent`**: Provides information for the UI.
    *   `name="$item_gourd"`: The displayed name in the UI.
*   **`AbilityComponent`**: Grants abilities to the item.
    *   `throw_as_item="1"`: Allows the item to be thrown.
*   **`AudioComponent`**: Manages sound effects.
    *   `event_root="player_projectiles/throwable"`: Specifies the audio event category for throwing sounds.

## Summary

The Gourd is a simple throwable item with a unique secondary effect: it spawns a regeneration aura upon destruction. Its physics properties allow it to be thrown and interact with the environment, while its damage and explosion components are configured to trigger the regeneration effect without causing direct damage itself.