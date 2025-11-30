---
title: Almost Pacifist Reward Entity
category: entities
---

# Almost Pacifist Reward Entity

This entity defines the reward for achieving an "almost pacifist" run, specifically associated with the boss centipede. It grants a significant amount of gold.

## Key Components

### Base Entity
*   **file**: `data/entities/animals/boss_centipede/rewards/gold_reward.xml` - Inherits core functionality from a generic gold reward.

### UI Info Component
*   **name**: `$reward_almostpacifist` - Defines the in-game name and UI identifier for this reward.

### Item Component
*   **item_name**: `$reward_almostpacifist` - Links this entity to the item definition used in the game's inventory and UI.

### Physics Image Shape Component
*   **image_file**: `data/entities/animals/boss_centipede/rewards/reward_almostpacifist.png` - Specifies the visual representation of the reward in the game world.

### Variable Storage Component
*   **name**: `end_gold` - Identifies the variable holding the gold amount.
*   **value_int**: `100000` - The specific amount of gold awarded (100,000).