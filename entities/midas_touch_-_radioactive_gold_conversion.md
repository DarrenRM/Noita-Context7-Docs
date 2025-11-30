---
title: Midas Touch - Radioactive Gold Conversion
category: entities
---

# Midas Touch - Radioactive Gold Conversion

This entity implements a "Midas Touch" effect, converting entities into radioactive gold.

## Core Functionality

The primary function of this entity is to trigger a conversion process.

### `ConvertEverythingToGold`

This function is the core of the entity's behavior.

*   **`target_material`**: `"gold_radioactive"` - Specifies the material to convert entities into. This material is radioactive.
*   **`static_material`**: `"gold_static_radioactive"` - Specifies the material for static entities (like terrain) that are converted. This material is also radioactive.

This function is designed to be called when a specific event or condition is met within the game, leading to a widespread transformation of game elements into a radioactive gold variant.