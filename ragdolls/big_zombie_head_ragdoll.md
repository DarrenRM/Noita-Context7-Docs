---
title: Big Zombie Head Ragdoll
category: data/ragdolls
---

```

# Big Zombie Head Ragdoll

This documentation describes the ragdoll configuration for the "Big Zombie" entity's head in Noita.

## Ragdoll Filenames

This section details the image files used for the Big Zombie's head ragdoll.

### Head Image

*   **File:** `data/ragdolls/bigzombie/head.png`
    *   This is the primary image asset for the Big Zombie's head ragdoll. It defines the visual appearance and collision shape of the head when it detaches or is affected by physics.

## Key Attributes (Implied from Filename)

While the provided `filenames_head.txt` only contains the image path, a typical ragdoll configuration in Noita would involve several key attributes that are not explicitly listed here but are crucial for its behavior. These would typically be defined in a corresponding `.xml` file.

### Potential Ragdoll Attributes (Not in Source)

*   **`sprite`**: The primary visual sprite for the ragdoll part.
*   **`material`**: The material properties (e.g., friction, bounciness) of the ragdoll part.
*   **`mass`**: The physical mass of the ragdoll part.
*   **`damping`**: How quickly the ragdoll part loses momentum.
*   **`friction`**: The resistance to sliding against other surfaces.
*   **`restitution`**: The bounciness of the ragdoll part.
*   **`collision_shape`**: The geometric shape used for physics calculations.
*   **`anchor`**: Points where the ragdoll part is attached to other parts or the main entity.
*   **`joint_limits`**: Constraints on the movement of connected ragdoll parts.
*   **`physics_material`**: Defines physical properties like density and elasticity.

**Note:** The actual `.xml` file for this ragdoll would contain the detailed physics and visual properties. The `filenames_head.txt` file serves as a simple reference to the image asset.