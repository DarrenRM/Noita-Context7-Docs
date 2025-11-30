---
title: Physics Trap Ignite Script
category: scripts
---

---

# Physics Trap Ignite Script

This script is designed to ignite entities when they are submerged in liquids. It achieves this by spawning multiple `fire_5_frames.xml` entities around the triggering entity's position.

## Core Functionality

The primary purpose of this script is to create an "ignition trap" effect. When an entity with this script attached comes into contact with a liquid, it triggers the spawning of fire entities.

### Key Elements

*   **`EntityLoad`**: This function is used to spawn other entities into the game world.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity currently being processed by the script.
*   **`EntityGetTransform()`**: Gets the position (x, y coordinates) of an entity.
*   **`offset`**: A local variable defining a fixed distance used to position the spawned fire entities relative to the triggering entity.

### Script Logic

1.  **Get Entity Information**: The script first obtains the `entity_id` and its `x`, `y` coordinates.
2.  **Define Offset**: An `offset` of `8` is set. This value determines how far away from the original entity the fire will be spawned.
3.  **Spawn Fire Entities**: The script then calls `EntityLoad` four times to spawn `data/entities/misc/fire_5_frames.xml` at positions:
    *   `x + offset, y` (to the right)
    *   `x - offset, y` (to the left)
    *   `x, y + offset` (below)
    *   `x, y - offset` (above)

This arrangement ensures that fire is generated in multiple directions around the entity, creating a more impactful ignition effect.

## Usage in Modding

This script can be attached to any entity that you want to act as an "ignition trap." For example, you could attach it to a physics-based prop that, when touched by water or other liquids, bursts into flames.

### Example Integration

To use this script, you would typically include it in the `[scripted_component]` of an entity's XML definition.

```xml
<entity name="my_ignitable_prop">
    <physics_trap_ignite/>
    <!-- Other components -->
</entity>
```

When `my_ignitable_prop` interacts with a liquid, the `physics_trap_ignite.lua` script will execute, spawning the fire entities as described above.