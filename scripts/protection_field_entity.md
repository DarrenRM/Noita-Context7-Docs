---
title: Protection Field Entity
category: scripts
---

# Protection Field Entity

This script defines the behavior for a protection field entity in Noita, primarily focused on attracting and affecting projectiles.

## Core Functionality

The protection field entity scans for nearby entities tagged as "hittable" within a specified radius. If a hittable entity has a `DamageModelComponent`, the protection field spawns a visual effect entity (`effect_protection_all_ultrashort.xml`) as a child of that hittable entity. This suggests the protection field visually "protects" or interacts with projectiles aimed at nearby objects.

## Key Attributes and Elements

*   **`distance_full`**: Defines the radius (in pixels) within which the protection field scans for entities.
    *   Value: `100`
*   **`EntityGetInRadiusWithTag`**: This function is used to find all entities within the `distance_full` radius that possess the "hittable" tag.
*   **`hittable` tag**: Entities with this tag are considered targets for the protection field's influence.
*   **`DamageModelComponent`**: The script checks for the presence of this component on found entities. This component is typically associated with entities that can take damage or have physics properties.
*   **`EntityLoad`**: Spawns a new entity.
    *   Entity XML: `data/entities/misc/effect_protection_all_ultrashort.xml`
    *   Spawn Position: Aligned with the protection field's position (`x`, `y`).
*   **`EntityAddChild`**: Attaches the spawned effect entity as a child to the identified hittable entity. This visually links the effect to the protected object.

## Summary

The protection field acts as a localized defensive aura. It identifies nearby objects capable of being hit and applies a visual effect to them, implying a mechanism to deflect or interact with incoming projectiles. The specific visual effect is defined by `effect_protection_all_ultrashort.xml`.