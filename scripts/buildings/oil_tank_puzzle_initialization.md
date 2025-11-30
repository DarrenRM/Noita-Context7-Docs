---
title: Oil Tank Puzzle Initialization
category: scripts/buildings
---

# Oil Tank Puzzle Initialization

This script initializes the `oiltank_puzzle` entity, specifically handling the random material assignment for its liquid content and updating a `MaterialAreaCheckerComponent`.

## Key Attributes and Elements

### Material Assignment

The script randomly selects a liquid material from a predefined list to fill the oil tank.

*   **`materials`**: A Lua table containing the possible liquid materials.
    *   `"water"`
    *   `"blood"`
    *   `"alcohol"`
    *   `"radioactive_liquid"`
    *   `"water_salt"`
    *   `"slime"`
    *   `"magic_liquid_berserk"`
    *   `"magic_liquid_charm"`
    *   `"oil"`

### Particle Effect

A particle effect is spawned to visually represent the initial liquid.

*   **`GameCreateParticle(mat, x+40, y-175, 10, 0, 0, false)`**: Spawns a particle of the chosen material (`mat`) at a specific offset from the entity's position.

### Material Area Checker Update

The script ensures the `MaterialAreaCheckerComponent` is correctly configured with the assigned material, but only on the first execution.

*   **`ComponentGetValue2(GetUpdatedComponentID(), "mTimesExecuted") == 0`**: This condition checks if the component's `mTimesExecuted` attribute is 0, meaning it's the first time the script is running for this component.
*   **`component_write( EntityGetFirstComponent( entity_id, "MaterialAreaCheckerComponent"), { material = mat_id, material2 = mat_id } )`**: If it's the first execution, this line updates the `MaterialAreaCheckerComponent` to use the `mat_id` (the numerical ID of the chosen material) for both `material` and `material2` properties. This ensures the checker accurately reflects the liquid present.