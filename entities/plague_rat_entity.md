---
title: Plague Rat Entity
category: entities
---

# Plague Rat Entity

This document details the configuration of the "Plague Rat" entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Entity Configuration

The Plague Rat is a basic enemy entity with specific AI behaviors and physical properties.

```xml
<Entity tags="rat,poopstone_immunity,plague_rat" name="$animal_rat">
  <!-- ... other components ... -->
</Entity>
```

### Key Tags:

*   `rat`: Identifies the entity as a rat.
*   `poopstone_immunity`: Grants immunity to damage from poopstones.
*   `plague_rat`: A specific tag for this variant of rat.

## Base Enemy Configuration

The `Base` component inherits from `base_enemy_basic.xml`, providing fundamental enemy functionalities.

```xml
<Base file="data/entities/base_enemy_basic.xml" >
  <!-- ... components ... -->
</Base>
```

### AnimalAIComponent:

This component governs the rat's artificial intelligence and combat behavior.

| Attribute                      | Value   | Description                                                              |
| :----------------------------- | :------ | :----------------------------------------------------------------------- |
| `preferred_job`                | `JobDefault` | The default job assigned to the AI.                                      |
| `attack_melee_damage_min`      | `0.35`  | Minimum damage dealt by melee attacks.                                   |
| `attack_melee_damage_max`      | `0.45`  | Maximum damage dealt by melee attacks.                                   |
| `needs_food`                   | `1`     | Indicates if the AI requires food.                                       |
| `attack_ranged_enabled`        | `0`     | Ranged attacks are disabled.                                             |
| `attack_dash_enabled`          | `1`     | Dash attacks are enabled.                                                |
| `attack_dash_damage`           | `0.35`  | Damage dealt by dash attacks.                                            |
| `attack_melee_max_distance`    | `14`    | Maximum distance for melee attacks.                                      |
| `aggressiveness_min`           | `100`   | Minimum aggressiveness level.                                            |
| `aggressiveness_max`           | `100`   | Maximum aggressiveness level.                                            |
| `dont_counter_attack_own_herd` | `1`     | Prevents counter-attacking members of its own herd.                      |

### DamageModelComponent:

Defines the rat's health and damage-related properties.

| Attribute                 | Value | Description                               |
| :------------------------ | :---- | :---------------------------------------- |
| `ragdoll_filenames_file`  | `data/ragdolls/plague_rat/filenames.txt` | Specifies the ragdoll files for the rat. |
| `hp`                      | `0.7` | Hit points of the rat.                    |
| `fire_probability_of_ignition` | `0` | Probability of igniting from fire.        |

### SpriteComponent:

Controls the visual representation of the rat.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/plague_rat.xml` | Path to the sprite's XML definition.      |

### PathFindingComponent:

Manages the entity's pathfinding capabilities.

| Attribute             | Value | Description                                     |
| :-------------------- | :---- | :---------------------------------------------- |
| `distance_to_reach_node_x` | `20`  | Horizontal distance to reach a path node.       |
| `distance_to_reach_node_y` | `20`  | Vertical distance to reach a path node.         |
| `frames_to_get_stuck` | `20`  | Frames before considering the AI stuck.         |
| `can_swim_on_surface` | `1`   | Can swim on the surface of liquids.             |
| `can_dive`            | `1`   | Can dive into liquids.                          |
| `can_jump`            | `1`   | Can jump.                                       |

### CharacterPlatformingComponent:

Defines movement parameters for platforming.

| Attribute       | Value | Description                 |
| :-------------- | :---- | :-------------------------- |
| `jump_velocity_y` | `-30` | Vertical jump force.        |
| `run_velocity`  | `40`  | Horizontal movement speed.  |

### HitboxComponent:

Defines the collision boundaries for the entity.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x` | `-5.5` | Minimum X-axis bounding box coordinate.   |
| `aabb_max_x` | `5.5`  | Maximum X-axis bounding box coordinate.   |
| `aabb_min_y` | `-1.4` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_y` | `3.5`  | Maximum Y-axis bounding box coordinate.   |
| `is_enemy`  | `1`   | Marks the hitbox as belonging to an enemy. |

### CharacterDataComponent:

Provides general character data, including mass and collision.

| Attribute            | Value | Description                               |
| :------------------- | :---- | :---------------------------------------- |
| `collision_aabb_min_x` | `-3.5` | Minimum X-axis collision box coordinate.  |
| `collision_aabb_max_x` | `3.5`  | Maximum X-axis collision box coordinate.  |
| `collision_aabb_min_y` | `-3`   | Minimum Y-axis collision box coordinate.  |
| `collision_aabb_max_y` | `3`    | Maximum Y-axis collision box coordinate.  |
| `mass`               | `0.4` | The mass of the character.                |

## Lua Components

These components enable custom scripting for the Plague Rat.

### Plague Rat Poof Effect:

This Lua script handles a visual effect when the rat is defeated.

```xml
<LuaComponent
    script_source_file="data/scripts/perks/plague_rats_rat_poof.lua"
    execute_every_n_frame="800"
    >
</LuaComponent>
```

*   `script_source_file`: Points to the Lua script responsible for the poof effect.
*   `execute_every_n_frame`: This value seems unusually high for a poof effect, suggesting it might be a placeholder or intended for a different trigger.

### Plague Rats Initialization:

This script is executed once when the entity is added to the game.

```xml
<LuaComponent
    script_source_file="data/scripts/perks/plague_rats_init.lua"
    execute_on_added="1"
    remove_after_executed="1"
    >
</LuaComponent>
```

*   `script_source_file`: The script for initializing plague rat behaviors.
*   `execute_on_added`: Ensures the script runs only when the entity is spawned.
*   `remove_after_executed`: The script is removed after its initial execution.

## Audio Component

Defines the sound effects associated with the rat.

```xml
<AudioComponent
    file="data/audio/Desktop/animals.bank"
    event_root="animals/rat" >
</AudioComponent>
```

*   `file`: Specifies the audio bank containing the sounds.
*   `event_root`: The base event name for rat sounds.

## Special Properties

### No Gold Drop:

This `VariableStorageComponent` with the tag `no_gold_drop` prevents the rat from dropping gold.

```xml
<VariableStorageComponent
    _tags="no_gold_drop">
</VariableStorageComponent>
```

### Protection Effect:

The entity has a temporary protection effect applied upon spawning.

```xml
<Entity>
    <GameEffectComponent
        effect="PROTECTION_ALL"
        frames="20"
    >
    </GameEffectComponent >
</Entity>
```

*   `effect`: `PROTECTION_ALL` grants immunity to all damage.
*   `frames`: The duration of the protection effect in frames (20 frames is less than a second).