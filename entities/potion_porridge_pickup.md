---
title: Potion Porridge Pickup
category: entities
---

# Potion Porridge Pickup

This entity defines a pickup item in Noita: the Porridge Potion. It inherits its base functionality from the generic `potion.xml` entity and specifically sets its material type to "porridge".

## Key Attributes

*   **`Base`**: Inherits properties from `data/entities/items/pickup/potion.xml`. This means it functions as a standard potion pickup with typical behaviors like being collectible and potentially having effects when consumed.
*   **`VariableStorageComponent`**:
    *   `name`: `potion_material`
    *   `value_string`: `porridge`
        This is the crucial attribute that distinguishes this potion from others. It assigns the "porridge" material to this specific potion pickup. This likely influences its visual appearance, its effect when consumed, or how it interacts with other game mechanics.