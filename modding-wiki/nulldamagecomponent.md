---
title: NullDamageComponent
source: https://noita.wiki.gg/wiki/Documentation:NullDamageComponent
category: modding-wiki
---

# NullDamageComponent

This documentation page explains the `NullDamageComponent` in Noita, a crucial component for creating entities that deal no damage. Understanding and utilizing this component is essential for modders who wish to implement unique mechanics, such as environmental hazards that don't harm the player directly, or decorative elements that can be interacted with without consequence.

## Overview

The `NullDamageComponent` is a simple entity component that, when added to an entity, prevents it from dealing any damage. This is particularly useful for creating objects or effects that might otherwise be perceived as harmful but are intended to have no damaging impact on the player or other entities.

## Usage

To apply the `NullDamageComponent` to an entity, you simply need to add it to the entity's XML definition. There are no configurable parameters for this component; its presence alone is sufficient to nullify damage.

### Example

Here's an example of how to add the `NullDamageComponent` to an entity in its XML definition:

```xml
<Entity name="my_non_damaging_object">
  <NullDamageComponent />
  <!-- Other components for visual representation, physics, etc. -->
  <Sprite sprite="data/objects/my_object.png" />
  <PhysicsBody2D />
</Entity>
```

In this example, `my_non_damaging_object` will not deal any damage to anything it might collide with, thanks to the inclusion of the `<NullDamageComponent />`.