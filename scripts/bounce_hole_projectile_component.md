---
title: Bounce Hole Projectile Component
category: scripts
---

# Bounce Hole Projectile Component

This script modifies the `ProjectileComponent` of a target entity to specify a custom bounce effect.

## Key Attributes

### `bounce_fx_file`
- **Description:** Specifies the entity file to be spawned when the projectile bounces.
- **Type:** String
- **Example:** `"data/entities/projectiles/deck/bounce_hole.xml"`

## Script Logic

The script first retrieves the `entity_id` and its transform. It then determines the `target_id`, which is either the parent entity or the entity itself. If the `target_id` has a `ProjectileComponent`, the script edits this component to set the `bounce_fx_file` attribute.