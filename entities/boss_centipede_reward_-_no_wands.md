---
title: Boss Centipede Reward - No Wands
category: entities
---

# Boss Centipede Reward - No Wands

This entity represents a special reward dropped by the boss centipede in Noita. It provides a significant amount of gold and is designed to be a non-collectible, purely visual reward.

## Key Components

### Base Entity
The `Base` component inherits properties from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`, indicating it's a gold-based reward.

### UI Info Component
*   `name`: `$reward_nowands` - This likely defines the internal name or identifier for this reward in the UI.

### Item Component
*   `item_name`: `$reward_nowands` - Similar to the UIInfoComponent, this links the reward to a specific item identifier.

### Physics Image Shape Component
*   `image_file`: `data/entities/animals/boss_centipede/rewards/reward_nowands.png` - Specifies the visual asset used for this reward.

### Variable Storage Component
*   `name`: `end_gold` - This component stores a variable named `end_gold`.
*   `value_int`: `100000` - The integer value assigned to `end_gold` is 100,000. This is the primary effect of this reward, granting a large sum of gold.

## Entity Tags
*   `teleportable_NOT`: This tag indicates that the entity cannot be teleported.