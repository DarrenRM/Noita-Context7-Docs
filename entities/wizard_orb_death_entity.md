---
title: Wizard Orb Death Entity
category: entities
---

---

# Wizard Orb Death Entity

This document describes the `wizard_orb_death.xml` entity, which represents a projectile or effect associated with the boss wizard's death. It's designed to emit particles and deal damage in an area.

## Key Components and Attributes

### Entity Tagging
- `name`: `$projectile_default` (Indicates a default projectile type)
- `tags`: `hittable`, `touchmagic_immunity`, `polymorphable_NOT`, `wizard_orb_death` (Defines its behavior and interactions)

### Particle Emitters
This entity utilizes two `ParticleEmitterComponent` instances to create visual effects.

#### Primary Particle Emitter (Slime)
- `emitted_material_name`: `slime`
- `gravity.y`: `100.0`
- `lifetime_min`/`lifetime_max`: `0.8` - `1.5` seconds
- `count_min`/`count_max`: `3` - `6` particles per emission
- `fade_based_on_lifetime`: `1` (Particles fade out as they expire)
- `airflow_force`/`airflow_time`/`airflow_scale`: Controls particle movement and spread.

#### Secondary Particle Emitter (Spark)
- `emitted_material_name`: `spark_purple_bright`
- `gravity.y`: `0.0` (No gravity effect)
- `lifetime_min`/`lifetime_max`: `0.2` - `0.6` seconds
- `count_min`/`count_max`: `5` - `10` particles per emission
- `area_circle_radius.min`/`max`: `8` - `16` (Emitted in a circular area)
- `airflow_force`/`airflow_time`/`airflow_scale`: `1.5`, `1.9`, `0.15` (Stronger airflow for sparks)
- `velocity_always_away_from_center`: `100` (Sparks are pushed outwards)

### Variable Storage
- `VariableStorageComponent`:
    - `_tags`: `wizard_orb_id`
    - `name`: `wizard_orb_id`
    - `value_int`: `0` (Likely used to identify this specific orb instance)

### Lua Scripting
- `LuaComponent` (Orb Rotation):
    - `script_source_file`: `data/entities/animals/boss_wizard/orb_rotation.lua`
    - `execute_every_n_frame`: `1` (Runs every frame for rotation logic)
- `LuaComponent` (Orb Death Effect):
    - `script_source_file`: `data/entities/animals/boss_wizard/orb_death_effect.lua`
    - `execute_every_n_frame`: `101` (Runs less frequently for death-related effects)

### Genome Data
- `GenomeDataComponent`:
    - `herd_id`: `mage`
    - `food_chain_rank`: `6`
    - `is_predator`: `1`

### Sprite Component
- `SpriteComponent`:
    - `image_file`: `data/entities/animals/boss_wizard/orb_death.xml` (References its own definition for sprite)
    - `z_index`: `1.2` (Determines rendering layer)

### Hitbox Component
- `HitboxComponent`:
    - `aabb_max_x`/`y`: `5`
    - `aabb_min_x`/`y`: `-5` (Defines a small, circular hitbox)

### Damage Model
- `DamageModelComponent`:
    - `hp`: `20`
    - `ragdoll_fx_forced`: `DISINTEGRATED`
    - `ragdoll_material`: `slime`
    - `damage_multipliers`: All multipliers are set to `0.5`, indicating reduced damage from various sources.

### Game Effect Components
Two `Entity` blocks with `InheritTransformComponent` and `GameEffectComponent` are present:
- `effect`: `STUN_PROTECTION_FREEZE`, `frames`: `-1` (Indicates immunity to freeze effects)
- `effect`: `STUN_PROTECTION_ELECTRICITY`, `frames`: `-1` (Indicates immunity to electricity effects)

### Area Damage Component
- `AreaDamageComponent`:
    - `aabb_min`/`max`: Defines a larger area of effect (`-12` to `12` on both axes).
    - `damage_per_frame`: `0.06`
    - `update_every_n_frame`: `4`
    - `entities_with_tag`: `human` (Targets player characters)
    - `damage_type`: `DAMAGE_CURSE` (Deals curse damage over time within the area)