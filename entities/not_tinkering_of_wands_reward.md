---
title: Not Tinkering of Wands Reward
category: entities
---

# Not Tinkering of Wands Reward

This entity represents a special reward, specifically the "Not Tinkering of Wands" item, which is likely intended to prevent players from tinkering with wands. It's designed to be dropped by the boss centipede.

## Key Attributes

*   **`tags`**: `teleportable_NOT` - Indicates this entity cannot be teleported.
*   **`Base`**: Inherits properties from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`.
    *   **`UIInfoComponent`**:
        *   `name`: `$reward_notinkeringofwands` - The internal identifier for UI display.
    *   **`ItemComponent`**:
        *   `item_name`: `$reward_notinkeringofwands` - The name of the item in the game.
    *   **`PhysicsImageShapeComponent`**:
        *   `image_file`: `data/entities/animals/boss_centipede/rewards/reward_notinkeringofwands.png` - The visual representation of the reward.
*   **`VariableStorageComponent`**:
    *   `name`: `end_gold` - A variable likely related to gold.
    *   `value_int`: `100000` - Stores an integer value of 100,000, suggesting a significant gold reward associated with this item.