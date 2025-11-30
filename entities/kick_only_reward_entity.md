---
title: Kick Only Reward Entity
category: entities
---

# Kick Only Reward Entity

This entity defines a special reward for the boss centipede, specifically designed to be collected only through kicking.

## Key Components

### Base Entity
*   **file**: `data/entities/animals/boss_centipede/rewards/gold_reward.xml`
    *   This indicates that `reward_kicksonly` inherits its core functionality from a generic `gold_reward` entity.

### UI Info Component
*   **name**: `$reward_kicksonly`
    *   Defines the internal name and potentially UI display name for this reward.

### Item Component
*   **item\_name**: `$reward_kicksonly`
    *   Associates this entity with an item, likely for inventory or game logic purposes.

### Physics Image Shape Component
*   **image\_file**: `data/entities/animals/boss_centipede/rewards/reward_kicksonly.png`
    *   Specifies the visual representation of the reward in the game world.

### Variable Storage Component
*   **name**: `end_gold`
*   **value\_int**: `100000`
    *   This component stores a significant amount of gold (100,000), which is likely awarded to the player upon collection. The name `end_gold` suggests it might be a final reward.

## Entity Tags

*   **teleportable\_NOT**: This tag explicitly prevents the entity from being teleported.