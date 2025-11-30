---
title: Cape Verlet Physics
category: entities
---

---

# Cape Verlet Physics

This document describes the `VerletPhysicsComponent` and `InheritTransformComponent` used to define the physics and behavior of a cape entity in Noita.

## VerletPhysicsComponent

This component governs the cloth-like physics simulation for the cape.

### Key Attributes:

*   **`num_points`**: The number of simulation points used for the cloth. A higher number allows for more detailed and fluid simulation.
    *   **Value**: `150`
*   **`width`**: The effective width of the cloth simulation.
    *   **Value**: `10`
*   **`type`**: Specifies the type of physics simulation. `CLOTH` indicates a fabric-like behavior.
    *   **Value**: `CLOTH`
*   **`stiffness`**: Controls how rigid the cloth is. Higher values make it stiffer.
    *   **Value**: `1.5`
*   **`velocity_dampening`**: Reduces the velocity of the cloth points over time, simulating air resistance or friction.
    *   **Value**: `0.55`
*   **`resting_distance`**: The preferred distance between simulation points when the cloth is at rest.
    *   **Value**: `1.0`
*   **`simulate_wind`**: Enables or disables wind simulation affecting the cloth.
    *   **Value**: `1` (Enabled)
*   **`constrain_stretching`**: Prevents the cloth from stretching beyond its natural length.
    *   **Value**: `1` (Enabled)
*   **`collide_with_cells`**: Enables collision detection between the cloth and the game's environment cells.
    *   **Value**: `1` (Enabled)
*   **`mass_min`**: The minimum mass assigned to individual simulation points.
    *   **Value**: `0.1`
*   **`mass_max`**: The maximum mass assigned to individual simulation points.
    *   **Value**: `0.2`
*   **`cloth_sprite_z_index`**: The Z-index for rendering the cloth sprite, determining its layering.
    *   **Value**: `0.7`

## InheritTransformComponent

This component allows the cape's transform (position, rotation, scale) to inherit from another entity's specified hotspot.

### Key Attributes:

*   **`parent_hotspot_tag`**: The tag of the hotspot on the parent entity from which this entity's transform will be inherited. This is crucial for attaching the cape to a character.
    *   **Value**: `cape_root`