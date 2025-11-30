---
title: Slime Potion Pickup
category: entities
---

# Slime Potion Pickup

This entity defines a pickup item in Noita that represents a Slime Potion. It inherits its base functionality from the generic `potion.xml` entity and specifically sets its material type to "slime".

## Key Attributes

*   **`Base`**: Inherits properties from `data/entities/items/pickup/potion.xml`. This means it functions as a standard potion pickup with typical behaviors like being throwable and consumable.
*   **`VariableStorageComponent`**:
    *   `name`: `potion_material`
    *   `value_string`: `slime`
        This is the crucial attribute that distinguishes this potion from others. It designates the potion's material as "slime", which will affect its properties when consumed or interacted with in the game world.