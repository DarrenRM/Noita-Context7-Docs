---
title: Mimic Potion AI
category: scripts
---

# Mimic Potion AI

This script defines the behavior for the Mimic Potion entity in Noita, focusing on its AI and interactions within the game world.

## Core Functionality

The Mimic Potion acts as a unique entity that can transform into a "Sea Mimic" under specific conditions. Its behavior is tied to its internal state (filled with mimic liquid) and external factors like being charmed.

### Key Attributes and Behaviors

*   **Enemy Tag Removal:** The `init` function removes the "enemy" tag from the Mimic Potion. This is a specific fix to prevent issues with the `RISKY_CRITICAL` game effect, which relies on this tag to detect nearby enemies.
*   **Sea Mimic Transformation:** The `death` function handles the potential transformation into a "Sea Mimic".
    *   It checks if the potion is "filled" (i.e., contains mimic liquid).
    *   It also checks if the potion does *not* have the "mimic\_potion\_sky" tag.
    *   If these conditions are met, there's a 1 in 5 chance to spawn a "SEA\_MIMIC" item at the potion's location.
*   **Enabled State Management:** The `enabled_changed` function is crucial for managing the potion's components and tags based on its enabled state and parent entity.
    *   **Homing Target Tag:** If the potion has a parent entity (meaning it's held or attached), the "homing\_target" tag is removed. Otherwise, it's added. This likely affects how other entities target it.
    *   **Child Component Enabling:** When the potion is enabled, it iterates through its children and ensures that components tagged with "enabled\_in\_world" are also enabled.
*   **Charmed State:** The main update loop checks if the potion is charmed.
    *   If charmed, components tagged "enabled\_if\_charmed" are enabled.
    *   If not charmed, these components are disabled.
*   **Unconscious State:** When the potion is empty (not filled with mimic liquid) and not held by a parent, it enters an "unconscious" state. This is controlled by enabling/disabling components tagged "alive".
*   **Limping Animation:** The `is_limp` property of the `IKLimbsAnimatorComponent` is set based on whether the potion is alive (filled) or not.
*   **Random Noises:** When alive, the potion has a chance to play random sounds, either a "jump" sound or a "damage/projectile" sound.
*   **Awakening Logic:**
    *   If the potion is alive and has a `VariableStorageComponent` named "potion\_mimic\_awoken" that is not yet true, it sets the variable to true.
    *   This action increments a global counter `potion_mimics_awoken`, tracking how many mimic potions have been "awoken".

### Key Variables and Components

*   `mimic_liquid`: The material type representing a filled mimic potion.
*   `"enemy"` tag: Used by other game mechanics, removed from the mimic potion.
*   `"mimic_potion_sky"` tag: Prevents transformation into a Sea Mimic under certain conditions.
*   `"homing_target"` tag: Influences targeting behavior.
*   `"enabled_in_world"` tag: Used for enabling child components.
*   `"enabled_if_charmed"` tag: Controls component states when charmed.
*   `"alive"` tag: Manages the potion's active state when empty.
*   `IKLimbsAnimatorComponent`: Controls the animation, specifically the "is\_limp" property.
*   `VariableStorageComponent` (named "potion\_mimic\_awoken"): Tracks if the potion has been "awoken".
*   `GlobalsGetValue`/`GlobalsSetValue`: Used to manage the global count of awoken mimic potions.

---