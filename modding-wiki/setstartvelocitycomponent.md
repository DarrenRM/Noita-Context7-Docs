---
title: SetStartVelocityComponent
source: https://noita.wiki.gg/wiki/Documentation:SetStartVelocityComponent
category: modding-wiki
---

# SetStartVelocityComponent

This documentation page explains the `SetStartVelocityComponent` in Noita, a crucial component for controlling the initial velocity of entities when they are spawned. Understanding and utilizing this component is essential for modders who wish to create custom behaviors, projectiles, or environmental effects that require precise initial movement.

## Overview

The `SetStartVelocityComponent` allows you to define the starting velocity of an entity. This is particularly useful for projectiles, enemies, or any spawned object that needs to move in a specific direction and at a specific speed immediately upon creation. By modifying the `x` and `y` values within this component, you can dictate the initial trajectory and force applied to the entity.

## Component Properties

The `SetStartVelocityComponent` has the following properties that can be configured:

*   **x**: The initial velocity along the X-axis.
*   **y**: The initial velocity along the Y-axis.

These values are typically floats and represent the velocity in pixels per frame.

## Usage Examples

### Basic Projectile Velocity

To make a projectile shoot straight to the right with a moderate speed, you could configure the component like this:

```xml
<SetStartVelocityComponent x="200" y="0" />
```

In this example, `x="200"` means the projectile will start moving 200 pixels per frame to the right, and `y="0"` means it will have no initial vertical movement.

### Upward Launch

To launch an entity upwards with a significant force:

```xml
<SetStartVelocityComponent x="0" y="-300" />
```

Here, `x="0"` indicates no horizontal movement, and `y="-300"` means the entity will start moving 300 pixels per frame upwards (as negative Y is typically upwards in Noita's coordinate system).

### Diagonal Launch

To launch an entity diagonally upwards and to the right:

```xml
<SetStartVelocityComponent x="150" y="-150" />
```

This configuration provides an initial velocity of 150 pixels per frame to the right and 150 pixels per frame upwards.

## Integration with Entity XML

The `SetStartVelocityComponent` is added to an entity's XML definition. For instance, if you were creating a custom projectile, its XML might look something like this:

```xml
<Entity name="my_custom_projectile">
    <Base file="data/entities/base_projectile.xml" />
    <ProjectileComponent
        damage="5"
        explosion_damage="0"
        explosion_radius="0"
        hit_particles="particle_fx/blood_hit_particle.xml"
        hit_sound="sounds/impact.wav"
        muzzle_velocity="0"
        on_death_particle_force="0 0"
        on_death_particle_count="0"
        on_hit_particle_force="0 0"
        on_hit_particle_count="0"
        pierce_entity="0"
        physics_impulse_force="0"
        reflectable="1"
        speed="0"
        stain_radius="0"
        stain_type="blood"
        throwable="0"
        >
        <tag name="projectile" />
        <tag name="homing" />
        <tag name="ignores_gravity" />
    </ProjectileComponent>
    <SetStartVelocityComponent x="300" y="0" />
    <Sprite name="sprite_id_here" />
</Entity>
```

**Note:** In the example above, `muzzle_velocity` and `speed` within `ProjectileComponent` might be overridden or influenced by `SetStartVelocityComponent`. It's important to test how these interact. Often, `SetStartVelocityComponent` dictates the *initial* velocity, while `ProjectileComponent`'s `speed` might influence ongoing velocity or how the projectile behaves after its initial launch.

## Important Considerations

*   **Coordinate System:** Remember that in Noita's 2D space, positive X is to the right, and negative Y is upwards.
*   **Interaction with Physics:** The `SetStartVelocityComponent` applies an initial impulse. Other physics components or game mechanics might affect the entity's velocity after this initial application (e.g., gravity, friction, other force components).
*   **Testing:** Always thoroughly test your modifications in-game to ensure the desired behavior. The exact values for velocity might require fine-tuning based on the entity's mass, sprite size, and other game factors.
*   **Lua Scripting:** For more dynamic control over initial velocity, you can often use Lua scripting to set the velocity of an entity at runtime, potentially based on game state or player actions. Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for more details.