---
title: Alcohol Potion Pickup
category: entities
---

# Alcohol Potion Pickup

This document describes the configuration for the Alcohol Potion pickup item in Noita, intended for AI-assisted modding.

## Entity Configuration

The Alcohol Potion is a pickup item that inherits its base functionality from the generic `potion.xml` entity. Its unique characteristic is defined by a `VariableStorageComponent`.

### Key Components

*   **`Base`**:
    *   `file`: `data/entities/items/pickup/potion.xml`
        *   This indicates that the Alcohol Potion reuses the fundamental properties and behaviors of a standard potion pickup.

*   **`VariableStorageComponent`**:
    *   `name`: `potion_material`
        *   This component is used to store specific variables associated with the potion.
    *   `value_string`: `alcohol`
        *   This is the crucial attribute that identifies this potion as containing "alcohol." This value is likely used by other game systems (e.g., crafting, status effects, spell interactions) to determine the potion's specific properties and effects.