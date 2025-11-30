---
title: Random Teleporter Script
category: scripts
---

---

# Random Teleporter Script

This script configures a teleporter entity to randomly select a destination from a predefined list of biome start positions.

## Key Components

### TeleportComponent
- **target**: The destination coordinates (x, y) for the teleport. This is dynamically set by the script.

### Entity Properties
- **enabled_by_script**: A tag used to control the teleporter's activation. The script ensures it's enabled only after initialization.

## Script Logic

1.  **Initialization**: Retrieves the entity's ID and current position.
2.  **Teleport Component Access**: Gets the `TeleportComponent` associated with the entity.
3.  **Biome Start Positions**: Defines a table `positions` containing hardcoded (x, y) coordinates for potential teleport destinations.
    ```lua
    local positions = {
        {970, 0},
        {190, 1525},
        {190, 3070},
        {190, 5118},
        {190, 6644},
        {190, 8704},
        {190, 10740},
    }
    ```
4.  **Random Destination Selection**: Uses `SetRandomSeed` based on the teleporter's position to ensure a consistent random choice for a given location. Then, `random_from_array` selects one of the predefined `positions`.
5.  **Target Assignment**: Updates the `TeleportComponent`'s `target` property with the randomly selected coordinates.
6.  **Activation Control**: Ensures the teleporter is enabled by setting the `enabled_by_script` tag to `true` only after its destination has been determined. This prevents premature activation.