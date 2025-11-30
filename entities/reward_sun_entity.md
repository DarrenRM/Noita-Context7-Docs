---
title: Reward Sun Entity
category: entities
---

# Reward Sun Entity

This document describes the `reward_sun.xml` entity, which represents a special reward item in Noita, likely dropped by a boss centipede.

## Entity Definition

The core of the entity is defined by an `<Entity>` tag.

### Key Attributes

*   **`tags="teleportable_NOT"`**: This tag indicates that the entity cannot be teleported.

### Base Entity Inheritance

*   **`<Base file="data/entities/animals/boss_centipede/rewards/gold_reward.xml">`**: This entity inherits its base properties from `gold_reward.xml`, suggesting it's a type of gold reward with specific modifications.

### Components

#### UIInfoComponent

*   **`name="$reward_sun"`**: This likely defines the internal name or identifier used for UI elements related to this reward.

#### ItemComponent

*   **`item_name="$reward_sun"`**: This component assigns an item name to the entity, which would be used in inventory or other item-related contexts.

#### PhysicsImageShapeComponent

*   **`image_file="data/entities/animals/boss_centipede/rewards/reward_sun.png"`**: Specifies the visual representation of the reward, a PNG image file.

#### VariableStorageComponent

*   **`name="end_gold"`**: This component stores a variable named `end_gold`.
*   **`value_int="70000"`**: The integer value associated with `end_gold` is 70000. This strongly suggests the reward provides a significant amount of gold to the player.