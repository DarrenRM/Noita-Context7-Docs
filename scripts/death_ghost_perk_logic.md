---
title: Death Ghost Perk Logic
category: scripts
---

---

# Death Ghost Perk Logic

This script defines the behavior of the "Death Ghost" perk in Noita. When the player dies, this perk spawns spectral entities that deal damage over time.

## Core Functionality

The `death` function is the primary logic for this perk. It's triggered upon player death and handles the spawning and configuration of the death ghosts.

### Key Attributes and Elements

*   **`flag_name`**: `"PERK_PICKED_DEATH_GHOST"` - A global flag used to track if the perk has been picked up.
*   **`pickup_count`**: Tracks how many times the "Death Ghost" perk has been picked up by the player. This influences the number and power of spawned ghosts.
*   **`rat_count`**: Determines the number of death ghosts to spawn. It scales with `pickup_count`, with a minimum of 1 and a maximum of 10.
*   **`rats`**: A list of existing entities tagged as `"death_ghost"`. This is used to limit the total number of ghosts on screen.
*   **`EntityLoad("data/entities/misc/perks/death_ghost.xml", pos_x, pos_y)`**: Spawns a new death ghost entity at the player's death location.
*   **`LifetimeComponent`**: Configures the duration for which spawned ghosts will exist. This duration is randomized and decreases with the number of existing ghosts.
*   **`AreaDamageComponent`**: Sets the damage dealt by the death ghosts per frame. This damage increases with the `pickup_count` of the perk.

## Spawning Logic

The script iterates `rat_count` times to spawn ghosts.

*   **Randomization**: For subsequent ghosts (i > 1), there's a chance (`Random(1, 5) > 2`) that a ghost will *not* be spawned to add variability.
*   **Limit**: Spawning is also prevented if the total number of existing death ghosts (`#rats`) exceeds 30.

## Damage Scaling

The damage dealt by each death ghost is directly tied to the player's perk progression:

*   **Base Damage**: `0.07`
*   **Per-Pickup Bonus**: `pickup_count * 0.02`

This means that the more times the player picks up the "Death Ghost" perk, the more potent the spectral damage becomes.