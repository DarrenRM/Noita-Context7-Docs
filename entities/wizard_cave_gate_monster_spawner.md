---
title: Wizard Cave Gate Monster Spawner
category: entities
---

# Wizard Cave Gate Monster Spawner

This entity defines a spawner for monsters that appear at the wizard cave gate. It also includes visual effects and area clearing mechanics.

## Key Components

### LoadEntitiesComponent (Visual Effect)

This component is responsible for loading a visual effect that appears when the spawner is active.

*   `entity_file`: `data/entities/particles/image_emitters/magical_symbol.xml` - Specifies the particle effect to be loaded.
*   `count.min`: `1`
*   `count.max`: `1`
*   `kill_entity`: `0` - The visual effect entity is not killed when this spawner is removed.

### LifetimeComponent

Determines how long the spawner entity itself persists.

*   `lifetime`: `240` - The spawner will exist for 240 frames.

### Entity (Monster Spawns)

This section defines multiple `Entity` blocks, each responsible for spawning a specific type of monster.

#### LoadEntitiesComponent (Monster Spawning)

Each monster spawn entity uses this component to load and manage the spawned creature.

*   `entity_file`: Specifies the XML file for the monster to be spawned (e.g., `gate_monster_a.xml`, `gate_monster_b.xml`, etc.). These are located in `data/entities/animals/boss_gate/`.
*   `count.min`: `1`
*   `count.max`: `1` - Only one of each specified monster type will be spawned.
*   `kill_entity`: `1` - The spawned monster entity will be killed when this spawner is removed.
*   `timeout_frames`: `220` to `235` - The time in frames after which the spawned monster will be automatically killed if not already defeated. This acts as a despawn timer.

#### InheritTransformComponent

Used to position each spawned monster relative to the spawner's origin.

*   `Transform`: Defines the `position.x` and `position.y` offsets for each monster.

### CellEaterComponent

This component clears out a circular area around the spawner.

*   `radius`: `140` - The radius of the area to be cleared.
*   `eat_probability`: `2` - Controls the likelihood of cells being eaten.
*   `ignored_material`: `rock_box2d_nohit_hard` - Specifies materials that should not be cleared.

### ParticleEmitterComponent

Responsible for emitting cosmetic particles around the spawner.

*   `emitted_material_name`: `spark_red` - The material of the particles being emitted.
*   `lifetime_min`/`lifetime_max`: `0.4` to `1.2` - The duration of each particle.
*   `area_circle_radius.min`/`area_circle_radius.max`: `0` to `150` - The area in which particles are emitted.
*   `count_min`/`count_max`: `100` - The number of particles emitted per emission cycle.
*   `emission_interval_min_frames`/`emission_interval_max_frames`: `1` - Particles are emitted every frame.
*   `is_emitting`: `1` - The particle emitter is active.