---
title: Larpa Downwards Projectile Script
category: scripts
---

# Larpa Downwards Projectile Script

This script defines the behavior for a projectile that shoots another projectile downwards. It's designed to be attached to a projectile entity.

## Key Functionality

*   **Projectile Spawning:** When the projectile is active, it spawns a new projectile based on a specified `projectile_file`.
*   **Directional Velocity:** The spawned projectile is always directed downwards with a significant velocity.
*   **Tagging:** The spawned projectile is tagged with `"projectile_cloned"` for potential further processing or identification.

## Core Attributes

*   `projectile_file`: (String) A variable storage component that specifies the file path of the projectile to be spawned. This is the most crucial attribute for determining what the "larpa" projectile will actually shoot.
*   `length`: (Number) Defines the magnitude of the downward velocity. A higher value means faster downward movement.
*   `vel_x`, `vel_y`: (Numbers) These are set internally to `0` and `length` respectively, ensuring the spawned projectile moves purely downwards.

## Script Logic Breakdown

1.  **Initialization:**
    *   Retrieves the root entity ID and its position.
    *   Sets a random seed based on game frame and entity position for potential future randomization.

2.  **Projectile File Retrieval:**
    *   Iterates through `VariableStorageComponent`s attached to the entity.
    *   Looks for a variable named `"projectile_file"`.
    *   If found, it stores the associated string value (the projectile file path) in the `projectile_file` variable.

3.  **Projectile Spawning:**
    *   Checks if `projectile_file` has been successfully loaded (i.e., its length is greater than 0).
    *   If a projectile file is specified:
        *   Sets `vel_x` to `0` and `vel_y` to `1700` (the `length`).
        *   Calls `shoot_projectile_from_projectile` to create the new projectile. This function takes the current entity's ID, the `projectile_file` path, its position, and the calculated velocities.
        *   Adds the tag `"projectile_cloned"` to the newly spawned projectile's entity ID.

## Example Usage (Conceptual)

To use this script, you would typically create a projectile entity and attach a `VariableStorageComponent` to it. This component would have a variable named `projectile_file` whose value is the path to another projectile `.lua` file (e.g., `"data/scripts/projectiles/my_custom_projectile.lua"`).

```lua
-- Example of how this script might be referenced in another projectile's definition
-- (This is NOT part of the larpa_downwards.lua script itself)

-- In a projectile's .xml definition:
-- <Entity tags="projectile,script_user">
--     <VariableStorageComponent
--         name="projectile_file"
--         value_string="data/scripts/projectiles/larpa_downwards.lua"
--     />
--     <LuaComponent
--         script_path="data/scripts/projectiles/larpa_downwards.lua"
--     />
--     ... other components ...
-- </Entity>
```