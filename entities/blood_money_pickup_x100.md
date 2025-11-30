---
title: Blood Money Pickup (x100)
category: entities
---

# Blood Money Pickup (x100)

This entity represents a pickup item in Noita, specifically a "Blood Money" item that grants 100 gold. It inherits its base properties from `goldnugget_x.xml` and modifies them to represent this specific reward.

## Key Attributes

### Entity Name
- `name`: `unknown` (This is a placeholder and likely intended to be more descriptive in a final build.)

### Base Entity
- `Base file`: `data/entities/items/pickup/goldnugget_x.xml`
  - This indicates that the item inherits its fundamental behavior and appearance from the generic gold nugget pickup.

### Components

#### UIInfoComponent
- `name`: `$reward_gold_statue`
  - This string likely refers to a localization key for the item's display name in the UI.

#### PhysicsImageShapeComponent
- `material`: `bloodgold_box2d`
  - Defines the physical material properties of the item, influencing its interaction with the game's physics engine.

#### ItemComponent
- `_tags`: `enabled_in_world`
  - Ensures the item is active and interactable when present in the game world.
- `item_name`: `$reward_gold_statue`
  - Similar to the `UIInfoComponent`, this likely links to a localization key for the item's name.

#### VariableStorageComponent
- `_tags`: `enabled_in_world`
  - Ensures the variable storage is active in the game world.
- `name`: `hp_value`
  - This component stores a variable named `hp_value`.
- `value_float`: `100`
  - The `hp_value` is set to `100`, which in this context represents the amount of gold this pickup grants.