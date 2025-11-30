---
title: Vomit Potion Pickup
category: entities
---

# Vomit Potion Pickup

This document describes the `potion_vomit.xml` entity, which represents a pickup item in Noita that, when consumed, applies the "vomit" effect.

## Entity Definition

The `potion_vomit.xml` entity inherits its base functionality from `data/entities/items/pickup/potion.xml`.

### Key Components

*   **`Base`**: Inherits from `data/entities/items/pickup/potion.xml`, providing the fundamental behavior of a potion pickup item.
*   **`VariableStorageComponent`**: This component is crucial for defining the specific type of potion.
    *   `name`: "potion_material"
    *   `value_string`: "vomit" - This attribute specifies that the potion's effect is related to "vomit".

## Functionality

When this entity is picked up and consumed by the player, it will trigger the effects associated with the "vomit" material. The exact in-game behavior of the "vomit" effect is determined by other game systems and data files that reference this material.

## AI Modding Considerations

For AI modding, understanding this entity means recognizing it as a specific type of potion. If an AI needs to interact with or identify potions, it would look for entities with a `VariableStorageComponent` where `potion_material` is set to "vomit". This allows for targeted AI behavior, such as avoiding these potions, collecting them, or reacting to their effects.