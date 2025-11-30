---
title: Orb 03 (Nuke Orb)
category: entities
---

---

# Orb 03 (Nuke Orb)

This document describes the configuration for the "Nuke Orb" entity in Noita, primarily focusing on its visual representation and core identity.

## Core Entity Configuration

The orb is defined as a hittable and teleportable entity.

```xml
<Entity tags="hittable,teleportable_NOT">
```

## Base Entity Inheritance

The orb inherits its fundamental properties from `orb_base.xml`.

```xml
<Base file="data/entities/items/orbs/orb_base.xml">
```

### Orb Component

This component assigns a unique identifier to the orb.

```xml
<OrbComponent
    orb_id="3" >
</OrbComponent>
```

### Sprite Component

Defines the visual appearance of the orb.

```xml
<SpriteComponent
    image_file="data/items_gfx/orbs/orb_03.xml"
    >
</SpriteComponent>
```

### Variable Storage Component

Stores a string value associated with the orb, likely its internal name or identifier.

```xml
<VariableStorageComponent
    name="card_name"
    value_string="NUKE"
/>
```

## Visual Offset and Particle Effects

This nested entity handles the visual positioning and particle effects associated with the orb.

```xml
<Entity>
    <InheritTransformComponent>
        <Transform
            position.x="0"
            position.y="-11"
            >
        </Transform>
    </InheritTransformComponent>

    <Base file="data/entities/items/orbs/orb_particles_base.xml" />
</Entity>
```