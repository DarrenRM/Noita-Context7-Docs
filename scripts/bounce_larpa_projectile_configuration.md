---
title: Bounce Larpa Projectile Configuration
category: scripts
---

---

# Bounce Larpa Projectile Configuration

This script configures the bounce effect for a projectile, specifically the "Larpa" type. It attaches a visual effect to the projectile when it bounces.

## Key Components and Attributes

### Projectile Configuration

The script primarily targets the `ProjectileComponent` of the entity.

*   **`bounce_fx_file`**: This attribute within the `ProjectileComponent` is crucial. It specifies the entity file to be spawned as a visual effect when the projectile bounces.

    *   **Value**: `"data/entities/misc/bounce_larpa_launcher.xml"`

## Logic Overview

1.  **Entity Identification**: The script first retrieves the `entity_id` of the current entity and its `parent_id`.
2.  **Target Identification**: It determines the `target_id` to apply the component modification. If the entity has a parent, the parent is used; otherwise, the entity itself is the target.
3.  **Component Retrieval**: It attempts to retrieve the `ProjectileComponent` from the `target_id`.
4.  **Component Modification**: If the `ProjectileComponent` exists, it modifies the `bounce_fx_file` attribute to point to the specified bounce effect entity.

## Example Usage (Conceptual)

This script would be attached to a projectile entity that is designed to bounce. When this projectile collides with a surface and triggers its bounce behavior, the `bounce_larpa_launcher.xml` entity will be instantiated at the point of impact, creating a visual cue for the bounce.