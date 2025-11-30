---
title: ConfigCutThroughWorld
source: https://noita.wiki.gg/wiki/Documentation:ConfigCutThroughWorld
category: modding-wiki
---

# ConfigCutThroughWorld

This documentation explains how to configure the `ConfigCutThroughWorld` component in Noita, which allows entities to pass through terrain. Understanding and utilizing this component is crucial for creating mods that introduce new projectile behaviors, enemy types, or environmental interactions that deviate from standard gameplay.

## Understanding ConfigCutThroughWorld

The `ConfigCutThroughWorld` component is a fundamental part of Noita's entity system that dictates whether an entity can pass through solid world geometry. By default, most entities are blocked by terrain. Modifying this component allows for entities to ignore these collisions, opening up a wide range of possibilities for custom gameplay mechanics.

### Component Properties

The `ConfigCutThroughWorld` component has a single boolean property:

*   **`cut_through_world`**:
    *   **Type**: `boolean`
    *   **Description**: If `true`, the entity will be able to pass through terrain. If `false` (or if the component is absent), the entity will be blocked by terrain.

### Usage in XML

This component is typically added to an entity's definition within the `data/entities/` directory.

**Example:**

To make a projectile pass through terrain, you would add the `ConfigCutThroughWorld` component to its entity definition:

```xml
<entity name="my_cutting_projectile">
  <hitbox_rect rect="0 0 4 4"/>
  <velocity velocity="100 0"/>
  <sprite sprite="data/projectiles/projectiles.xml" rect="0 0 4 4"/>
  <config_cut_through_world/> <!-- This line enables cutting through the world -->
  <lifetime_impact lifetime="1"/>
  <damage damage="5"/>
  <projectile/>
</entity>
```

In this example, the `my_cutting_projectile` entity will now ignore collisions with the world geometry.

### Modding Implications

*   **New Projectile Types**: Create projectiles that can bypass obstacles, allowing for unique combat strategies or puzzle mechanics.
*   **Enemy Behaviors**: Design enemies that can phase through walls or terrain, making them more challenging or unpredictable.
*   **Environmental Interactions**: Implement special effects or entities that can alter the terrain they pass through, or simply move through it unimpeded.

### Related Components and Concepts

*   **`hitbox_rect`**: Defines the collision area of an entity. Even with `ConfigCutThroughWorld`, a hitbox is still necessary for other interactions like damage or triggering effects.
*   **`projectile`**: Marks an entity as a projectile, enabling its movement and interaction with the game world.
*   **`lifetime_impact`**: Controls how long an entity exists before despawning.

By understanding and applying the `ConfigCutThroughWorld` component, modders can significantly expand the interactive possibilities within Noita.