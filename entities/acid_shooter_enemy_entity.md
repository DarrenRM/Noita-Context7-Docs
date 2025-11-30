---
title: Acid Shooter Enemy Entity
category: entities
---

# Acid Shooter Enemy Entity

This document details the `acidshooter.xml` entity, defining the properties and behaviors of the Acid Shooter enemy in Noita.

## Core Entity Definition

The Acid Shooter is an enemy entity with the tag `glue_NOT`. Its base behavior is inherited from `base_enemy_flying.xml`.

```xml
<Entity tags="glue_NOT" name="$animal_acidshooter">
  <Base file="data/entities/base_enemy_flying.xml" >
    <!-- ... other components ... -->
  </Base>
  <!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

### AnimalAIComponent

This component governs the AI behavior of the Acid Shooter, primarily its ranged attack capabilities.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `attack_ranged_entity_file`   | `data/entities/projectiles/acidshot.xml` | Specifies the projectile entity used for its ranged attack.                 |
| `attack_ranged_state_duration_frames` | `70`                                | Duration of the attack state in frames.                                     |
| `attack_ranged_enabled`       | `1`                                 | Enables the ranged attack.                                                  |
| `attack_dash_enabled`         | `0`                                 | Disables dashing behavior.                                                  |
| `attack_ranged_frames_between`| `40`                                | Frames to wait between ranged attacks.                                      |
| `attack_ranged_offset_y`      | `0.1`                               | Vertical offset for the ranged attack origin.                               |
| `needs_food`                  | `0`                                 | The entity does not require food.                                           |
| `can_fly`                     | `1`                                 | The entity is capable of flight.                                            |

### SpriteComponent

Defines the visual appearance of the Acid Shooter.

| Attribute   | Value                           | Description                               |
| :---------- | :------------------------------ | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/acidshooter.xml`| Path to the sprite's graphical definition. |
| `alpha`     | `0.5`                           | Transparency level of the sprite.         |

### CharacterDataComponent

Contains physical properties and collision information for the entity.

| Attribute             | Value   | Description                                                              |
| :-------------------- | :------ | :----------------------------------------------------------------------- |
| `collision_aabb_min_x`| `-4.0`  | Minimum X-axis value for the collision bounding box.                     |
| `collision_aabb_max_x`| `4.0`   | Maximum X-axis value for the collision bounding box.                     |
| `collision_aabb_min_y`| `-10`   | Minimum Y-axis value for the collision bounding box.                     |
| `collision_aabb_max_y`| `3`     | Maximum Y-axis value for the collision bounding box.                     |
| `mass`                | `1.2`   | The mass of the entity.                                                  |

### LightComponent

Adds a light source originating from the entity.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `radius`  | `70`  | The radius of the light emitted.          |
| `r`       | `149` | Red component of the light color.         |
| `g`       | `255` | Green component of the light color.       |
| `b`       | `149` | Blue component of the light color.        |

### AudioComponent (Multiple Instances)

The Acid Shooter utilizes several audio components for different sound effects and events.

*   **Main Attack Sound:**
    ```xml
    <AudioComponent
        file="data/audio/Desktop/animals.bank"
        event_root="animals/acidshooter" >
    </AudioComponent>
    ```
*   **Movement Loop:**
    ```xml
    <AudioLoopComponent
        file="data/audio/Desktop/animals.bank"
        event_name="animals/slimy_small/movement_loop"
        set_speed_parameter="1"
        auto_play="1">
    </AudioLoopComponent>
    ```
*   **Illusion Sound:**
    ```xml
    <AudioComponent
        file="data/audio/Desktop/animals.bank"
        event_root="animals/illusion">
    </AudioComponent>
    ```

### LuaComponent

This component enables custom scripting for the entity.

| Attribute           | Value                                | Description                                                              |
| :------------------ | :----------------------------------- | :----------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/animals/illusion_disappear.lua` | The Lua script file that controls the entity's behavior.                 |
| `execute_on_removed`| `1`                                  | The script will execute when the entity is removed.                      |

### LifetimeComponent

Determines how long the entity exists before despawning.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `600` | The entity's lifespan in frames.          |