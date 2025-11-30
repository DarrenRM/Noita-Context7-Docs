---
title: Confuse Spirit Entity
category: entities
---

# Confuse Spirit Entity

This document details the configuration of the Confuse Spirit entity in Noita, focusing on attributes relevant to AI-assisted modding.

## Core Entity Definition

The Confuse Spirit is a flying enemy with unique behavioral and visual properties.

```xml
<Entity tags="glue_NOT" name="$animal_confusespirit" >
  <!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

### AnimalAIComponent

This component governs the AI behavior of the Confuse Spirit.

| Attribute                     | Value      | Description                                                              |
| :---------------------------- | :--------- | :----------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault` | The default job assigned to this creature.                               |
| `escape_if_damaged_probability` | `35`       | Percentage chance to flee when damaged.                                  |
| `creature_detection_range_x`  | `250`      | Horizontal range for detecting other creatures.                          |
| `creature_detection_range_y`  | `250`      | Vertical range for detecting other creatures.                            |
| `food_material`               | `meat`     | The material this creature considers food.                               |
| `needs_food`                  | `0`        | Whether the creature requires food to survive (0 = no).                  |
| `sense_creatures`             | `1`        | Whether the creature can sense other creatures.                          |
| `can_fly`                     | `1`        | Enables flight capabilities.                                             |

### DamageModelComponent

Defines the health and damage resistances of the Confuse Spirit.

| Attribute                 | Value   | Description                                                              |
| :------------------------ | :------ | :----------------------------------------------------------------------- |
| `hp`                      | `3`     | Hit points of the entity.                                                |
| `ragdoll_material`        | `rock_static_glow` | The material used for its ragdoll when defeated.                         |
| `blood_material`          | `plasma_fading` | The material used for blood effects.                                     |
| `air_needed`              | `0`     | Whether the creature requires air to survive (0 = no).                   |

#### Damage Multipliers

Specific resistances and vulnerabilities to different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `projectile`| `0.8`      |
| `explosion` | `0.8`      |
| `electricity`| `1`        |
| `fire`      | `0`        |
| `slice`     | `0.4`      |
| `holy`      | `1.2`      |

### SpriteComponent

Controls the visual appearance of the Confuse Spirit.

| Attribute     | Value                               | Description                                                              |
| :------------ | :---------------------------------- | :----------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/confusespirit.xml` | Path to the sprite definition file.                                      |
| `additive`    | `1`                                 | Enables additive blending for the sprite.                                |
| `emissive`    | `1`                                 | Makes the sprite emissive (glows).                                       |

### PathFindingComponent

Defines how the entity navigates the game world.

| Attribute         | Value | Description                                                              |
| :---------------- | :---- | :----------------------------------------------------------------------- |
| `can_swim_on_surface` | `1`   | Allows swimming on the surface of liquids.                               |
| `can_fly`         | `1`   | Enables flight navigation.                                               |
| `can_jump`        | `0`   | Disables jumping.                                                        |

### GenomeDataComponent

Provides genetic information, influencing its role in the ecosystem.

| Attribute           | Value   | Description                                                              |
| :------------------ | :------ | :----------------------------------------------------------------------- |
| `herd_id`           | `ghost` | Identifier for its herd or type.                                         |
| `food_chain_rank`   | `15`    | Its position in the food chain.                                          |
| `is_predator`       | `1`     | Indicates if it's a predator.                                            |

### LuaComponent

Attaches custom Lua scripting for advanced behaviors.

| Attribute         | Value                                       | Description                                                              |
| :---------------- | :------------------------------------------ | :----------------------------------------------------------------------- |
| `script_source_file` | `data/scripts/animals/spirit_aura_confuse.lua` | The Lua script file responsible for its unique effects.                  |
| `execute_every_n_frame` | `101`                                       | How often the script is executed (in frames).                            |

### ParticleEmitterComponent

Manages the visual particle effects emitted by the Confuse Spirit.

| Attribute                     | Value   | Description                                                              |
| :---------------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name`       | `spark` | The material of the particles being emitted.                             |
| `gravity.y`                   | `0.0`   | Vertical gravity applied to particles.                                   |
| `lifetime_min`                | `0.5`   | Minimum lifetime of emitted particles.                                   |
| `lifetime_max`                | `1.2`   | Maximum lifetime of emitted particles.                                   |
| `count_min`                   | `20`    | Minimum number of particles emitted per burst.                           |
| `count_max`                   | `30`    | Maximum number of particles emitted per burst.                           |
| `area_circle_radius.min`      | `32`    | Minimum radius of the emission area.                                     |
| `area_circle_radius.max`      | `72`    | Maximum radius of the emission area.                                     |
| `velocity_always_away_from_center` | `240`   | Particles are always pushed away from the center at this velocity.       |

## Other Notable Components

*   **Base:** Inherits common properties from `base_enemy_flying.xml`.
*   **ItemChestComponent:** Defines loot drop properties.
*   **HitboxComponent & CharacterDataComponent:** Define the entity's collision and physical boundaries.
*   **AudioComponent & AudioLoopComponent:** Manage sound effects and looping audio.
*   **GameEffectComponent:** Applies a permanent freeze protection effect.