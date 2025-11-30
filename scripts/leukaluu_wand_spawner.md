---
title: Leukaluu Wand Spawner
category: scripts
---

# Leukaluu Wand Spawner

This script handles the spawning of the Leukaluu wand and associated visual effects. It determines the spawn location, either at the player's current position or at a specific "ending_sampo_spot_mountain" if it exists, and then loads the necessary entities and plays a sound effect.

## Key Functionality

*   **Dynamic Spawn Location:** The script can spawn the Leukaluu wand at the player's current coordinates or at a predefined mountain location.
*   **Entity Loading:** It loads the `wand_leukaluu.xml` entity and a particle effect `magical_symbol.xml`.
*   **Sound Effect:** A specific sound effect is triggered upon spawning.

## Core Attributes

| Attribute             | Description