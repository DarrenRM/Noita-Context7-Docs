---
title: Minit Reward Entity
category: entities
---

# Minit Reward Entity

This entity represents a special reward, likely dropped by a boss centipede, that grants a significant amount of gold.

## Key Components

### Base Entity
The `Base` component inherits properties from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`, indicating it's a type of gold reward.

### UI Info Component
- **`name`**: `$reward_minit` - This likely serves as an internal identifier and potentially a localization key for UI elements.

### Item Component
- **`item_name`**: `$reward_minit` - Similar to `UIInfoComponent`, this links the entity to an item definition, likely for inventory or display purposes.

### Physics Image Shape Component
- **`image_file`**: `data/entities/animals/boss_centipede/rewards/reward_minit.png` - Specifies the visual representation of this reward entity.

### Variable Storage Component
- **`name`**: `end_gold` - This component stores a variable named `end_gold`.
- **`value_int`**: `100000` - The integer value associated with `end_gold` is 100,000, signifying the amount of gold awarded.