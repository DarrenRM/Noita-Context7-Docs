---
title: Vacuum Powder Projectile
category: entities
---

# Vacuum Powder Projectile

This document details the `vacuum_powder.xml` entity, which defines the behavior and appearance of the Vacuum Powder projectile in Noita. This projectile is characterized by its ability to suck in materials and its distinct visual effects.

## Key Components and Attributes

The Vacuum Powder projectile is constructed from several key components, each contributing to its unique functionality.

### GameAreaEffectComponent

This component defines a general area effect associated with the projectile.

*   **radius**: `64` - The radius of the area affected by the projectile.

### ParticleEmitterComponent (x2)

Two `ParticleEmitterComponent` instances are used to generate visual effects.

**Emitter 1:**

*   **emitted_material_name**: `spark_purple_bright` - The material used for the emitted particles.
*   **lifetime\_min**: `0.5` - Minimum lifetime of emitted particles.
*   **lifetime\_max**: `1.5` - Maximum lifetime of emitted particles.
*   **count\_min**: `2` - Minimum number of particles emitted per burst.
*   **count\_max**: `4` - Maximum number of particles emitted per burst.
*   **airflow\_force**: `1.7` - Force applied to particles by airflow.
*   **attractor\_force**: `4` - Force that attracts particles.

**Emitter 2:**

*   **emitted\_material\_name**: `spark_purple_bright` - The material used for the emitted particles.
*   **lifetime\_min**: `0.5` - Minimum lifetime of emitted particles.
*   **lifetime\_max**: `2.5` - Maximum lifetime of emitted particles.
*   **count\_min**: `4` - Minimum number of particles emitted per burst.
*   **count\_max**: `4` - Maximum number of particles emitted per burst.
*   **area\_circle\_radius.min**: `64` - Minimum radius for particle emission.
*   **area\_circle\_radius.max**: `64` - Maximum radius for particle emission.
*   **airflow\_force**: `0.8` - Force applied to particles by airflow.
*   **attractor\_force**: `8` - Force that attracts particles.

### Base File Inclusion

The projectile inherits properties from `data/entities/projectiles/deck/base_field.xml`.

*   **SpriteComponent**: Disabled (`_enabled="0"`).
*   **SpriteParticleEmitterComponent**: Disabled (`_enabled="0"`).
*   **ProjectileComponent**:
    *   **lifetime**: `300` - The duration the projectile exists.
    *   **config\_explosion**: Specifies the explosion visual effect (`data/particles/blast_out_polymorph.xml`).
*   **AudioLoopComponent**:
    *   **file**: `data/audio/Desktop/projectiles.bank`
    *   **event\_name**: `player_projectiles/field_transmutation/loop` - The audio event for the projectile's loop sound.
    *   **auto\_play**: `1` - The sound will play automatically.

### MaterialSuckerComponent

This component enables the projectile to absorb materials.

*   **num\_cells\_sucked\_per\_frame**: `100` - The number of material cells absorbed per frame.
*   **randomized\_position.min\_x/max\_x/min\_y/max\_y**: `-64` to `64` - Defines the area around the projectile where materials are sucked from.
*   **material\_type**: `1` - Specifies the type of material to be sucked (likely related to internal game material IDs).
*   **barrel\_size**: `10000` - A large value, suggesting a wide suction range.

### MaterialInventoryComponent

Manages how materials are handled when the projectile is destroyed.

*   **drop\_as\_item**: `0` - The absorbed materials are not dropped as an item upon death.
*   **on\_death\_spill**: `1` - Absorbed materials are spilled upon death.

### DamageModelComponent

Defines the damage and health properties of the projectile.

*   **hp**: `0.5` - The projectile's health.
*   **materials\_create\_messages**: `1` - Materials interacting with the projectile can create messages.
*   **wait\_for\_kill\_flag\_on\_death**: `1` - The projectile waits for a kill flag before fully dying.
*   **ui\_report\_damage**: `0` - Damage dealt by this projectile is not reported in the UI.

### HitboxComponent

Defines the collision area of the projectile.

*   **aabb\_min\_x/max\_x**: `-2` to `2` - Defines the bounding box in the X-axis.
*   **aabb\_min\_y/max\_y**: `-2` to `2` - Defines the bounding box in the Y-axis.

### LuaComponent (x2)

These components execute Lua scripts to control projectile behavior.

**Lua Component 1:**

*   **_tags**: `vacuum_powder_helper` - A tag for identifying this component.
*   **script\_source\_file**: `data/scripts/projectiles/vacuum_powder.lua` - The main script for the projectile's behavior.
*   **execute\_every\_n\_frame**: `280` - The script executes every 280 frames.

**Lua Component 2:**

*   **script\_source\_file**: `data/scripts/projectiles/vacuum_powder_init.lua` - A script for initial setup.
*   **execute\_every\_n\_frame**: `2` - The script executes every 2 frames.
*   **remove\_after\_executed**: `1` - The script is removed after its first execution.