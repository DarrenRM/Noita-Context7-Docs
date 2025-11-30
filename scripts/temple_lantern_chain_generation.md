---
title: Temple Lantern Chain Generation
category: scripts
---

# Temple Lantern Chain Generation

This script dynamically generates a chain for a temple lantern, attaching it to the ceiling. It calculates the required chain length based on the distance to the nearest platform above and creates individual chain segments with physics components.

## Key Attributes and Functionality

### Chain Generation Parameters

*   **`segment_length`**: The length of each individual chain segment.
*   **`search_dist`**: The maximum distance to search for a ceiling platform.
*   **`break_force_mid`**: The force required to break a middle chain segment.
*   **`break_force_end`**: The force required to break the end chain segments (attached to the lantern and ceiling).
*   **`break_distance_end`**: The distance threshold for breaking end chain segments.
*   **`break_distance_mid`**: The distance threshold for breaking middle chain segments.

### Chain Material and Graphics

*   **`mat`**: The material used for the chain segments. In this case, it's `"metal_chain_nohit"`.
*   **`image_file`**: The graphical asset used for each chain segment (`"data/props_gfx/torch_hang_chain.png"`).

### Chain Segment Creation

The script iterates to create multiple chain segments:

1.  **Bottom Segment**: Attached to the root entity (ID 100) with a `REVOLUTE_JOINT`.
2.  **Middle Segments**: Created in a loop until the ceiling is reached. Each segment is connected to the previous one with a `REVOLUTE_JOINT`.
3.  **Ceiling Attachment**: The topmost segment is attached to the nearest surface above using `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`.

### Physics Components

*   **`PhysicsImageShapeComponent`**: Defines the physical shape and visual representation of each chain segment.
*   **`PhysicsJoint2Component`**: Connects the chain segments together and to the ceiling, defining joint types, offsets, and break conditions.

### Initialization and Cleanup

*   **`PhysicsBody2InitFromComponents( entity_id )`**: Initializes the physics body for the entity based on its components.
*   **`EntitySetComponentIsEnabled( entity_id, GetUpdatedComponentID(), false)`**: Disables the script component after it has finished its execution.

---

**Note:** This script is designed to be attached to an entity that will act as the anchor point for the chain. The `offset_x` and `offset_y` variables determine the initial positioning of the chain relative to this anchor.