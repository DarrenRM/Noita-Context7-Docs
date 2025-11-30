---
title: Laser Aim Perk
category: entities
---

# Laser Aim Perk

This entity defines the "Laser Aim" perk in Noita. It grants the player a laser beam that originates from their aiming direction.

## Key Components

### LuaComponent
This component links the perk to its associated Lua script, which handles the perk's logic and behavior.

*   **script_source_file**: `data/scripts/perks/laser_aim.lua` - The path to the script that controls the perk's functionality.
*   **execute_every_n_frame**: `1` - The script will execute every frame, allowing for real-time updates and responsiveness.

### LaserEmitterComponent
This component defines the properties of the laser beam itself.

*   **laser**: This nested element contains the specific attributes of the laser beam.
    *   **damage_to_entities**: `0` - The laser does not deal damage to entities.
    *   **damage_to_cells**: `0` - The laser does not damage environmental cells.
    *   **max_length**: `312` - The maximum distance the laser beam can extend.
    *   **beam_radius**: `0.5` - The thickness or width of the laser beam.
    *   **max_cell_durability_to_destroy**: `0` - The laser cannot destroy cells by depleting their durability.
    *   **audio_enabled**: `0` - No sound effects are played for the laser beam.
    *   **hit_particle_chance**: `0` - No particles are spawned when the laser hits something.
    *   **beam_particle_chance**: `50` - There is a 50% chance for particles to be spawned along the beam.
    *   **beam_particle_type**: `spark` - The type of particle spawned along the beam is "spark".