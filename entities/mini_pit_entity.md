---
title: Mini Pit Entity
category: entities
---

# Mini Pit Entity

This document details the configuration of the "Mini Pit" entity in Noita, focusing on its AI, physics, and combat attributes for modding purposes.

## Core Components

The Mini Pit is a flying, aggressive creature that attacks from range. It utilizes a `Base` entity for its core functionality, inheriting from `base_enemy_flying.xml`.

### PhysicsAIComponent

Controls the creature's movement and AI-driven physics.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `target_vec_max_len`  | `15.0`  | Maximum length of the target vector for movement.                           |
| `force_coeff`         | `20.0`  | Coefficient for applying force to movement.                                 |
| `force_max`           | `100`   | Maximum force that can be applied.                                          |
| `torque_coeff`        | `50`    | Coefficient for applying torque (rotational force).                         |
| `torque_max`          | `50.0`  | Maximum torque that can be applied.                                         |
| `damage_deactivation_probability` | `30` | Percentage chance to deactivate AI upon taking damage.                      |
| `damage_deactivation_time_min` | `20` | Minimum duration (frames) of AI deactivation after taking damage.           |
| `damage_deactivation_time_max` | `60` | Maximum duration (frames) of AI deactivation after taking damage.           |

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

| Attribute           | Value | Description                                     |
| :------------------ | :---- | :---------------------------------------------- |
| `allow_sleep`       | `1`   | Allows the body to enter a sleep state.         |
| `angular_damping`   | `0.02`| Resistance to rotational movement.              |
| `linear_damping`    | `0`   | Resistance to linear movement.                  |
| `on_death_leave_physics_body` | `1` | Leaves a physics body behind upon death.      |

### PhysicsShapeComponent

Defines the collision shape of the entity.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `is_circle` | `1`   | The shape is a circle.                          |
| `radius_x`  | `8`   | Radius along the X-axis.                        |
| `radius_y`  | `8`   | Radius along the Y-axis.                        |
| `friction`  | `0.0` | Friction coefficient.                           |
| `restitution` | `0.3` | Bounciness of the shape.                        |

### LightComponent

Adds a light source to the entity.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `radius`  | `200` | The radius of the light.                        |
| `r`       | `135` | Red component of the light color.               |
| `g`       | `10`  | Green component of the light color.             |
| `b`       | `180` | Blue component of the light color.              |

## Inherited Components (from `base_enemy_flying.xml`)

### AnimalAIComponent

Governs the creature's behavior and combat AI.

| Attribute                     | Value   | Description                                                                 |
| :---------------------------- | :------ | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault` | The default job assigned to this creature.                                  |
| `dont_counter_attack_own_herd`| `1`     | Prevents counter-attacking members of its own herd.                         |
| `attack_ranged_min_distance`  | `0`     | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`  | `50`    | Maximum distance for ranged attacks.                                        |
| `creature_detection_range_x`  | `300`   | Detection range for creatures on the X-axis.                                |
| `creature_detection_range_y`  | `300`   | Detection range for creatures on the Y-axis.                                |
| `sense_creatures`             | `1`     | Enables sensing of other creatures.                                         |
| `attack_ranged_enabled`       | `1`     | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `0`     | Disables melee attacks.                                                     |
| `can_fly`                     | `1`     | Allows the creature to fly.                                                 |
| `needs_food`                  | `0`     | The creature does not require food.                                         |
| `attack_ranged_entity_file`   | `...orb_purple.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_frames_between`| `10`    | Frames between consecutive ranged attacks.                                  |
| `aggressiveness_min`          | `30`    | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `60`    | Maximum aggressiveness level.                                               |

### DamageModelComponent

Defines the creature's health and damage resistances/vulnerabilities.

| Attribute               | Value         | Description                                                                 |
| :---------------------- | :------------ | :-------------------------------------------------------------------------- |
| `hp`                    | `16`          | Hit points of the creature.                                                 |
| `ragdoll_material`      | `meat_slime`  | Material used for the ragdoll upon death.                                   |
| `blood_material`        | `blood_fungi` | Material for blood splatters.                                               |
| `blood_spray_material`  | `blood_fungi` | Material for blood spray.                                                   |
| `fire_probability_of_ignition` | `0` | Probability of igniting from fire.                                          |
| `air_needed`            | `0`           | Does not require air to survive.                                            |
| `blood_sprite_directional` | `...purple_$[1-3].xml` | Sprite file for directional blood splatters.                                |
| `blood_sprite_large`    | `...purple_$[1-3].xml` | Sprite file for large blood splatters.                                      |

#### damage_multipliers

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.3`      |
| `projectile`| `0.3`      |
| `explosion` | `0.4`      |
| `electricity`| `0.1`      |
| `fire`      | `0`        |

### PathFindingComponent

Handles pathfinding and movement logic.

| Attribute             | Value | Description                                     |
| :-------------------- | :---- | :---------------------------------------------- |
| `distance_to_reach_node_x` | `20` | Distance threshold to consider a node reached (X). |
| `distance_to_reach_node_y` | `20` | Distance threshold to consider a node reached (Y). |
| `frames_to_get_stuck` | `120` | Frames before considering the creature stuck.   |
| `can_jump`            | `0`   | Cannot jump.                                    |
| `can_fly`             | `1`   | Can fly.                                        |

### GenomeDataComponent

Defines genetic traits and ecological role.

| Attribute       | Value   | Description                                     |
| :-------------- | :------ | :---------------------------------------------- |
| `herd_id`       | `slimes`| Identifier for the creature's herd.             |
| `food_chain_rank`| `7`     | Position in the food chain.                     |
| `is_predator`   | `1`     | This creature is a predator.                    |

### CharacterPlatformingComponent

Controls character-specific movement parameters.

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `jump_velocity_y` | `0`   | Vertical jump velocity.                         |
| `run_velocity`  | `24`  | Horizontal movement speed.                      |

### HitboxComponent

Defines the entity's hitbox for interactions.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `aabb_max_x`| `8`   | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y`| `8`   | Maximum Y-coordinate of the bounding box.       |
| `aabb_min_x`| `-8`  | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y`| `-8`  | Minimum Y-coordinate of the bounding box.       |

### CharacterDataComponent

General character data.

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `mass`          | `1.9` | Mass of the character.                          |

## Visuals and Other Components

### SpriteComponent (Main)

Defines the primary visual representation of the Mini Pit.

| Attribute       | Value   | Description                                     |
| :-------------- | :------ | :---------------------------------------------- |
| `image_file`    | `...minipit.png` | Path to the sprite image.                   |
| `offset_x`      | `8`     | X-axis offset for the sprite.                   |
| `offset_y`      | `8`     | Y-axis offset for the sprite.                   |
| `has_special_scale` | `1` | Enables special scaling.                        |
| `special_scale_x` | `1` | X-axis scale factor.                            |

### CellEaterComponent

Allows the entity to consume cells.

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `radius`        | `9`   | The radius within which it eats cells.          |
| `eat_probability` | `100` | Probability of eating cells (100% here).        |

## Minion Tentacles

The Mini Pit spawns with three "minion tentacles" which are instances of `minion_tentacle.xml`. Their positions are offset relative to the Mini Pit.

```xml
<Entity>
  <Base file="data/entities/animals/special/verlet_chains/minion_tentacle.xml">
    <InheritTransformComponent>
      <Transform position.x="-2" position.y="-2" />
    </InheritTransformComponent>
  </Base>
</Entity>
<Entity>
  <Base file="data/entities/animals/special/verlet_chains/minion_tentacle.xml">
    <InheritTransformComponent>
      <Transform position.x="2" position.y="-2" />
    </InheritTransformComponent>
  </Base>
</Entity>
<Entity>
  <Base file="data/entities/animals/special/verlet_chains/minion_tentacle.xml">
    <InheritTransformComponent>
      <Transform position.x="0" position.y="2" />
    </InheritTransformComponent>
  </Base>
</Entity>
```