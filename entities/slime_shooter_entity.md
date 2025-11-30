---
title: Slime Shooter Entity
category: entities
---

# Slime Shooter Entity

This document details the `slimeshooter.xml` entity, a flying, radioactive slime creature in Noita.

## Core Components

The Slime Shooter is built upon several base components that define its behavior and appearance.

### Base Enemy Flying

Inherits fundamental properties for flying enemies.

### AnimalAIComponent

Governs the creature's artificial intelligence and combat actions.

*   **`attack_ranged_entity_file`**: `data/entities/projectiles/radioactive_blob_trail.xml` - Specifies the projectile fired.
*   **`attack_ranged_enabled`**: `1` - Enables ranged attacks.
*   **`attack_dash_enabled`**: `0` - Disables dashing attacks.
*   **`attack_ranged_frames_between`**: `35` - Cooldown between ranged attacks.
*   **`attack_ranged_offset_y`**: `-8` - Vertical offset for projectile origin.
*   **`needs_food`**: `0` - Does not require food.
*   **`can_fly`**: `1` - Confirms it can fly.

### DamageModelComponent

Defines health, damage resistances, and how damage is applied.

*   **`hp`**: `0.75` - Health points.
*   **`ragdoll_filenames_file`**: `data/ragdolls/slimeshooter/filenames.txt` - Defines ragdoll appearance on death.
*   **`ragdoll_material`**: `meat_slime_green` - Material for the ragdoll.
*   **`blood_material`**: `radioactive_liquid` - Material of the blood.
*   **`blood_spray_material`**: `radioactive_liquid` - Material of the blood spray.
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_green_$[1-3].xml` - Sprite for directional blood splatters.
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_green_$[1-3].xml` - Sprite for large blood splatters.
*   **`materials_that_damage`**: `lava,poison,blood_cold,blood_cold_vapour` - Materials that inflict damage.
*   **`materials_how_much_damage`**: `0.004,0.001,0.0008,0.0007` - Damage values for the above materials.
*   **`damage_multipliers`**:
    *   `radioactive`: `0.0` - Immune to radioactive damage.

### PathFindingComponent

Determines movement capabilities.

*   **`can_fly`**: `1` - Can fly.
*   **`can_walk`**: `0` - Cannot walk.

### SpriteComponent

Handles visual representation.

*   **`image_file`**: `data/enemies_gfx/slimeshooter.xml` - Path to the sprite graphics.

### GenomeDataComponent

Used for genetic traits and herd behavior.

*   **`herd_id`**: `slimes` - Belongs to the "slimes" herd.

### HitboxComponent

Defines the collision boundaries of the entity.

*   **`aabb_min_x`**: `-4.0`
*   **`aabb_max_x`**: `4.0`
*   **`aabb_min_y`**: `-12`
*   **`aabb_max_y`**: `1`
*   **`is_enemy`**: `1` - Identifies as an enemy.

### CharacterDataComponent

Provides character-specific properties.

*   **`climb_over_y`**: `4`
*   **`collision_aabb_min_x`**: `-2.0`
*   **`collision_aabb_max_x`**: `2.0`
*   **`collision_aabb_min_y`**: `-10`
*   **`collision_aabb_max_y`**: `0`
*   **`mass`**: `0.9`

### AudioComponent (Base)

Manages general sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_root`**: `animals/slime`

## Additional Components

These components add specific functionalities like lighting, material handling, and specialized sounds.

### LightComponent

Emits light.

*   **`radius`**: `30`
*   **`r`**: `99`
*   **`g`**: `205`
*   **`b`**: `139`
*   **`offset_y`**: `-9`

### MaterialInventoryComponent

Manages the entity's internal materials.

*   **`drop_as_item`**: `0` - Does not drop as an item.
*   **`leak_on_damage_percent`**: `0.999` - Leaks material when heavily damaged.
*   **`count_per_material_type`**:
    *   `Material material="radioactive_liquid" count="800"` - Contains 800 units of radioactive liquid.

### AudioComponent (Specific)

Handles unique sound events for the Slime Shooter.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_root`**: `animals/slimeshooter`

### AudioLoopComponent (Movement)

Plays a looping sound for movement.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_name`**: `animals/slimy_small/movement_loop`
*   **`set_speed_parameter`**: `1`
*   **`auto_play`**: `1`

### AudioLoopComponent (Spray)

Plays a looping sound for spraying.

*   **`_tags`**: `sound_spray`
*   **`file`**: `data/audio/Desktop/materials.bank`
*   **`event_name`**: `materials/spray_animal`
*   **`volume_autofade_speed`**: `0.25`

## Attached Entities

The Slime Shooter has several attached entities, likely for visual flair or secondary effects.

*   **Slime Tentacle (Bright 02)**: `data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_02.xml`
*   **Slime Tentacle (Bright 01)**: `data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_01.xml`
*   **Slime Tentacle (Thin 01)**: `data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_01.xml`