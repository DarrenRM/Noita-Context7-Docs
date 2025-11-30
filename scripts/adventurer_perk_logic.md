---
title: Adventurer Perk Logic
category: scripts
---

---

# Adventurer Perk Logic

This script defines the behavior for the "Adventurer" perk in Noita. When the player enters a new biome for the first time, they receive a small amount of healing and a message.

## Core Functionality

The primary function of this script is to grant a one-time healing bonus upon entering a biome the player has not previously visited.

### Key Attributes

*   **Healing Amount:** The perk provides a base healing of 60, which is then divided by 25 (resulting in 2.4 healing points).
*   **Biome Tracking:** A unique flag is created for each biome the player visits (e.g., `"adventurer_swamp_visited"`). This flag prevents the healing from being applied multiple times in the same biome.
*   **Player Identification:** The script identifies the player's entity ID and root entity ID to apply healing and display messages.
*   **Biome Detection:** It determines the current biome the player is in using `BiomeMapGetName`.
*   **Message Display:** Upon successful healing, the player receives the message `$log_adventurer`.

### Logic Flow

1.  **Get Player and Location:** The script first obtains the player's entity ID and their current coordinates to determine the biome.
2.  **Generate Biome Flag:** A unique flag string is constructed based on the current biome name.
3.  **Check for First Visit:** It checks if the player has already triggered this perk in the current biome using `GameHasFlagRun`.
4.  **Apply Healing and Flag:** If it's a first visit:
    *   The player is healed using `heal_entity`.
    *   The biome-specific flag is set using `GameAddFlagRun`.
    *   A confirmation message is displayed to the player.