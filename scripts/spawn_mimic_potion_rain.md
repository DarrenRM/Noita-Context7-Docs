---
title: Spawn Mimic Potion Rain
category: scripts
---

# Spawn Mimic Potion Rain

This script is responsible for spawning a "mimic potion" entity from the sky, simulating a potion rain effect.

## Key Functionality

*   **Entity Spawning:** Creates an instance of `data/entities/animals/mimic_potion.xml`.
*   **Randomized Placement:** The spawned mimic potion is positioned randomly within a defined horizontal range and a specific vertical offset from the script's origin.
*   **Tag Propagation:** If the spawning entity has the tag "mimic\_potion\_sky", the spawned mimic potion will also inherit this tag. This is likely used for further game logic or visual effects.
*   **Screen Shake:** Triggers a screen shake effect to emphasize the spawning event.

## Core Attributes

| Attribute        | Description