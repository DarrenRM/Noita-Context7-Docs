---
title: Stainless Armour Effect
category: entities
---

# Stainless Armour Effect

This entity defines the "Stainless Armour" effect in Noita, providing resistance to certain damage types.

## Key Components

### `GameEffectComponent`

This component governs the core functionality of the effect.

*   **`effect`**: `STAINLESS_ARMOUR` - Specifies the type of effect.
*   **`frames`**: `600` - The duration of the effect in frames (equivalent to 10 seconds).
*   **`_tags`**: `effect_resistance,effect_protection` - Tags indicating the nature of the effect.

### `InheritTransformComponent`

This component is present but has no specific configurable attributes in this instance, suggesting it's a standard placeholder for entity transformations.

## Summary

The `effect_stainless_armour.xml` file defines a temporary buff that grants the player resistance and protection. The primary configuration is within the `GameEffectComponent`, which sets the effect type to `STAINLESS_ARMOUR` and its duration to 600 frames.