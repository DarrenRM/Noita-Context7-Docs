---
title: Peace Reward Entity
category: entities
---

# Peace Reward Entity

This entity represents a special reward, likely dropped by a boss centipede, that grants a significant amount of gold.

## Key Components

### Base Entity
The entity inherits its core functionality from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`.

### UIInfoComponent
*   **name**: `$reward_peace` - This likely defines the in-game name or identifier for the reward.

### ItemComponent
*   **item_name**: `$reward_peace` - Similar to `UIInfoComponent`, this links the entity to its item representation.

### PhysicsImageShapeComponent
*   **image_file**: `data/entities/animals/boss_centipede/rewards/reward_peace.png` - Specifies the visual asset for the reward.
*   **material**: `gold_b2` - Indicates the material properties, suggesting it's a type of gold.

### VariableStorageComponent
*   **name**: `end_gold` - This component stores a variable related to the gold amount.
*   **value_int**: `150000` - The integer value associated with `end_gold`, representing 150,000 units of gold.