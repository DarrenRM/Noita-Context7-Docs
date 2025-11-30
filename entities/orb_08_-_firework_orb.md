---
title: Orb 08 - Firework Orb
category: entities
---

# Orb 08 - Firework Orb

This document details the configuration for the Firework Orb in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The orb is defined as a hittable and non-teleportable entity.

```xml
<Entity tags="hittable,teleportable_NOT">
```

### Base Entity Inheritance

The orb inherits its fundamental properties from `orb_base.xml`.

```xml
<Base file="data/entities/items/orbs/orb_base.xml">
```

### Orb Component

This component assigns the unique identifier for this orb.

```xml
<OrbComponent
    orb_id="8" >
</OrbComponent>
```

### Sprite Component

Defines the visual appearance of the orb.

```xml
<SpriteComponent
    image_file="data/items_gfx/orbs/orb_08.xml"
    >
</SpriteComponent>
```

### Variable Storage Component

Stores the in-game name of the orb.

```xml
<VariableStorageComponent
    name="card_name"
    value_string="FIREWORK"
/>
```

## Visual Effects and Positioning

This section defines the particle effects and their relative positioning.

### Inherited Transform Component

Positions the particle effects relative to the orb's base.

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