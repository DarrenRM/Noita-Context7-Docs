---
title: Personal Laser Perk
category: entities
---

# Personal Laser Perk

This entity defines the "Personal Laser" perk in Noita. When acquired, it grants the player a continuous laser beam that follows their cursor.

## Key Components

### LuaComponent
This component links the perk to its associated Lua script, which handles the logic for aiming and firing the laser.

*   **script_source_file**: `data/scripts/perks/personal_laser_aim.lua`
*   **execute_every_n_frame**: `1` (The script runs every frame, ensuring responsive aiming.)

### Entity (Inner)
This defines the actual laser projectile and its properties.

*   **tags**: `personal_laser` (Used for identification and potentially other game systems.)

#### InheritTransformComponent
This component is used to position the laser relative to the player.

*   **Transform**:
    *   **position.x**: `5` (Offset from the player's origin.)
    *   **position.y**: `0`

#### LaserEmitterComponent
This is the core component that defines the laser's behavior and appearance.

*   **laser**:
    *   **damage_to_entities**: `0.15` (Low damage to entities, suggesting it's not primarily for combat.)
    *   **damage_to_cells**: `3000` (High damage to environmental cells, useful for mining.)
    *   **max_length**: `54` (The maximum range of the laser beam.)
    *   **beam_radius**: `1.0` (The thickness of the laser beam.)
    *   **max_cell_durability_to_destroy**: `11` (How much durability a cell needs to have to be destroyed by the laser.)
    *   **root_entity_is_responsible_for_damage**: `1` (The main entity handles damage calculations.)
    *   **audio_enabled**: `0` (Disables general audio for the beam itself.)
    *   **audio_hit_always_enabled**: `1` (Ensures hit sounds are always played.)
    *   **hit_particle_chance**: `10` (Chance to spawn particles on hit.)
    *   **beam_particle_chance**: `80` (High chance to spawn particles along the beam.)
    *   **beam_particle_type**: `spark_green` (The type of particle effect for the beam.)