---
title: Boss Centipede Crown Reward
category: entities
---

# Boss Centipede Crown Reward

This entity defines the reward dropped by the Boss Centipede, specifically a "crown" item.

## Key Components

### Base Entity

The `Base` component inherits properties from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`. This suggests it's a variation of a general gold reward.

### UIInfoComponent

*   **name**: `$reward_crown` - This likely serves as an internal identifier and potentially for UI display text.

### ItemComponent

*   **item_name**: `$reward_crown` - Links this entity to the item definition for the crown.

### PhysicsImageShapeComponent

*   **image_file**: `data/entities/animals/boss_centipede/rewards/reward_crown.png` - Specifies the visual representation of the reward.

### VariableStorageComponent

*   **name**: `end_gold` - This component stores a variable named `end_gold`.
*   **value_int**: `350000` - The integer value associated with `end_gold`, indicating a significant amount of gold.