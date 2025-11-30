---
title: Decoy Projectile
category: entities
---

# Decoy Projectile

This entity defines a projectile that acts as a decoy, mimicking the player's appearance and behavior for a short duration. It has no damage and is primarily used for distraction.

## Key Components

### VelocityComponent
Controls the projectile's movement and interaction with physics.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `gravity_y`      | `400`   | The force of gravity applied on the Y-axis.     |
| `air_friction`   | `0.55`  | Resistance to movement in the air.              |
| `terminal_velocity` | `1000`  | The maximum speed the projectile can reach.     |

### SimplePhysicsComponent
Enables basic physics interactions for the projectile.

### GenomeDataComponent
Defines the entity's role within the game's ecosystem.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `herd_id`        | `player`| Identifies this entity as belonging to the player's group. |
| `food_chain_rank`| `20`    | Its position in the food chain (higher is more dominant). |
| `is_predator`    | `1`     | Indicates that this entity is a predator.       |

### HitboxComponent
Defines the collision area of the projectile.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `aabb_max_x`     | `3`     | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y`     | `0`     | Maximum Y-coordinate of the bounding box.       |
| `aabb_min_x`     | `-3`    | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y`     | `-16`   | Minimum Y-coordinate of the bounding box.       |
| `is_enemy`       | `0`     | Not considered an enemy.                        |
| `is_item`        | `0`     | Not an item.                                    |
| `is_player`      | `1`     | This hitbox is treated as the player's.         |

### PathFindingGridMarkerComponent
Used by the pathfinding system.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `marker_offset_y`| `-3`    | Vertical offset for the pathfinding marker.     |
| `marker_work_flag`| `8`     | Flag used by the pathfinding system.            |

### LightComponent
Adds a light source to the projectile.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `r`, `g`, `b`    | `50`, `100`, `255` | RGB color values for the light.                 |
| `radius`         | `64`    | The radius of the light's influence.            |
| `fade_out_time`  | `0.75`  | Time it takes for the light to fade out.        |

### SpriteComponent
Defines the visual appearance of the projectile.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `_tags`          | `character` | Tags associated with the sprite.                |
| `alpha`          | `0.5`   | Transparency of the sprite (50%).               |
| `image_file`     | `data/enemies_gfx/player.xml` | The sprite image to use (player's graphics). |
| `next_rect_animation`, `rect_animation` | `stand` | The animation state for the sprite.             |
| `offset_x`, `offset_y` | `6`, `15` | Offset of the sprite from its origin.           |

### SpriteAnimatorComponent
Handles sprite animations.

### HotspotComponent
Defines specific points on the sprite for interactions.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `_tags`          | `cape_root` | Tags for this hotspot.                          |
| `sprite_hotspot_name` | `cape`  | The name of the hotspot on the sprite.          |

### ProjectileComponent
Core component for projectile behavior.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `speed_min`, `speed_max` | `0`, `0` | The projectile has no initial speed.            |
| `on_death_gfx_leave_sprite` | `0` | No sprite is left upon death.                   |
| `die_on_low_velocity` | `0` | Does not die from low velocity.                 |
| `on_collision_die` | `0` | Does not die on collision.                      |
| `on_lifetime_out_explode` | `0` | Does not explode when lifetime ends.            |
| `on_death_explode` | `0` | Does not explode upon death.                    |
| `create_shell_casing` | `0` | Does not create shell casings.                  |
| `velocity_sets_rotation` | `0` | Velocity does not affect rotation.              |
| `lifetime`       | `200`   | The projectile exists for 200 frames.           |
| `damage`         | `0`     | Deals no damage.                                |

### SpriteParticleEmitterComponent
Emits particles to create visual effects.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `sprite_file`    | `data/particles/creepy.xml` | The particle sprite to use.                     |
| `delay`          | `0`     | Particles are emitted immediately.              |
| `lifetime`       | `0`     | Particles have no independent lifetime.         |
| `render_back`    | `1`     | Particles are rendered behind other elements.   |
| `color.r`, `color.g`, `color.b`, `color.a` | `1`, `1`, `1`, `0.4` | Initial color and transparency of particles.    |
| `color_change.a` | `-1`    | Transparency decreases over time.               |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `3`, `4` | Interval between particle emissions.            |
| `count_min`, `count_max` | `1`, `1` | Number of particles emitted per interval.       |
| `randomize_rotation.min`, `randomize_rotation.max` | `-3.1415`, `3.1415` | Random rotation range for particles.            |
| `randomize_angular_velocity.min`, `randomize_angular_velocity.max` | `-8.3415`, `8.3415` | Random angular velocity range for particles.    |
| `randomize_position.min_x`, `randomize_position.max_x` | `-2`, `2` | Random X position range for particles.          |
| `randomize_position.min_y`, `randomize_position.max_y` | `-2`, `2` | Random Y position range for particles.          |
| `randomize_velocity.min_x`, `randomize_velocity.max_x` | `-8`, `8` | Random X velocity range for particles.          |
| `randomize_velocity.min_y`, `randomize_velocity.max_y` | `-8`, `8` | Random Y velocity range for particles.          |