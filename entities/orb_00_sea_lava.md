---
title: Orb 00 (Sea Lava)
category: entities
---

# Orb 00 (Sea Lava)

This document describes the configuration for Orb 00, also known as the "Sea Lava" orb, within the Noita game data.

## Core Entity Configuration

The orb is defined as a hittable and non-teleportable entity.

```xml
<Entity tags="hittable,teleportable_NOT">
```

## Base Item Configuration

It inherits its fundamental properties from `orb_base.xml`.

### Orb Component

This component assigns a unique identifier to the orb.

```xml
<OrbComponent
    orb_id="0" >
</OrbComponent>
```

### Sprite Component

Defines the visual appearance of the orb.

```xml
<SpriteComponent
    image_file="data/items_gfx/orbs/orb_00.xml"
    >
</SpriteComponent>
```

### Variable Storage Component

Stores a string value associated with the orb, likely for internal game logic or UI display.

```xml
<VariableStorageComponent
    name="card_name"
    value_string="SEA_LAVA"
/>
```

## Visual Effects and Positioning

This section defines the visual effects and relative positioning of the orb.

### Inherited Transform Component

This component allows for precise positioning of child entities relative to the parent.

```xml
<InheritTransformComponent>
    <Transform
        position.x="0"
        position.y="-11"
        >
    </Transform>
</InheritTransformComponent>
```

### Particle Base

The orb utilizes a base configuration for its particle effects.

```xml
<Base file="data/entities/items/orbs/orb_particles_base.xml" />
```