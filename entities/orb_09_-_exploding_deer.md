---
title: Orb 09 - Exploding Deer
category: entities
---

# Orb 09 - Exploding Deer

This document details the configuration for Orb 09, also known as the "Exploding Deer" orb, within Noita's entity system.

## Core Entity Configuration

The orb is defined as a Hittable and Non-Teleportable entity.

```xml
<Entity tags="hittable,teleportable_NOT">
```

## Base Item Configuration

It inherits its fundamental properties from `orb_base.xml`.

```xml
<Base file="data/entities/items/orbs/orb_base.xml">
```

### Orb Component

This component assigns the unique identifier for this orb.

```xml
<OrbComponent
    orb_id="9" >
</OrbComponent>
```

### Sprite Component

Defines the visual representation of the orb.

```xml
<SpriteComponent
    image_file="data/items_gfx/orbs/orb_09.xml"
    >
</SpriteComponent>
```

### Variable Storage Component

Stores the in-game name associated with this orb.

```xml
<VariableStorageComponent
    name="card_name"
    value_string="EXPLODING_DEER"
/>
```

## Particle Effects

The orb includes a child entity for particle effects, inheriting from a base configuration.

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