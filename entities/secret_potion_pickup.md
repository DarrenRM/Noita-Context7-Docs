---
title: Secret Potion Pickup
category: entities
---

# Secret Potion Pickup

This entity defines a secret potion pickup item in Noita. It inherits its base functionality from the generic `potion.xml` and customizes its behavior with a specific Lua script.

## Key Components

### Base Entity

*   **`file="data/entities/items/pickup/potion.xml"`**: This indicates that the secret potion inherits all properties and behaviors from the standard potion pickup entity. This includes its visual representation, collision, and basic pickup mechanics.

### Lua Component

*   **`script_source_file="data/scripts/items/potion_secret.lua"`**: This is the core of the customization. This Lua script defines the unique effects and interactions of the secret potion when picked up. The specific logic for what makes this potion "secret" will be found within this script.

## Summary

The `potion_secret.xml` file is a simple entity definition that leverages an existing base entity (`potion.xml`) and applies a custom Lua script (`potion_secret.lua`) to create a distinct type of potion pickup. The actual unique properties of this potion are determined by the code within `potion_secret.lua`.