---
title: Orb 01 - Crumbling Earth
category: entities
---

# Orb 01 - Crumbling Earth

This document details the configuration for the "Crumbling Earth" orb, a special item in Noita.

## Core Entity Configuration

The orb is defined as a Hittable and Teleportable_NOT entity.

```xml
<Entity tags="hittable,teleportable_NOT">
```

## Base Item Configuration

The orb inherits its core functionality from `orb_base.xml`.

```xml
<Base file="data/entities/items/orbs/orb_base.xml">
```

### Orb Component

This component assigns a unique ID to the orb.

```xml
<OrbComponent
    orb_id="1" >
</OrbComponent>
```

### Sprite Component

Defines the visual appearance of the orb.

```xml
<SpriteComponent
    image_file="data/items_gfx/orbs/orb_01.xml"
    >
</SpriteComponent>
```

### Variable Storage Component

Stores the in-game name associated with this orb.

```xml
<VariableStorageComponent
    name="card_name"
    value_string="CRUMBLING_EARTH"
/>
```

## Particle Effects

The orb includes a base configuration for particle effects, inherited from `orb_particles_base.xml`.

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