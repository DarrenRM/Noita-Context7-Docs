---
title: Base Flying Enemy Configuration
category: entities
---

# Base Flying Enemy Configuration

This document outlines the core configuration for a base flying enemy entity in Noita, focusing on its AI, combat, and physical properties.

## Entity Definition

The root `<Entity>` tag defines the entity and its primary tags.

```xml
<Entity tags="teleportable_NOT,enemy,flying" >
```

*   **`teleportable_NOT`**: Prevents this entity from being teleported.
*   **`enemy`**: Identifies the entity as an enemy.
*   **`flying`**: Indicates the entity's ability to fly.

## Base Entity Inheritance

This entity inherits its fundamental properties from `data/entities/base_humanoid.xml`.

```xml
<Base file="data/entities/base_humanoid.xml" >
    <!-- ... components ... -->
</Base>
```

## Key Components

### AnimalAIComponent

Controls the AI behavior of the creature, including its senses, attacks, and movement preferences.

```xml
<AnimalAIComponent
    preferred_job="JobDefault"
    creature_detection_range_x="300"
    creature_detection_range_y="300"
    attack_dash_enabled="0"
    attack_ranged_enabled="1"
    attack_ranged_entity_file="data/entities/projectiles/acidshot.xml"
    attack_ranged_frames_between="40"
    food_material="blood"
    needs_food="1"
    sense_creatures="1"
    can_fly="1"
    aggressiveness_min="1"
    aggressiveness_max="100"
    >
</AnimalAIComponent>
```

*   **`creature_detection_range_x`/`y`**: Defines the horizontal and vertical range for detecting other creatures.
*   **`attack_ranged_enabled`**: Enables ranged attacks.
*   **`attack_ranged_entity_file`**: Specifies the projectile entity used for ranged attacks.
*   **`attack_ranged_frames_between`**: Sets the delay in frames between ranged attacks.
*   **`food_material`**: The material the creature consumes for sustenance.
*   **`needs_food`**: Whether the creature requires food.
*   **`sense_creatures`**: Enables the creature to sense other creatures.
*   **`can_fly`**: Crucial for flying entities, enabling flight capabilities.
*   **`aggressiveness_min`/`max`**: Determines the creature's aggression level.

### DamageModelComponent

Manages the entity's health, damage multipliers, and how it reacts to damage (e.g., blood splatters, ragdolls).

```xml
<DamageModelComponent
    hp="0.5"
    materials_create_messages="1"
    ragdoll_material="meat"
    ragdoll_filenames_file="data/ragdolls/zombie/filenames.txt"
    blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_$[1-3].xml"
    blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_$[1-3].xml"
    blood_spray_material="blood"
    air_needed="1"
    >
    <damage_multipliers
        drill="0.5"
        >
    </damage_multipliers>
</DamageModelComponent>
```

*   **`hp`**: The entity's health points.
*   **`ragdoll_material`**: The material used for the ragdoll when the entity dies.
*   **`blood_sprite_directional`/`large`**: Specifies the particle effects for blood splatters.
*   **`damage_multipliers`**: Allows for specific multipliers against different damage types (e.g., `drill`).

### SpriteComponent

Defines the visual appearance of the entity.

```xml
<SpriteComponent
    image_file="data/enemies_gfx/zombie.xml"
    z_index="-1">
</SpriteComponent>
```

*   **`image_file`**: Points to the graphical asset defining the sprite.
*   **`z_index`**: Controls the rendering order of the sprite.

### PathFindingComponent

Configures how the entity navigates the game world.

```xml
<PathFindingComponent
    distance_to_reach_node_x="10"
    distance_to_reach_node_y="10"
    frames_to_get_stuck="30"
    can_jump="0" >
</PathFindingComponent>
```

*   **`distance_to_reach_node_x`/`y`**: The tolerance for reaching a navigation point.
*   **`frames_to_get_stuck`**: How many frames the entity can be stuck before considering a path failed.
*   **`can_jump`**: Whether the entity can jump. For flying entities, this is typically `0`.

### CharacterPlatformingComponent

Governs the entity's movement physics, including acceleration, gravity, and velocity.

```xml
<CharacterPlatformingComponent
    accel_x="1"
    pixel_gravity="600"
    jump_velocity_y="-8"
    run_velocity="12">
</CharacterPlatformingComponent>
```

*   **`accel_x`**: Horizontal acceleration.
*   **`pixel_gravity`**: The strength of gravity applied to the entity.
*   **`jump_velocity_y`**: The vertical velocity applied when jumping (not typically used for flying entities).
*   **`run_velocity`**: The base horizontal movement speed.

### HitboxComponent

Defines the collision boundaries of the entity.

```xml
<HitboxComponent
    aabb_min_x="-4.5"
    aabb_max_x="4.5"
    aabb_min_y="-5.5"
    aabb_max_y="3"
    >
</HitboxComponent>
```

*   **`aabb_min_x`/`max_x`**: The minimum and maximum X-coordinates of the Axis-Aligned Bounding Box.
*   **`aabb_min_y`/`max_y`**: The minimum and maximum Y-coordinates of the Axis-Aligned Bounding Box.

### CharacterDataComponent

Provides additional character-specific data, including collision and buoyancy offsets.

```xml
<CharacterDataComponent
    climb_over_y="4"
    collision_aabb_min_x="-2.0"
    collision_aabb_max_x="2.0"
    collision_aabb_min_y="-3"
    collision_aabb_max_y="3"
    buoyancy_check_offset_y="-6">
</CharacterDataComponent>
```

*   **`collision_aabb_min_x`/`max_x`/`min_y`/`max_y`**: Defines the precise collision box used for interactions with the environment and other entities.
*   **`buoyancy_check_offset_y`**: The vertical offset used for buoyancy checks.

### CameraBoundComponent

Manages how the entity interacts with the camera's boundaries.

```xml
<CameraBoundComponent
  max_count="20"
  distance="160000">
</CameraBoundComponent>
```

*   **`max_count`**: The maximum number of this entity that can be active within the camera's view.
*   **`distance`**: The maximum distance from the camera at which this entity can exist.