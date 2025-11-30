---
title: Wand Experimenter Perk
category: scripts
---

---

# Wand Experimenter Perk

This perk modifies wand behavior, granting the player health based on how many times a wand has been fired. The amount of health restored is influenced by whether the wand shuffles its spell deck when empty.

## Core Functionality

The `wand_fired` function is triggered when a wand is used. It checks the `AbilityComponent` of the wand for specific statistics to determine the health restoration amount.

### Key Attributes & Logic

*   **`stat_times_player_has_shot`**: This stat on the `AbilityComponent` tracks how many times the wand has been fired.
*   **`stat_times_player_has_edited`**: If this stat is greater than 0, the perk's healing effect is disabled. This suggests the perk is intended for wands that haven't been modified by the player.
*   **`shuffle_deck_when_empty`**: This configuration value within the wand's `gun_config` determines if the spell deck shuffles.
    *   If `0` (false), the wand does *not* shuffle.
    *   If `1` (true), the wand *does* shuffle.

### Health Restoration Calculation

The amount of health restored (`heal`) is calculated based on `stat_times_player_has_shot` and `shuffle_deck_when_empty`. The base values are then divided by 25.

#### Non-Shuffling Wands (Base Heal Values)

| Shots Fired | Base Heal |
| :---------- | :-------- |
| 1           | 30        |
| 2           | 15        |
| 3           | 9         |
| 4           | 6         |
| 5           | 4         |
| 6           | 3         |
| 7           | 2         |

#### Shuffling Wands (Base Heal Values)

| Shots Fired | Base Heal |
| :---------- | :-------- |
| 1           | 48        |
| 2           | 24        |
| 3           | 12        |
| 4           | 8         |
| 5           | 6         |
| 6           | 4         |
| 7           | 2         |

### Player Healing

The `heal_entity(player_id, heal)` function is called to restore health to the player.