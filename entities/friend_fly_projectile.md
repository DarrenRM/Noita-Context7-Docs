---
title: Friend Fly Projectile
category: entities
---

# Friend Fly Projectile

This document details the configuration of the "Friend Fly" projectile entity in Noita, focusing on its behavior, appearance, and interactions.

## Entity Definition

The core entity definition for the Friend Fly projectile.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player,hittable,mortal,summon_player"
   >
   <!-- ... other components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Inherits default projectile naming.
*   **`tags`**: `projectile_player`, `hittable`, `mortal`, `summon_player` - Defines its classification and interactions.

## Base Projectile Configuration

Inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
      gravity_y="50"
      air_friction="2"
      mass="0.03"
      >
    </VelocityComponent>
</Base>
```

*   **`gravity_y`**: `50` - Applies a moderate downward gravitational pull.
*   **`air_friction`**: `2` - Medium air resistance.
*   **`mass`**: `0.03` - Low mass, contributing to its projectile nature.

## Homing Component

Enables the projectile to track its target.

```xml
<HomingComponent
    homing_targeting_coeff="10.0"
    homing_velocity_multiplier="1.0"
    detect_distance="300"
    just_rotate_towards_target="0"
    target_who_shot="1"
>
</HomingComponent>
```

*   **`homing_targeting_coeff`**: `10.0` - Strong homing capability.
*   **`detect_distance`**: `300` - Range at which it can detect targets.
*   **`target_who_shot`**: `1` - The projectile will attempt to home in on the entity that fired it.

## Projectile Component

Defines the specific behaviors and properties of the Friend Fly projectile.

```xml
<ProjectileComponent 
    _enabled="1" 
    lob_min="0.5"
    lob_max="0.7"
    speed_min="50"
    speed_max="150"
    friction="0"
    direction_random_rad="0.8"
    on_death_explode="1"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    lifetime="1800"
    damage="0.0"
    lifetime_randomness="100"
    bounce_always="1"
    bounces_left="10"
    bounce_energy="1.0"
    knockback_force="0.4"
    physics_impulse_coeff="1200"
    damage_every_x_frames="30"
    >
    <!-- ... damage_by_type and config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`/`lob_max`**: `0.5`/`0.7` - Controls the arc of the projectile.
*   **`speed_min`/`speed_max`**: `50`/`150` - Defines the projectile's speed range.
*   **`direction_random_rad`**: `0.8` - Introduces some randomness in its initial trajectory.
*   **`on_death_explode`**: `1` - Explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion will not harm the entity that fired it.
*   **`lifetime`**: `1800` - The projectile exists for a long duration.
*   **`damage`**: `0.0` - The projectile itself deals no direct damage.
*   **`bounce_always`**: `1` - The projectile will always bounce.
*   **`bounces_left`**: `10` - Can bounce up to 10 times.
*   **`bounce_energy`**: `1.0` - Retains full energy upon bouncing.
*   **`knockback_force`**: `0.4` - Applies a small knockback effect.
*   **`damage_every_x_frames`**: `30` - Damage is applied periodically.

### Damage By Type

Specifies damage dealt to different entity types.

```xml
<damage_by_type
    melee="0.4"
    >
</damage_by_type>
```

*   **`melee`**: `0.4` - Deals a small amount of "melee" damage.

### Explosion Configuration

Details the explosion effect upon death or lifetime expiry.

```xml
<config_explosion
    damage="0"
    camera_shake="0" 
    explosion_radius="1"
    load_this_entity="data/entities/particles/swarm_poof.xml"
    hole_enabled="1" 
    spark_material="plasma_fading_pink"
    >
</config_explosion>
```

*   **`damage`**: `0` - The explosion itself does not deal damage.
*   **`explosion_radius`**: `1` - Small explosion radius.
*   **`load_this_entity`**: `data/entities/particles/swarm_poof.xml` - Spawns a "swarm poof" particle effect.
*   **`hole_enabled`**: `1` - Creates a small hole in surfaces.
*   **`spark_material`**: `plasma_fading_pink` - Defines the material for any sparks generated.

## Sprite Component

Defines the visual representation of the projectile.

```xml
<SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/friend_fly.xml" 
    has_special_scale="1"
    special_scale_x="1"
     >
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/friend_fly.xml` - Links to the sprite definition.

## Audio Component

Handles sound effects for the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_smg">
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank.
*   **`event_root`**: `player_projectiles/bullet_smg` - Sets the base sound event.

## Particle Emitter Component

Generates cosmetic particles, likely for a trail effect.

```xml
<ParticleEmitterComponent 
    emitted_material_name="spark_purple_bright"
    gravity.y="0"
    x_vel_min="-3"
    x_vel_max="3"
    y_vel_min="-3"
    y_vel_max="3"
    count_min="1"
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.3"
    is_trail="1"
    emit_cosmetic_particles="1"
    fade_based_on_lifetime="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `spark_purple_bright` - The type of particle emitted.
*   **`is_trail`**: `1` - Indicates this emitter creates a trail.
*   **`emit_cosmetic_particles`**: `1` - Emits particles for visual effect only.

## Damage Model Component

Defines the projectile's health and how it's damaged.

```xml
<DamageModelComponent
    hp="1.5"
    >
</DamageModelComponent>
```

*   **`hp`**: `1.5` - The projectile has a small amount of health.

## Hitbox Component

Defines the projectile's collision area.

```xml
<HitboxComponent 
    _enabled="1" 
    aabb_min_x="-6" 
    aabb_max_x="6" 
    aabb_min_y="-4" 
    aabb_max_y="4" 
    is_enemy="1" 
    is_player="0" >
</HitboxComponent>
```

*   **`aabb_min_x`/`aabb_max_x`**: `-6`/`6` - Defines the horizontal bounds of the hitbox.
*   **`aabb_min_y`/`aabb_max_y`**: `-4`/`4` - Defines the vertical bounds of the hitbox.
*   **`is_enemy`**: `1` - The hitbox is considered an enemy for targeting purposes.

## Audio Loop Component

Plays a continuous sound effect while the projectile is active.

```xml
<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="player_projectiles/fly/movement_loop"
    auto_play="1">
</AudioLoopComponent>
```

*   **`event_name`**: `player_projectiles/fly/movement_loop` - The specific sound event for its movement.

## Variable Storage Component

Stores custom variables for use by scripts or other components.

```xml
<VariableStorageComponent
    name="target"
    value_int="0"
    >
</VariableStorageComponent>

<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/friend_fly.xml"
    >
</VariableStorageComponent>
```

*   **`name="target"`**: Stores an integer value, likely for tracking its target.
*   **`name="projectile_file"`**: Stores the path to this entity's XML file.

## Lua Component

Links to an external Lua script for custom logic.

```xml
<LuaComponent
    script_source_file="data/scripts/projectiles/friend_fly.lua"
    execute_every_n_frame="15"
    >
</LuaComponent>
```

*   **`script_source_file`**: `data/scripts/projectiles/friend_fly.lua` - The path to the associated Lua script.
*   **`execute_every_n_frame`**: `15` - The script logic runs every 15 frames.