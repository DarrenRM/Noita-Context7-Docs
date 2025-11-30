---
title: Random Explosion Projectile
category: scripts/
---

# Random Explosion Projectile

This script defines a projectile that, upon collision, spawns a random projectile from a predefined list. This is useful for creating unpredictable and varied explosion effects.

## Key Components

### Projectile Behavior

*   **`on_collision_spawn_entity`**: When the projectile collides with something, it will spawn another entity.
*   **`spawn_entity_is_projectile`**: The entity to be spawned is itself a projectile.
*   **`spawn_entity`**: Specifies the entity XML file to spawn. This script dynamically sets this value.

### Randomization Logic

*   **`opts` Table**: A list of projectile names that can be randomly selected.
    *   `acidshot`
    *   `alcohol_blast`
    *   `black_hole_big`
    *   `cloud_thunder`
    *   `cloud_acid`
    *   `cloud_blood`
    *   `cloud_water`
    *   `death_cross`
    *   `death_cross_big`
    *   `fireball`
    *   `firebomb`
    *   `grenade`
    *   `grenade_tier_2`
    *   `grenade_tier_3`
    *   `lightning`
    *   `meteor`
    *   `nuke`
    *   `regeneration_field`
    *   `rocket`
    *   `rocket_tier_2`
    *   `rocket_tier_3`
    *   `tentacle_portal`
    *   `thunder_blast`
    *   `wall_square`
    *   `xray`
*   **`SetRandomSeed`**: Initializes the random number generator using the entity's ID for a consistent but unique seed per projectile instance.
*   **`Random(1, #opts)`**: Selects a random index from the `opts` table.
*   **`result = "data/entities/projectiles/deck/" .. opts[rnd] .. ".xml"`**: Constructs the full path to the randomly chosen projectile's XML file.

## Usage

This script is intended to be attached to a projectile entity. When this projectile collides, it will trigger the spawning of another projectile, chosen randomly from the `opts` list. This allows for creating effects like a "random explosion" that could manifest as a fireball, a lightning strike, or a black hole, depending on the random selection.