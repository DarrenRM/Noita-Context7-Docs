---
title: PlatformShooterPlayerComponent
source: https://noita.wiki.gg/wiki/Documentation:PlatformShooterPlayerComponent
category: modding-wiki
---

# PlatformShooterPlayerComponent

This documentation page details the `PlatformShooterPlayerComponent` in Noita, a crucial component for understanding and modifying player projectile behavior. Modders can leverage this information to customize how players shoot, the types of projectiles they fire, and their associated properties, opening up possibilities for new weapons and gameplay mechanics.

## Overview

The `PlatformShooterPlayerComponent` is responsible for managing the player's shooting capabilities. It dictates how projectiles are spawned, their initial properties, and the logic behind firing. Understanding this component is key to creating custom weapons, modifying existing ones, or implementing unique shooting mechanics for player characters.

## Component Properties

The `PlatformShooterPlayerComponent` has several properties that can be modified to alter shooting behavior. These properties are typically defined within the `data/entities/player.xml` file or in custom entity files.

### `shoot_type`

Determines the type of projectile that is shot. This usually refers to a projectile entity ID.

### `shoot_offset_x` and `shoot_offset_y`

These values define the offset from the player's center where the projectile is spawned.

### `shoot_angle`

The initial angle of the projectile when fired.

### `shoot_delay`

The time in seconds between shots.

### `projectile_speed`

The initial speed of the spawned projectile.

### `projectile_damage`

The base damage of the projectile.

### `projectile_mana_cost`

The amount of mana consumed when firing this projectile.

### `projectile_lifetime`

The duration in seconds the projectile exists before despawning.

### `projectile_material`

The material of the projectile.

### `projectile_entity_file`

The path to the XML file defining the projectile entity.

## Example Usage

Here's an example of how `PlatformShooterPlayerComponent` might be configured within an entity file:

```xml
<Entity name="player">
    <PlatformShooterPlayerComponent
        shoot_type="PROJECTILE_BULLET"
        shoot_offset_x="10"
        shoot_offset_y="5"
        shoot_angle="0"
        shoot_delay="0.2"
        projectile_speed="50"
        projectile_damage="5"
        projectile_mana_cost="1"
        projectile_lifetime="2"
        projectile_material="wood"
        projectile_entity_file="data/entities/projectiles/bullet.xml"
    />
    <!-- Other components -->
</Entity>
```

## Modifying Projectile Behavior

Modders can create new projectile entities and reference them using the `shoot_type` or `projectile_entity_file` properties. This allows for a wide range of customization, from simple bullet variations to complex magical projectiles.

### Creating Custom Projectiles

To create a custom projectile, you would typically define a new entity in its own XML file, for example, `data/entities/projectiles/my_custom_projectile.xml`. This entity would then be referenced by the `PlatformShooterPlayerComponent`.

```xml
<!-- data/entities/projectiles/my_custom_projectile.xml -->
<Entity name="my_custom_projectile">
    <ProjectileComponent
        _tags="projectile"
        damage="10"
        speed="60"
        lifetime="3"
        knockback_force="1"
        owner_is_player="1"
        on_death_spawn_entity="data/entities/particles/impact_spark.xml"
    />
    <SpriteComponent
        image_file="data/sprites/projectiles/custom_bullet.png"
        offset_x="0"
        offset_y="0"
    />
    <MaterialComponent
        material="magic"
    />
</Entity>
```

Then, in the player's entity file, you would update the `PlatformShooterPlayerComponent` to use this new projectile:

```xml
<Entity name="player">
    <PlatformShooterPlayerComponent
        shoot_type="MY_CUSTOM_PROJECTILE" <!-- Or use projectile_entity_file -->
        shoot_offset_x="12"
        shoot_offset_y="6"
        shoot_angle="5"
        shoot_delay="0.15"
        projectile_speed="60"
        projectile_damage="10"
        projectile_mana_cost="2"
        projectile_lifetime="3"
        projectile_material="magic"
        projectile_entity_file="data/entities/projectiles/my_custom_projectile.xml"
    />
    <!-- Other components -->
</Entity>
```

## Related Components and Concepts

*   **ProjectileComponent**: Defines the core behavior of a projectile once it has been spawned.
*   **SpriteComponent**: Used to define the visual appearance of projectiles.
*   **MaterialComponent**: Assigns a material to a projectile, affecting its interactions with the environment.
*   **Entity System**: Understanding how entities and components interact is fundamental to Noita modding.

For more information on the Lua API and other modding concepts, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) documentation.