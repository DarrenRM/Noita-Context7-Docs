---
title: Giant Shooter Entity
category: entities
---

# Giant Shooter Entity

This document details the configuration of the Giant Shooter entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Attributes

The Giant Shooter is a flying, acidic enemy with a distinct appearance and attack pattern.

### `Base` Component

Inherits from `base_enemy_flying.xml`, providing fundamental flying enemy behaviors.

### `AnimalAIComponent`

*   **`attack_ranged_entity_file`**: `data/entities/projectiles/acidshot.xml` - Specifies the projectile used for ranged attacks.
*   **`attack_ranged_frames_between`**: `40` - The cooldown in frames between ranged attacks.
*   **`needs_food`**: `0` - This entity does not require food.
*   **`can_fly`**: `1` - Enables flight capabilities.

### `DamageModelComponent`

*   **`hp`**: `5.0` - The entity's health points.
*   **`ragdoll_material`**: `meat_slime_green` - The material used for its ragdoll when defeated.
*   **`blood_material`**: `acid` - The material that constitutes its blood.
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_green_$[1-3].xml` - Defines directional blood splatter particle effects.
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_green_$[1-3].xml` - Defines large blood splatter particle effects.
*   **`materials_that_damage`**: `lava,poison,blood_cold,blood_cold_vapour` - Lists materials that inflict damage upon contact.
*   **`materials_how_much_damage`**: `0.004,0.001,0.0008,0.0007` - Corresponding damage values for the materials listed above.

### `PathFindingComponent`

*   **`can_fly`**: `1` - Confirms the entity can fly.
*   **`can_walk`**: `0` - The entity cannot walk.
*   **`space_required`**: `5` - The amount of space this entity occupies for pathfinding.

### `SpriteComponent`

*   **`image_file`**: `data/enemies_gfx/giantshooter.xml` - The graphical asset file for the entity's sprite.

### `GenomeDataComponent`

*   **`herd_id`**: `slimes` - Identifies this entity as part of the "slimes" herd.

### `HitboxComponent`

*   **`aabb_max_x`**: `8`
*   **`aabb_max_y`**: `3`
*   **`aabb_min_x`**: `-8`
*   **`aabb_min_y`**: `-15`
    These define the Axis-Aligned Bounding Box for collision detection.

### `CharacterDataComponent`

*   **`collision_aabb_min_x`**: `-8.0`
*   **`collision_aabb_max_x`**: `8.0`
*   **`collision_aabb_min_y`**: `-15`
*   **`collision_aabb_max_y`**: `3`
    These define the collision bounding box for the character.
*   **`mass`**: `2.2` - The entity's mass.

### `AudioComponent`

*   Multiple components define various sound events, including general animal sounds, movement loops, and specific Giant Shooter sounds.

## Special Components

### `MaterialInventoryComponent`

*   **`drop_as_item`**: `0` - The materials are not dropped as items upon death.
*   **`leak_on_damage_percent`**: `0.999` - The entity will leak its stored materials when at 99.9% damage.
*   **`count_per_material_type`**:
    *   `Material material="acid" count="400"` - The entity carries 400 units of "acid".

### `LightComponent`

*   **`radius`**: `80` - The radius of the light emitted by the entity.
*   **`r`, `g`, `b`**: `118, 255, 118` - Defines the green color of the emitted light.

### `ExplodeOnDamageComponent`

*   **`explode_on_death_percent`**: `1` - The entity will explode upon death.
*   **`explode_on_damage_percent`**: `0.0` - The entity does not explode from taking damage, only from death.
*   **`config_explosion`**: Defines the parameters of the explosion, including damage, radius, particle effects, and physics properties. Key parameters include:
    *   `damage`: `3`
    *   `camera_shake`: `30`
    *   `explosion_radius`: `30`
    *   `create_cell_material`: `acid`
    *   `ray_energy`: `160000`
    *   `physics_explosion_power.min/max`: `0.6/1.1`

### `LuaComponent`

*   **`script_damage_received`**: `data/scripts/animals/giantshooter_death.lua` - A script executed when the entity receives damage, likely for custom death behaviors.

### `Entity` (Child Entities)

The Giant Shooter spawns several `verlet_chains` which appear to be tentacles. These are defined by their respective `Base` files and `InheritTransformComponent` for positioning.

*   `slime_tentacle_02.xml` (offset x="-3", y="-1")
*   `slime_tentacle_01.xml` (offset x="-6", y="-1")
*   `slime_tentacle_thin_01.xml` (offset x="0", y="-1")
*   `slime_tentacle_thin_01.xml` (offset x="6", y="-1")
*   `slime_tentacle_03.xml` (offset x="2", y="-1")

### `MusicEnergyAffectorComponent`

*   **`energy_target`**: `1.0` - Affects music energy.

### `AudioLoopComponent`

*   Two components are present: one for a "sound\_spray" event and another for a "movement\_loop" with auto-play enabled.