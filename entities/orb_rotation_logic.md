---
title: Orb Rotation Logic
category: entities
---

---

# Orb Rotation Logic

This script defines the rotational movement logic for a boss wizard's orbiting orbs. It calculates the position of each orb based on its unique ID, the boss's position, and a frame-based rotation speed.

## Key Components

### Entity Identification

*   `entity_id`: The unique identifier for the current orb entity.
*   `boss_id`: The root entity ID of the boss wizard, used to get the boss's transform.

### Position Calculation

*   `x`, `y`: The current transform (position) of the boss wizard.
*   `count`: The total number of orbs in the rotation (set to 8).
*   `circle`: Represents a full circle in radians (`math.pi * 2`).
*   `inc`: The angular increment between each orb.
*   `dir`: The current direction/angle of the orb, calculated using its `id`, frame number, and a rotation speed multiplier.
*   `nx`, `ny`: The calculated new X and Y coordinates for the orb.

### Orb Placement

The orbs are positioned in a circular pattern around the boss. The `math.cos` and `math.sin` functions are used to determine the X and Y offsets from the boss's position, creating the circular orbit. An additional offset (`- 20`) is applied to the Y coordinate, likely to position the orbs slightly above or below the boss's center.

### Transform Update

*   `EntitySetTransform( entity_id, nx, ny )`: Updates the position of the current orb entity to its newly calculated coordinates.

## Logic Flow

1.  Get the current orb's entity ID and its root boss entity ID.
2.  Retrieve the boss's current transform (x, y coordinates).
3.  Check if the orb has a `VariableStorageComponent` with the key `wizard_orb_id`. This component stores the unique ID of the orb.
4.  If the component exists, retrieve the orb's `id`.
5.  Calculate the angular increment (`inc`) based on the total number of orbs.
6.  Determine the current direction (`dir`) of the orb, which is influenced by its `id`, the current game frame, and a rotation speed.
7.  Calculate the new X (`nx`) and Y (`ny`) coordinates for the orb based on its direction and a fixed radius (50 units) from the boss, with a vertical offset.
8.  Update the orb's transform to the calculated `nx`, `ny` position.