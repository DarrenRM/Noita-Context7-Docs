---
title: Orbit Projectile Script
category: scripts
---

# Orbit Projectile Script

This script defines the behavior for projectiles that orbit other entities. It allows for customizable projectile types and speeds, enabling the creation of complex orbiting attack patterns.

## Core Functionality

The primary purpose of this script is to spawn and manage orbiting projectiles. It reads configuration from `VariableStorageComponent`s attached to the projectile entity to determine what kind of projectile to spawn and how fast it should orbit.

### Key Components and Variables

*   **`entity_id`**: The unique identifier for the current projectile entity.
*   **`root_id`**: The root entity ID, often used for accessing global variables or components.
*   **`projtype`**: A `VariableStorageComponent` that stores the *type* of projectile to be spawned (e.g., "orbit\_larpa").
*   **`projspeed`**: A `VariableStorageComponent` that stores the *speed* at which the orbiting projectile should move.
*   **`proj`**: The file path to the XML definition of the projectile to be spawned.
*   **`projfile`**: The string name of the projectile file (e.g., "orbit\_larpa").

## Orbiting Behavior

The script dynamically determines the orbiting projectile's properties and spawns multiple instances.

### Projectile Spawning Logic

1.  **Retrieve Projectile Type and Speed**: The script first checks for `VariableStorageComponent`s named `orbit_projectile_type` and `orbit_projectile_speed`.
2.  **Determine Projectile File**: Based on the `orbit_projectile_type` value, it constructs the path to the projectile's XML definition.
    *   **Special Case: `orbit_larpa`**: If the projectile type is "orbit\_larpa", it attempts to find the actual projectile file from a `VariableStorageComponent` named `projectile_file` on the root entity. This allows for more dynamic projectile selection for this specific orbit type.
3.  **Spawn Orbiting Projectiles**: If a valid projectile file is found:
    *   A random, non-zero speed is assigned to the `projspeed` component.
    *   The script then iterates four times, spawning a projectile using `shoot_projectile_from_projectile`.
    *   Each spawned projectile is added as a child to the orbiting projectile entity.
4.  **`orbit_larpa` Specific Modifications**: For "orbit\_larpa" projectiles, additional tags (`orbit_projectile`, `projectile_cloned`) are added, and their `LifetimeComponent` and `ProjectileComponent` are set to a long duration (7200 frames) to ensure they persist.

### `shoot_projectile_from_projectile` Function

This is a core Noita function used to spawn a projectile originating from another projectile.

```lua
-- Example usage within the script:
local eid = shoot_projectile_from_projectile( entity_id, proj, x, y, 0, 0 )
```

*   **`entity_id`**: The ID of the projectile from which the new projectile originates.
*   **`proj`**: The file path to the XML definition of the projectile to spawn.
*   **`x`, `y`**: The initial position of the spawned projectile.
*   **`0`, `0`**: Initial velocity components (often modified by other components or scripts).

## Configuration Example (Conceptual)

To use this script, you would typically attach `VariableStorageComponent`s to an entity that will act as the orbiting projectile.

```xml
<Entity tags="projectile">
    <VariableStorageComponent
        name="orbit_projectile_type"
        value_string="orbit_larpa" /> <!-- Or another projectile type -->

    <VariableStorageComponent
        name="orbit_projectile_speed"
        value_float="0.5" /> <!-- This value is randomized by the script -->

    <LuaComponent
        script_path="data/scripts/projectiles/orbit_projectile.lua" />
</Entity>
```

**Note:** The `value_float` for `orbit_projectile_speed` is a base value that the script will randomize. The actual speed will be a small random value between -0.1 and 0.1 (excluding 0).

### `orbit_larpa` Specific Configuration

For the `orbit_larpa` type, you would also need to ensure the root entity has the `projectile_file` variable:

```xml
<Entity tags="root">
    <!-- ... other components ... -->
    <VariableStorageComponent
        name="projectile_file"
        value_string="orbit_larpa" /> <!-- The actual projectile to spawn -->
    <!-- ... other components ... -->
</Entity>
```