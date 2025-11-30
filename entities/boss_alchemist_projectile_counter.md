---
title: Boss Alchemist Projectile Counter
category: entities
---

# Boss Alchemist Projectile Counter

This entity defines the visual and functional components of the projectile counter used by the Boss Alchemist. It primarily handles visual effects and the area-of-effect behavior associated with its projectiles.

## Core Components

### InheritTransformComponent
This component is used to set the initial position of the projectile counter relative to its parent entity.

*   **position.x**: X-coordinate offset.
*   **position.y**: Y-coordinate offset.

### LuaComponent (Main Logic)
This component executes the primary Lua script responsible for the projectile counter's behavior.

*   **script\_source\_file**: `data/entities/animals/boss_alchemist/projectile_counter.lua` - The main script for this entity.
*   **execute\_every\_n\_frame**: `1` - The script runs every frame.

### Entity (Cell Eater)
This nested entity represents the area-of-effect that consumes cells.

*   **CellEaterComponent**:
    *   **radius**: `38` - The radius of the cell-eating effect.
    *   **eat\_probability**: `99` - The high probability of consuming cells within its radius.

### ParticleEmitterComponent (Purple Sparks - Inner)
This component emits purple sparks, creating a visual effect around the counter.

*   **emitted\_material\_name**: `spark_purple_bright` - The material of the emitted particles.
*   **lifetime\_min/max**: `0.5` to `1.5` seconds - Duration of each particle.
*   **count\_min/max**: `2` to `8` - Number of particles emitted per interval.
*   **area\_circle\_radius.max**: `48` - The maximum radius for particle emission.
*   **emission\_interval\_min/max\_frames**: `1` - Particles are emitted every frame.

### ParticleEmitterComponent (Purple Sparks - Outer)
Another particle emitter for purple sparks, with a slightly different emission pattern.

*   **emitted\_material\_name**: `spark_purple_bright` - The material of the emitted particles.
*   **lifetime\_min/max**: `0.5` to `1.5` seconds - Duration of each particle.
*   **count\_min/max**: `8` to `12` - Number of particles emitted per interval.
*   **area\_circle\_radius.min/max**: `48` - Particles are emitted at a fixed radius of 48.
*   **emission\_interval\_min/max\_frames**: `1` - Particles are emitted every frame.

### Base (Projectile Base)
This inherits from a base projectile entity, providing common projectile properties.

*   **SpriteComponent**:
    *   **image\_file**: `data/particles/area_indicator_096_purple.png` - The visual sprite for the counter.
    *   **offset\_x/y**: `48` - Offsets for the sprite's position.
*   **ProjectileComponent**:
    *   **lifetime**: `240` - The duration of the projectile in frames.
    *   **config\_explosion**: Defines the explosion effect upon projectile expiry.
*   **AudioLoopComponent**:
    *   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank for projectile sounds.
    *   **event\_name**: `player_projectiles/field_transmutation/loop` - The specific audio event to loop.

### LuaComponent (Cleanup Logic)
This component handles cleanup actions when the entity is removed.

*   **script\_source\_file**: `data/entities/animals/boss_alchemist/projectile_counter_away.lua` - The script for handling entity removal.
*   **execute\_on\_removed**: `1` - The script executes when the entity is removed.