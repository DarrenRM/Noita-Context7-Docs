---
title: Nolla Reward Entity
category: entities
---

# Nolla Reward Entity

This document describes the `reward_nolla.xml` entity, which represents a special reward, likely a large amount of gold, associated with the boss centipede in Noita.

## Entity Structure

The `reward_nolla` entity inherits from `gold_reward.xml` and defines specific attributes for its appearance and value.

### Key Components

*   **`Base`**: Inherits functionality from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`.
    *   **`UIInfoComponent`**: Defines the in-game name for this reward, `$reward_nolla`.
    *   **`ItemComponent`**: Specifies the internal item name as `$reward_nolla`.
    *   **`PhysicsImageShapeComponent`**: Sets the visual representation of the reward using the image file `data/entities/animals/boss_centipede/rewards/reward_nolla.png`.

*   **`VariableStorageComponent`**:
    *   **`name`**: `end_gold`
    *   **`value_int`**: `500000` - This indicates a significant amount of gold awarded.