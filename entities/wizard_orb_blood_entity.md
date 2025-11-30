---
title: Wizard Orb (Blood) Entity
category: entities
---

---

# Wizard Orb (Blood) Entity

This document describes the `wizard_orb_blood.xml` entity, representing a blood-themed orb used by a boss wizard in Noita. It details its visual representation, behavior, and combat properties.

## Key Components and Attributes

### Entity Name and Tags

*   **name**: `$projectile_default` (This seems to be a placeholder or a base projectile name, but the entity itself is the blood orb).
*   **tags**: `hittable`, `touchmagic_immunity`, `polymorphable_NOT`
    *   `hittable`: The orb can be targeted and damaged.
    *   `touchmagic_immunity`: Immune to touch magic effects.
    *   `polymorphable_NOT`: Cannot be polymorphed.

### ParticleEmitterComponent

This component controls the visual effects of the orb, specifically emitting blood particles.

*   **emitted\_material\_name**: `blood` - The material used for emitted particles.
*   **gravity.y**: `100.0` - Controls the downward pull of the particles.
*   **lifetime\_min**: `0.8` - Minimum duration particles exist.
*   **lifetime\_max**: `1.5` - Maximum duration particles exist.
*   **count\_min**: `3` - Minimum number of particles emitted per burst.
*   **count\_max**: `6` - Maximum number of particles emitted per burst.
*   **render\_on\_grid**: `1` - Particles are rendered on the game grid.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade out as their lifetime ends.
*   **airflow\_force**: `1.1` - Strength of airflow affecting particles.
*   **airflow\_time**: `1.01` - Duration airflow affects particles.
*   **airflow\_scale**: `0.05` - Scale of airflow effect.
*   **emission\_interval\_min\_frames**: `1` - Minimum frames between particle emissions.
*   **emission\_interval\_max\_frames**: `1` - Maximum frames between particle emissions.
*   **emit\_cosmetic\_particles**: `1` - Emits cosmetic particles.
*   **is\_emitting**: `1` - The particle emitter is active.

### VariableStorageComponent

Stores a unique identifier for the wizard orb.

*   **\_tags**: `wizard_orb_id`
*   **name**: `wizard_orb_id`
*   **value\_int**: `0` - An integer value, likely used to distinguish this orb from others.

### LuaComponent (Orb Rotation)

*   **script\_source\_file**: `data/entities/animals/boss_wizard/orb_rotation.lua` - This script handles the orb's rotation behavior.
*   **execute\_every\_n\_frame**: `1` - The script runs every frame.

### LuaComponent (Damage Received)

*   **script\_damage\_received**: `data/entities/animals/boss_wizard/orb_blood_damage.lua` - This script defines how the orb reacts to taking damage.
*   **execute\_every\_n\_frame**: `-1` - This script likely runs only when damage is received, not on a fixed frame interval.

### SpriteComponent

Defines the visual appearance of the orb.

*   **image\_file**: `data/entities/animals/boss_wizard/orb_blood.xml` - The XML file containing the sprite data.
*   **offset\_x**: `0`
*   **offset\_y**: `0`
*   **z\_index**: `1.2` - Controls the rendering layer of the sprite.

### GenomeDataComponent

Provides biological and ecological information about the entity.

*   **herd\_id**: `mage` - Identifies the entity as belonging to the "mage" herd.
*   **food\_chain\_rank**: `6` - A high rank, indicating it's a significant entity.
*   **is\_predator**: `1` - The entity is a predator.

### HitboxComponent

Defines the collision area of the orb.

*   **aabb\_max\_x**: `5`
*   **aabb\_max\_y**: `5`
*   **aabb\_min\_x**: `-5`
*   **aabb\_min\_y**: `-5` - This creates a square hitbox centered at the orb's origin.

### DamageModelComponent

Manages the orb's health and how it takes damage.

*   **hp**: `6000` - The orb has a substantial amount of health.
*   **ragdoll\_filenames\_file**: `""` - No specific ragdoll files are used.
*   **blood\_material**: `blood` - The material of blood produced when damaged.
*   **blood\_spray\_material**: `blood` - The material of blood spray.
*   **ragdoll\_offset\_y**: `-14`
*   **fire\_probability\_of\_ignition**: `0` - Cannot be ignited by fire.
*   **ragdoll\_fx\_forced**: `DISINTEGRATED` - The visual effect upon destruction.
*   **ragdoll\_material**: `blood` - The material of the destroyed entity.
*   **critical\_damage\_resistance**: `1.0` - No resistance to critical damage.
*   **physics\_objects\_damage**: `0` - Does not deal damage to physics objects.

#### damage\_multipliers

These multipliers affect how much damage the orb takes from different sources.

| Damage Type | Multiplier |
| :---------- | :--------- |
| projectile  | 0.2        |
| explosion   | 0.2        |
| electricity | 0.2        |
| fire        | 0.2        |
| ice         | 0.2        |
| melee       | 0.2        |
| slice       | 0.2        |

The orb takes significantly reduced damage (80% reduction) from all listed sources.

### GameEffectComponent (x2)

These components grant the orb immunity to certain status effects.

*   **InheritTransformComponent**: Ensures these effects are tied to the orb's transform.
*   **GameEffectComponent**:
    *   **effect**: `STUN_PROTECTION_FREEZE` - Grants immunity to freezing.
    *   **frames**: `-1` - The effect is permanent.
*   **GameEffectComponent**:
    *   **effect**: `STUN_PROTECTION_ELECTRICITY` - Grants immunity to electricity.
    *   **frames**: `-1` - The effect is permanent.