---
title: Laser Shooter Ragdoll Sprites
category: ragdolls
---

---

# Laser Shooter Ragdoll Sprites

This documentation outlines the sprite assets used for the "Laser Shooter" entity's ragdoll. These files define the visual components of the ragdoll when the entity is defeated or its physics are simulated.

## Sprite Files

The following PNG files represent the individual sprite components of the Laser Shooter ragdoll.

### Torso

*   `data/ragdolls/lasershooter/torso.png`: The main body segment of the Laser Shooter.

### Tentacles

The Laser Shooter features multiple tentacle segments, likely for animation and physics simulation.

*   `data/ragdolls/lasershooter/tentacle_1_a.png`
*   `data/ragdolls/lasershooter/tentacle_1_b.png`
*   `data/ragdolls/lasershooter/tentacle_2_a.png`
*   `data/ragdolls/lasershooter/tentacle_2_b.png`
*   `data/ragdolls/lasershooter/tentacle_3_a.png`
*   `data/ragdolls/lasershooter/tentacle_3_b.png`
*   `data/ragdolls/lasershooter/tentacle_4_a.png`
*   `data/ragdolls/lasershooter/tentacle_4_b.png`

These tentacle sprites are likely paired (e.g., `_a` and `_b`) to represent different states or animation frames for each tentacle.

## Usage in Modding

When creating or modifying entities that utilize ragdoll physics, these sprite files would be referenced within the entity's definition or a dedicated ragdoll configuration file. The game engine uses these images to render the ragdoll's visual representation.

For AI-assisted modding, understanding these file names and their purpose is crucial for:

*   **Asset Replacement:** Swapping out existing ragdoll sprites with custom ones.
*   **New Entity Creation:** Defining the visual components for new ragdoll-based enemies or objects.
*   **Physics Configuration:** Associating these sprites with specific physics properties and joint configurations.