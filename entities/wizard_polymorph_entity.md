---
title: Wizard Polymorph Entity
category: entities
---

# Wizard Polymorph Entity

This document details the `wizard_poly.xml` entity, representing a polymorphed wizard enemy in Noita.

## Core Attributes

The `wizard_poly` entity inherits from `base_enemy_basic.xml` and possesses several key components that define its behavior and appearance.

### `Base` Component

*   **`file`**: `data/entities/base_enemy_basic.xml` - Inherits fundamental enemy properties.
*   **`ItemChestComponent`**: `level="2"` - Indicates the loot tier associated with this enemy.

### `AnimalAIComponent`

This component governs the AI and combat behavior of the wizard polymorph.

*   **`_enabled`**: `1` - The AI component is active.
*   **`preferred_job`**: `JobDefault` - Uses the default AI job.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `400` - Defines the detection radius for other creatures.
*   **`food_material`**: `blood` - The material it consumes for sustenance.
*   **`needs_food`**: `0` - Does not require food to survive.
*   **`sense_creatures`**: `1` - Actively senses nearby creatures.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`can_fly`**: `1` - The entity can fly.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/orb_poly.xml` - Specifies the projectile used for ranged attacks.
*   **`attack_ranged_action_frame`**: `5` - The frame at which the ranged attack is initiated.
*   **`attack_ranged_frames_between`**: `180` - The number of frames between ranged attacks.
*   **`attack_ranged_offset_y`**: `0` - Vertical offset for the ranged attack origin.
*   **`attack_ranged_min_distance`**: `0` - Minimum distance for ranged attacks.
*   **`attack_ranged_max_distance`**: `300` - Maximum distance for ranged attacks.

### `DamageModelComponent`

Defines the health and damage-related properties.

*   **`hp`**: `4` - The entity's hit points.
*   **`ragdoll_material`**: `meat_polymorph_protection` - The material used for its ragdoll upon death.
*   **`ragdoll_filenames_file`**: `data/ragdolls/wizard_poly/filenames.txt` - Points to the file defining its ragdoll structure.

### `SpriteComponent` (Primary)

Controls the main visual representation of the entity.

*   **`image_file`**: `data/enemies_gfx/wizard_poly.xml` - The primary sprite sheet for the entity.
*   **`offset_x` / `offset_y`**: `0` - Offsets for the sprite's position.

### `PathFindingComponent`

Enables pathfinding capabilities.

*   **`can_jump`**: `1` - The entity can jump.

### `GenomeDataComponent`

Provides genetic information for AI and ecosystem simulation.

*   **`herd_id`**: `mage` - Identifies the herd or group this entity belongs to.
*   **`food_chain_rank`**: `6` - Its position in the food chain.
*   **`is_predator`**: `1` - Indicates that this entity is a predator.

### `CharacterPlatformingComponent`

Defines movement parameters.

*   **`jump_velocity_y`**: `-12` - The vertical velocity applied when jumping.
*   **`run_velocity`**: `18` - The horizontal movement speed.

### `HitboxComponent`

Defines the collision boundaries for the entity.

*   **`aabb_min_x` / `aabb_max_x`**: `-4.5` / `4.5` - Defines the horizontal bounds of the hitbox.
*   **`aabb_min_y` / `aabb_max_y`**: `-10` / `3` - Defines the vertical bounds of the hitbox.

### `CharacterDataComponent`

Additional character-specific collision data.

*   **`collision_aabb_min_x` / `collision_aabb_max_x`**: `-3.0` / `3.0` - Horizontal collision bounds.
*   **`collision_aabb_min_y` / `collision_aabb_max_y`**: `-7` / `3` - Vertical collision bounds.

## Visual and Particle Effects

### `SpriteParticleEmitterComponent`

Responsible for emitting visual particles.

*   **`sprite_file`**: `data/particles/shine_03.xml` - The particle sprite to emit.
*   **`lifetime`**: `2` - Duration of each particle.
*   **`color`**: `1, 1, 1, 1` - Initial color (white).
*   **`color_change`**: `0, 0, 0, -1` - Color fades out over time.
*   **`gravity`**: `x="0", y="30"` - Gravity applied to particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `10` / `20` - Controls the timing of particle emissions.
*   **`count_min` / `count_max`**: `1` / `1` - Number of particles emitted per interval.
*   **`randomize_rotation`**: `min="-3.1415", max="3.1415"` - Randomizes particle rotation.
*   **`randomize_velocity`**: `min_x="-5", max_x="5", min_y="-5", max_y="5"` - Randomizes particle velocity.
*   **`randomize_position`**: `min_x="-10", max_x="10", min_y="-10", max_y="10"` - Randomizes particle spawn position.

### `SpriteComponent` (Emissive)

Adds an emissive sprite for a glowing effect.

*   **`_tags`**: `character` - Tag for character-related sprites.
*   **`alpha`**: `1` - Full opacity.
*   **`image_file`**: `data/enemies_gfx/wizard_poly_emissive.xml` - The emissive sprite sheet.
*   **`emissive`**: `1` - Enables emissive rendering.
*   **`additive`**: `1` - Uses additive blending for the emissive effect.
*   **`rect_animation`**: `walk` - Specifies the default animation.

## Audio Components

### `AudioLoopComponent`

Plays a looping sound effect.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank containing the sound.
*   **`event_name`**: `animals/wizard/movement_loop` - The specific sound event to play.
*   **`auto_play`**: `1` - The sound starts automatically.

### `AudioComponent`

Plays general audio events.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank.
*   **`event_root`**: `animals/wizard` - The root event name for wizard sounds.

## Other Components

### `ItemPickUpperComponent`

*   **`is_in_npc`**: `1` - Indicates this item can be picked up by NPCs.

### `HotspotComponent`

*   **`sprite_hotspot_name`**: `cape` - Defines a hotspot named "cape" for attachment.

### `Entity name="cape"`

This nested entity defines the wizard's cape.

*   **`Base file`**: `data/entities/verlet_chains/cape/cape.xml` - Inherits from a generic cape entity.
*   **`VerletPhysicsComponent`**:
    *   **`cloth_color_edge`**: `0xFFEBD1E6` - Edge color of the cloth.
    *   **`cloth_color`**: `0xFF773B3E` - Main color of the cloth.