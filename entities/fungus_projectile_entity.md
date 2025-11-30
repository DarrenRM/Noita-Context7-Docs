---
title: Fungus Projectile Entity
category: entities
---

# Fungus Projectile Entity

This document details the configuration of the Fungus projectile entity in Noita, primarily focusing on its behavior, appearance, and interactions.

## Core Entity Configuration

The `fungus_projectile.xml` file defines a basic enemy entity with specific AI behaviors, damage properties, and visual elements.

### Base Entity (`<Base>`)

This section inherits properties from `data/entities/base_enemy_basic.xml`, providing a foundation for enemy characteristics.

*   **`ItemChestComponent`**: Configures loot drops.
    *   `level`: 2 (Indicates the rarity/quality of the loot table).
    *   `enemy_drop`: 1 (Specifies that this entity can drop items).

### AI Behavior (`<AnimalAIComponent>`)

Controls the entity's movement and combat logic.

*   **`_enabled`**: `1` (AI is active).
*   **`escape_if_damaged_probability`**: `70` (70% chance to attempt escape when damaged).
*   **`food_material`**: `blood` (The entity is attracted to or consumes blood).
*   **`attack_melee_enabled`**: `0` (Melee attacks are disabled).
*   **`attack_dash_enabled`**: `1` (Dash attacks are enabled).
*   **`attack_dash_lob`**: `1.1` (Controls the trajectory or arc of the dash attack).
*   **`aggressiveness_min`**: `10`
*   **`aggressiveness_max`**: `100` (Determines the overall aggression level).

### Damage and Health (`<DamageModelComponent>`)

Defines how the entity takes damage and its physical properties.

*   **`hp`**: `2.6` (Hit points of the entity).
*   **`air_needed`**: `0` (Does not require air to survive).
*   **`ragdoll_filenames_file`**: `data/ragdolls/fungus/filenames.txt` (Specifies the ragdoll configuration).
*   **`fire_probability_of_ignition`**: `100` (100% chance to ignite when exposed to fire).
*   **`ragdoll_material`**: `fungus_loose_trippy` (The material used for its ragdoll).
*   **`blood_material`**: `blood_fungi` (The material of the blood it bleeds).
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` (Visuals for directional blood splatters).
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` (Visuals for large blood splatters).
*   **`minimum_knockback_force`**: `100000` (A high value indicating significant knockback resistance or effect).

#### Damage Multipliers (`<damage_multipliers>`)

*   **`fire`**: `40.0` (Takes 40x damage from fire).

### Visuals (`<SpriteComponent>`)

Determines the entity's appearance.

*   **`image_file`**: `data/enemies_gfx/fungus.xml` (The graphical asset for the fungus).
*   **`offset_x`**: `0`
*   **`offset_y`**: `0`

### Pathfinding (`<PathFindingGridMarkerComponent>`, `<PathFindingComponent>`)

Configures how the entity navigates the game world.

*   **`PathFindingGridMarkerComponent`**:
    *   `marker_work_flag`: `16` (A flag used for pathfinding grid calculations).
*   **`PathFindingComponent`**:
    *   `frames_to_get_stuck`: `120` (Number of frames before considering itself stuck).
    *   `can_jump`: `1` (Can jump).
    *   `never_consider_line_of_sight`: `1` (Ignores line of sight for pathfinding).

### Genetic Data (`<GenomeDataComponent>`)

Defines the entity's place in the ecosystem.

*   **`herd_id`**: `fungus` (Identifier for its herd or species).
*   **`food_chain_rank`**: `15` (Its position in the food chain).
*   **`is_predator`**: `1` (Classified as a predator).

### Movement (`<CharacterPlatformingComponent>`)

Controls basic movement parameters.

*   **`jump_velocity_y`**: `-12` (The vertical force applied when jumping).
*   **`run_velocity`**: `9` (The horizontal movement speed).

### Camera Bounds (`<CameraBoundComponent>`)

Manages how the entity interacts with the camera's view.

*   **`max_count`**: `30` (Maximum number of this entity type that can be active within camera bounds).
*   **`distance`**: `160000` (The radius around the camera within which the entity is considered active).

### Hitbox (`<HitboxComponent>`)

Defines the collision area for interactions.

*   **`aabb_max_x`**: `6`
*   **`aabb_max_y`**: `4`
*   **`aabb_min_x`**: `-6`
*   **`aabb_min_y`**: `-10`

### Character Data (`<CharacterDataComponent>`)

General character physics and collision properties.

*   **`collision_aabb_min_x`**: `-3.0`
*   **`collision_aabb_max_x`**: `3.0`
*   **`collision_aabb_min_y`**: `-10`
*   **`collision_aabb_max_y`**: `3`
*   **`mass`**: `1.3`

### Audio (`<AudioComponent>`)

Specifies sound effects associated with the entity.

*   **`file`**: `data/audio/Desktop/animals.bank` (The audio bank containing the sounds).
*   **`event_root`**: `animals/slime` (The base event name for its sounds).

## Additional Components

These components add specific functionalities beyond the basic enemy template.

### Material Inventory (`<MaterialInventoryComponent>`)

Manages the materials the entity possesses and how they are handled.

*   **`_enabled`**: `1`
*   **`drop_as_item`**: `0` (Does not drop its internal materials as items).
*   **`leak_on_damage_percent`**: `0.999` (Leaks its materials when 99.9% damaged).
*   **`count_per_material_type`**:
    *   `Material material="blood_fungi" count="400"` (Contains 400 units of `blood_fungi` material).

### Lua Scripting (`<LuaComponent>`)

Integrates custom Lua scripts for advanced behaviors.

*   **Script for Death**:
    *   `script_death`: `data/scripts/animals/fungus_death.lua` (Executed when the entity dies).
*   **Script for Collision Trigger Timer**:
    *   `script_collision_trigger_timer_finished`: `data/scripts/animals/fungus_death.lua` (Executed when a collision trigger timer finishes).
*   **Script for Collision Trigger Hit**:
    *   `script_collision_trigger_hit`: `data/scripts/animals/fungus_smoke.lua` (Executed when a collision trigger is hit).

### Collision Triggers (`<CollisionTriggerComponent>`)

Components that detect collisions and trigger events.

*   **Trigger 1**:
    *   `width`: `10`
    *   `height`: `10`
    *   `radius`: `5`
    *   `required_tag`: `mortal` (Only triggers if the colliding entity has the "mortal" tag).
    *   `timer_for_destruction`: `20` (The entity is destroyed after 20 frames when triggered).
*   **Trigger 2**:
    *   `width`: `10`
    *   `height`: `10`
    *   `radius`: `5`
    *   `required_tag`: `mortal`
    *   `timer_for_destruction`: `0` (Destroys immediately upon trigger).
    *   `destroy_this_entity_when_triggered`: `0` (Does not destroy itself when triggered).
    *   `remove_component_when_triggered`: `1` (Removes this specific collision trigger component when activated).

### Particle Emitter (`<ParticleEmitterComponent>`)

Generates visual particle effects.

*   **`emitted_material_name`**: `acid_gas` (The material of the particles emitted).
*   **`offset.x`, `offset.y`**: `0` (Emission origin relative to the entity).
*   **`x_pos_offset_min`, `y_pos_offset_min`**: `-2`, `-2` (Minimum offset for particle spawn position).
*   **`x_pos_offset_max`, `y_pos_offset_max`**: `2`, `2` (Maximum offset for particle spawn position).
*   **`x_vel_min`, `y_vel_min`**: `-10`, `-10` (Minimum velocity of emitted particles).
*   **`x_vel_max`, `y_vel_max`**: `10`, `10` (Maximum velocity of emitted particles).
*   **`count_min`, `count_max`**: `1`, `2` (Number of particles emitted per burst).
*   **`lifetime_min`, `lifetime_max`**: `0.6`, `1.8` (Duration particles exist).
*   **`create_real_particles`**: `1` (Emits actual game particles).
*   **`emit_cosmetic_particles`**: `0` (Does not emit purely cosmetic particles).
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `10`, `35` (Frame delay between particle emissions).
*   **`is_emitting`**: `1` (Particle emission is active).

### Additional Audio (`<AudioComponent>`)

A second audio component, likely for specific fungus-related sounds.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_root`**: `animals/fungus`

### Variable Storage (`<VariableStorageComponent>`)

Used to store custom variables or tags for the entity.

*   **`_tags`**: `no_gold_drop` (This entity will not drop gold).