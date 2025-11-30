---
title: ConfigLaser Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ConfigLaser
category: modding-wiki
---

# ConfigLaser Documentation for AI-Assisted Modding

This documentation outlines the configuration options for the `ConfigLaser` component in Noita, which is crucial for understanding and modifying projectile behavior. By leveraging this information, AI-assisted modding tools can more effectively generate or modify projectile properties, enabling deeper customization of gameplay mechanics.

## Understanding ConfigLaser

The `ConfigLaser` component is a fundamental part of how projectiles function in Noita. It dictates various aspects of a projectile's behavior, from its visual appearance and damage to its trajectory and special effects. Modifying these settings allows for the creation of unique weapons, spells, and environmental hazards.

### Core Properties

The `ConfigLaser` component accepts a variety of properties that define its behavior. These are typically defined within an entity's XML definition.

#### Damage and Impact

*   **damage**: The base damage dealt by the projectile.
*   **damage_type**: The type of damage (e.g., `damage_type_fire`, `damage_type_explosion`).
*   **impact_material**: The material the projectile interacts with upon impact (e.g., `material_stone`, `material_water`).
*   **impact_effect**: The visual effect that plays on impact.

#### Projectile Behavior

*   **speed**: The initial speed of the projectile.
*   **lifetime**: The duration in seconds the projectile exists before despawning.
*   **gravity**: The effect of gravity on the projectile (0 for no gravity, 1 for standard gravity).
*   **pierce_by_material**: A list of materials the projectile can pierce.
*   **pierce_by_entity**: A list of entity types the projectile can pierce.
*   **bounce_count**: The number of times the projectile can bounce off surfaces.
*   **bounce_friction**: The reduction in speed after each bounce.
*   **muzzle_velocity_factor**: A multiplier for the initial velocity based on the caster's velocity.

#### Visuals and Effects

*   **sprite_file**: The path to the sprite texture for the projectile.
*   **sprite_animation_file**: The path to an animation definition file for the sprite.
*   **trail_effect**: A visual effect that follows the projectile.
*   **light_color**: The color of the light emitted by the projectile.
*   **light_radius**: The radius of the light emitted by the projectile.

#### Special Behaviors

*   **is_homing**: Whether the projectile tracks the nearest enemy.
*   **homing_speed**: The speed at which the projectile turns towards its target.
*   **homing_delay**: The delay before homing behavior activates.
*   **explosion_radius**: The radius of an explosion effect if the projectile explodes.
*   **explosion_damage**: The damage dealt by the explosion.
*   **explosion_damage_type**: The damage type of the explosion.
*   **explosion_effect**: The visual effect of the explosion.

### Example XML Configuration

Here's a simplified example of how `ConfigLaser` might be configured within an entity's XML:

```xml
<Entity name="my_custom_laser">
    <ConfigLaser
        damage="10"
        damage_type="damage_type_magic"
        speed="50"
        lifetime="5"
        sprite_file="data/projectiles/laser.png"
        trail_effect="effects/trail_magic.xml"
        is_homing="1"
        homing_speed="10"
    />
    <Lifetime
        lifetime="5"
    />
</Entity>
```

## Modifying Projectiles with AI

AI-assisted modding can leverage the detailed properties of `ConfigLaser` to:

*   **Generate New Projectiles**: Create entirely new projectile types with unique damage, speed, visual effects, and behaviors.
*   **Tweak Existing Projectiles**: Modify the parameters of existing projectiles to alter their effectiveness or introduce new gameplay dynamics.
*   **Balance Gameplay**: Analyze and adjust projectile properties to maintain game balance.
*   **Create Complex Spell Combinations**: Combine `ConfigLaser` properties with other components and Lua scripting for intricate spell effects.

### Key Components for AI Interaction

When working with AI for projectile modding, focus on these components and their interaction with `ConfigLaser`:

*   **ConfigLaser**: The primary component for defining projectile characteristics.
*   **Lifetime**: Controls how long a projectile exists.
*   **Damage**: Defines the damage dealt.
*   **Explosion**: If the projectile has an explosion effect.
*   **Homing**: For projectiles that track targets.
*   **Lua Scripting**: For advanced behaviors and dynamic modifications.

### Resources for AI Modding

*   **[Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)**: Essential for understanding how to interact with game objects and components via scripting.
*   **Noita Modding Discord**: A community resource for asking questions and getting help.
*   **Existing Mod Files**: Studying the XML and Lua files of existing mods can provide valuable insights into common practices and advanced techniques.

By understanding and systematically applying the information within this documentation, AI models can become powerful tools for Noita modders, enabling the creation of a vast array of custom projectile behaviors.