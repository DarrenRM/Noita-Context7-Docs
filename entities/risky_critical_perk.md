---
title: Risky Critical Perk
category: entities
---

---

# Risky Critical Perk

This entity defines the "Risky Critical" perk in Noita, which modifies projectile behavior.

## Core Components

### LuaComponent
This component links the perk to its associated Lua script, `data/scripts/perks/risky_critical.lua`. It's set to execute every 2 frames, indicating active logic for the perk.

### ParticleEmitterComponent
This component is responsible for visual effects associated with the perk.
- `_tags="risky_critical"`: Identifies particles related to this perk.
- `emitted_material_name="spark_red"`: Specifies the material for the emitted particles.
- `count_min="1"`, `count_max="3"`: Controls the number of particles emitted per burst.
- `lifetime_min="0.8"`, `lifetime_max="2.0"`: Sets the duration for which particles exist.
- `emission_interval_min_frames="4"`, `emission_interval_max_frames="5"`: Determines the frequency of particle emissions.
- `is_emitting="1"`: Ensures the particle emitter is active.

### ShotEffectComponent
This component applies a direct effect to projectiles.
- `_tags="risky_critical"`: Links this effect to the perk.
- `extra_modifier="critical_plus_small"`: This is the key attribute, applying a "critical_plus_small" modifier to shots. This likely increases the chance or magnitude of critical hits.

## Key Attributes

| Component             | Attribute                 | Value                 | Description                                       |
| :-------------------- | :------------------------ | :-------------------- | :------------------------------------------------ |
| LuaComponent          | `script_source_file`      | `data/scripts/perks/risky_critical.lua` | The script that governs the perk's logic.         |
| LuaComponent          | `execute_every_n_frame`   | `2`                   | How often the Lua script logic is executed.       |
| ParticleEmitterComponent | `emitted_material_name`   | `spark_red`           | The visual effect material.                       |
| ParticleEmitterComponent | `lifetime_min`            | `0.8`                 | Minimum duration of emitted particles.            |
| ParticleEmitterComponent | `lifetime_max`            | `2.0`                 | Maximum duration of emitted particles.            |
| ShotEffectComponent   | `extra_modifier`          | `critical_plus_small` | The primary effect: enhances critical hits.       |