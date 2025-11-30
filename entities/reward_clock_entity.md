---
title: Reward Clock Entity
category: entities
---

# Reward Clock Entity

This document describes the `reward_clock.xml` entity, which represents a special reward item in Noita.

## Entity Definition

The `reward_clock` entity is a special reward, likely dropped by a boss (indicated by its parent folder). It's designed to be non-teleportable.

### Key Components

*   **`Base`**: Inherits properties from `data/entities/animals/boss_centipede/rewards/gold_reward.xml`. This suggests it's a type of gold reward.
    *   **`UIInfoComponent`**: Defines the in-game name for the UI, set to `$reward_clock`.
    *   **`ItemComponent`**: Specifies the item name for inventory and crafting purposes, also `$reward_clock`.
    *   **`PhysicsImageShapeComponent`**: Sets the visual representation of the reward, using `reward_clock.png`.

*   **`VariableStorageComponent`**:
    *   **`name="end_gold"`**: This variable stores the amount of gold awarded.
    *   **`value_int="100000"`**: The reward grants a substantial amount of 100,000 gold.

```xml
<Entity tags="teleportable_NOT">
  <Base file="data/entities/animals/boss_centipede/rewards/gold_reward.xml" >
    <UIInfoComponent              name="$reward_clock"/>
    <ItemComponent                item_name="$reward_clock" />
    <PhysicsImageShapeComponent   image_file="data/entities/animals/boss_centipede/rewards/reward_clock.png" />
  </Base>

  <VariableStorageComponent
    name="end_gold"
    value_int="100000" >
  </VariableStorageComponent>
</Entity>
```