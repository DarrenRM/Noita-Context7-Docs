---
title: Dollar Reward Entity
category: entities
---

# Dollar Reward Entity

This entity represents a large dollar reward, likely dropped by a boss enemy. It inherits its base functionality from `gold_reward.xml` and is primarily defined by its visual representation and the amount of gold it provides.

## Key Attributes

### Entity
- **tags**: `teleportable_NOT` - Indicates this entity cannot be teleported.

### Base Entity (`data/entities/animals/boss_centipede/rewards/gold_reward.xml`)
This entity inherits core properties from a generic gold reward.

### UIInfoComponent
- **name**: `$reward_dollar` - The internal identifier for UI elements related to this reward.

### ItemComponent
- **item_name**: `$reward_dollar` - The internal identifier for this item when it's considered an inventory item.

### PhysicsImageShapeComponent
- **image_file**: `data/entities/animals/boss_centipede/rewards/reward_dollar.png` - Specifies the visual asset for this reward.

### VariableStorageComponent
- **name**: `end_gold` - A variable storage component.
- **value_int**: `100000` - The integer value representing the amount of gold this reward grants.