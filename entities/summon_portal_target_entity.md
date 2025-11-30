---
title: Summon Portal Target Entity
category: entities
---

# Summon Portal Target Entity

This entity defines a target for summon portals. It's a simple entity with a single tag.

## Key Attributes

*   **`tags`**: `summon_portal_target` - This tag is crucial for identifying this entity as a valid destination for summon portals.

## Usage

This entity is primarily used internally by the game to designate specific locations or objects as potential targets for summon portals. When a summon portal is activated, it will attempt to target an entity with the `summon_portal_target` tag.

## Example

```xml
<Entity tags="summon_portal_target" />
```