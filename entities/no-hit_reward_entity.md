---
title: No-Hit Reward Entity
category: entities
---

# No-Hit Reward Entity

This entity defines a special reward that can be obtained in Noita, specifically a "no-hit" reward. It's designed to be a high-value item, likely awarded for achieving a significant challenge like defeating a boss without taking damage.

## Key Components

### Base Entity
This reward inherits its core functionality from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`. This suggests it's a type of gold reward with additional specific properties.

### UIInfoComponent
*   `name`: `$reward_nohit` - This likely defines the internal name or identifier used for displaying information about this reward in the game's UI.

### ItemComponent
*   `item_name`: `$reward_nohit` - Similar to `UIInfoComponent`, this specifies the name of the item as it would appear in an inventory or tooltip.

### PhysicsImageShapeComponent
*   `image_file`: `data/entities/animals/boss_centipede/rewards/reward_nohit.png` - This points to the visual asset used to represent the reward in the game world.

### VariableStorageComponent
*   `name`: `end_gold` - This component stores a variable named `end_gold`.
*   `value_int`: `500000` - The integer value associated with `end_gold` is 500,000. This strongly suggests that obtaining this reward grants the player a substantial amount of gold.

## Entity Tags
*   `teleportable_NOT`: This tag indicates that this entity cannot be teleported.