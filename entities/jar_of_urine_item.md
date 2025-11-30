---
title: Jar of Urine Item
category: entities
---

---

# Jar of Urine Item

This document describes the `jar_of_urine.xml` entity, which represents a "Jar of Urine" pickup item in Noita.

## Entity Definition

The core of this item is based on a generic `jar.xml` entity, with specific modifications to define its unique properties.

```xml
<Entity tags="hittable,teleportable_NOT,item_physics" >
  <!-- physical presence -->
  <Base file="data/entities/items/pickup/jar.xml" >
    <!-- disable the pick up particle effect -->
    <SpriteParticleEmitterComponent
      _enabled="0"
  		>
  	</SpriteParticleEmitterComponent>
  </Base>

  <VariableStorageComponent
    name="potion_material"
    value_string="urine" >
  </VariableStorageComponent>
  
</Entity>
```

## Key Components and Attributes

### Base Entity (`<Base>`)

*   **`file="data/entities/items/pickup/jar.xml"`**: Inherits fundamental properties from a standard jar pickup item. This includes its visual representation, physics, and interaction behavior.

### Sprite Particle Emitter Component (`<SpriteParticleEmitterComponent>`)

*   **`_enabled="0"`**: This attribute explicitly disables the default particle effect that would normally accompany picking up an item. This suggests the "Jar of Urine" has a distinct or no visual feedback upon collection.

### Variable Storage Component (`<VariableStorageComponent>`)

*   **`name="potion_material"`**: This component is crucial for defining the item's type.
*   **`value_string="urine"`**: This assigns the string "urine" to the `potion_material` variable, identifying this jar as containing urine. This likely influences its behavior when used or interacted with in the game.

## Summary

The "Jar of Urine" is a simple item entity that leverages the existing `jar.xml` structure. Its primary distinction lies in the `VariableStorageComponent` which labels it as containing "urine," and the disabling of its default pickup particle effect.