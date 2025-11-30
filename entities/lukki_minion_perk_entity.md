---
title: Lukki Minion Perk Entity
category: entities
---

# Lukki Minion Perk Entity

This entity defines the "Lukki Minion" perk in Noita. It's a small, passive creature that follows the player and deals minor contact damage.

## Core Components

### SpriteComponent
- **image_file**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_minion.xml` - Specifies the visual appearance of the minion.

### LuaComponent
- **script_source_file**: `data/scripts/perks/lukki_minion_movement.lua` - Controls the AI and movement behavior of the minion.
- **execute_every_n_frame**: `1` - The AI script runs every frame.

### PhysicsBodyComponent
- **allow_sleep**: `0` - The minion will not go to sleep, ensuring constant activity.
- **fixed_rotation**: `1` - Prevents the minion from rotating, maintaining its upright orientation.

### DamageModelComponent
- **hp**: `9999.5` - High health, making it difficult to destroy.
- **fire_damage_amount**: `02` - Deals a small amount of fire damage on contact.
- **blood_material**: `slime_green` - Defines the material of the blood/goo it leaves.
- **damage_multipliers**: All set to `0.0`, indicating it's immune to most damage types.

### HitboxComponent (Weak Spot)
- **_tags**: `hitbox_weak_spot` - Identifies this hitbox as a critical point.
- **aabb_min/max**: Defines a small central area for targeting.
- **damage_multiplier**: `1.0` - Standard damage taken at this weak spot.

### AreaDamageComponent
- **aabb_min/max**: Defines the area of effect for contact damage.
- **damage_per_frame**: `0.2` - Deals a small amount of damage per frame to enemies within its area.
- **entities_with_tag**: `enemy` - Only affects entities tagged as "enemy".
- **damage_type**: `DAMAGE_MELEE` - The type of damage dealt.

## Visuals and Effects

### LightComponent
- **radius**: `32` - Emits a small light.
- **r, g, b**: `120, 60, 10` - Defines the color of the light (orangish-yellow).
- **fade_out_time**: `1.5` - How long the light fades out.

### ParticleEmitterComponent
- **emitted_material_name**: `radioactive_liquid` - Emits particles of this material.
- **count_min/max**: `1` to `5` particles emitted at a time.
- **lifetime_min/max**: `0.3` to `1.6` seconds.
- **emission_interval_min/max_frames**: `7` to `20` frames between emissions.
- **cosmetic_force_create**: `1` - Ensures particles are created even if other conditions aren't met.
- **emit_cosmetic_particles**: `1` - Particles are purely visual.

## Limbs and Structure

The minion is constructed from multiple instances of a base limb entity:

- **Base Limbs**: 5 instances of `data/entities/animals/lukki/lukki_feet/lukki_limb_minion.xml`.
- **Attacker Limb**: 1 instance of `data/entities/animals/lukki/lukki_feet/lukki_limb_attacker_minion.xml`, likely responsible for the contact damage.

## Other Components

### GenomeDataComponent
- **herd_id**: `player` - Associates the minion with the player's herd.

### AudioComponent
- Two instances are present, likely for general animal sounds and specific "lukki_tiny" sounds.

### SpriteAnimatorComponent
- **target_sprite_comp_name**: `character` - Links animation to the main sprite.

### VariableStorageComponent
- **name**: `memory`
- **value_int**: `0` - A placeholder for potential future memory functionality.