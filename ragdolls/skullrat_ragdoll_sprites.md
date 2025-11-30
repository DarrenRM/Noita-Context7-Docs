---
title: Skullrat Ragdoll Sprites
category: ragdolls
---

# Skullrat Ragdoll Sprites

This documentation describes the sprite assets used for the Skullrat ragdoll in Noita. These files define the visual components of the ragdoll when it is in a non-animated, physics-driven state.

## Sprite Files

The following image files are used to construct the Skullrat ragdoll. They are typically layered and positioned to create the full visual representation.

### Core Body Parts

*   `part1.png`
*   `part2.png`
*   `part3.png`
*   `part4.png`

### Tail Components

*   `tail1.png`
*   `tail2.png`

## Usage in Modding

When creating or modifying ragdolls, these sprite filenames would be referenced within the relevant `.xml` or `.lua` configuration files. The order and positioning of these sprites are crucial for the ragdoll's appearance.

**Example (Conceptual - actual implementation may vary):**

```lua
-- This is a simplified, conceptual example.
-- Actual ragdoll definitions are more complex and involve physics properties.

local skullrat_ragdoll_definition = {
    sprite_files = {
        "data/ragdolls/skullrat/part1.png",
        "data/ragdolls/skullrat/part2.png",
        "data/ragdolls/skullrat/part3.png",
        "data/ragdolls/skullrat/part4.png",
        "data/ragdolls/skullrat/tail1.png",
        "data/ragdolls/skullrat/tail2.png",
    },
    -- ... other ragdoll properties like physics, collision, etc.
}
```