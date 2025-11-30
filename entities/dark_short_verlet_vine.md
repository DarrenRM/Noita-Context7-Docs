---
title: Dark Short Verlet Vine
category: entities
---

# Dark Short Verlet Vine

This entity defines a short, dark-colored vine that uses Verlet physics for its movement and behavior. It's designed to attach to surfaces and sway realistically.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   **`num_points`**: `8` - The number of segments the vine is divided into for physics calculations. More points generally lead to smoother, more detailed movement.
*   **`stiffness`**: `1.0` - Controls how rigid the vine is. A value of 1.0 means it's quite stiff.
*   **`velocity_dampening`**: `0.9` - Reduces the velocity of the vine segments over time, causing it to eventually settle. A value closer to 1.0 means less dampening.
*   **`resting_distance`**: `4` - The ideal distance between connected points when the vine is not under stress.
*   **`simulate_wind`**: `1` - Enables the simulation of wind effects on the vine.
*   **`wind_change_speed`**: `0.25` - Controls how quickly the wind direction and strength can change.
*   **`simulate_gravity`**: `1` - Enables gravity to affect the vine.

## Base Components

The vine is constructed from several smaller vine segments, defined by individual `.xml` files. These files likely contain sprite information and collision properties for each part of the vine.

### Included Vine Segments:

*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_8.xml`

## MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attempts to attach itself to the nearest suitable surface.

### Key Attributes:

*   **`lookup_radius`**: `28` - The area around the creation point to search for a surface.
*   **`verlet_min_joint_distance`**: `14` - The minimum distance required between joints for the attachment to be considered valid.
*   **`type`**: `VERLET_ROPE_ONE_JOINT` - Specifies the type of attachment behavior, indicating it's a rope-like structure with a single primary joint for surface connection.

## AudioComponent

This component handles the sound effects associated with the vine, specifically for collisions.

### Key Attributes:

*   **`file`**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound events.
*   **`event_root`**: `collision/vine` - The root event name for vine-related collision sounds.