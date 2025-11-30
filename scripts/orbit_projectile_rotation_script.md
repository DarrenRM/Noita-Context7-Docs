---
title: Orbit Projectile Rotation Script
category: scripts
---

---

# Orbit Projectile Rotation Script

This script manages the rotation and positioning of projectiles orbiting a central entity. It's designed to be attached to a parent entity that holds multiple "orbit projectile" children.

## Key Functionality

*   **Orbital Movement:** Calculates and applies positions and rotations for child projectiles to create an orbiting effect.
*   **Speed Control:** Uses a `VariableStorageComponent` to define the speed of the orbital rotation.
*   **Distance Adjustment:** Allows for different orbital distances, with a specific adjustment for projectiles tagged as "orbit\_laser".
*   **Frame-Based Animation:** The orbital angle is influenced by the current game frame number, creating continuous motion.

## Core Components & Attributes

### `VariableStorageComponent` (for speed)

*   **`orbit_projectile_speed`**: A float value determining how fast the projectiles orbit.

### Entity Tags

*   **`orbit_projectile`**: Applied to child entities that should participate in the orbital movement.
*   **`orbit_laser`**: Applied to specific projectiles that require a different orbital distance (closer to the center).

### Key Lua Variables & Functions

*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity this script is attached to.
*   **`EntityGetTransform( entity_id )`**: Gets the current position (x, y) of the parent entity.
*   **`EntityGetAllChildren( entity_id )`**: Retrieves all child entities of the parent.
*   **`ComponentGetValue2( component, "value_float" )`**: Extracts the float value from a `VariableStorageComponent`.
*   **`EntityHasTag( entity_id, tag_name )`**: Checks if an entity possesses a specific tag.
*   **`math.pi`**: Mathematical constant for pi.
*   **`GameGetFrameNum()`**: Returns the current game frame number.
*   **`math.cos( angle )`, `math.sin( angle )`**: Trigonometric functions used for calculating circular positions.
*   **`EntitySetTransform( entity_id, x, y, rotation )`**: Sets the position and rotation of an entity.
*   **`EntityApplyTransform( entity_id, x, y, rotation )`**: Applies the transform to an entity.

## Example Usage (Conceptual)

Imagine a parent entity with the `orbit_projectile_rotation.lua` script attached. It would also have several child entities, each with the `orbit_projectile` tag. One or more of these children might also have the `orbit_laser` tag. The parent entity would likely have a `VariableStorageComponent` named `orbit_projectile_speed` to control the rotation speed.

```lua
-- Example of a parent entity setup (not part of the script itself)
-- This would be defined in a .xml entity file

-- <Entity name="orbit_parent">
--     <VariableStorageComponent
--         name="orbit_projectile_speed"
--         value_float="0.05" /> -- Controls rotation speed
--     <ScriptComponent
--         script_filename="data/scripts/projectiles/orbit_projectile_rotation.lua" />
--
--     <Entity name="orbiting_orb_1">
--         <Tags>
--             <tag name="orbit_projectile" />
--         </Tags>
--         <!-- Other projectile components -->
--     </Entity>
--
--     <Entity name="orbiting_orb_2">
--         <Tags>
--             <tag name="orbit_projectile" />
--             <tag name="orbit_laser" /> -- This one will orbit closer
--         </Tags>
--         <!-- Other projectile components -->
--     </Entity>
-- </Entity>
```