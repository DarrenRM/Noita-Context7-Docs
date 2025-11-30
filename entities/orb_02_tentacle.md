---
title: Orb 02 (Tentacle)
category: entities
---

---

# Orb 02 (Tentacle)

This document describes the configuration for Orb 02, also known as the "Tentacle" orb, within the Noita game data.

## Entity Definition

The core entity definition for this orb.

```xml
<Entity tags="hittable,teleportable_NOT">
```

*   **`tags`**:
    *   `hittable`: Indicates the orb can be damaged or interacted with by projectiles.
    *   `teleportable_NOT`: The orb cannot be teleported using standard game mechanics.

## Base Configuration

This orb inherits its fundamental properties from a base orb configuration.

```xml
<Base file="data/entities/items/orbs/orb_base.xml">
```

### Orb Component

Defines specific properties related to the orb's functionality.

```xml
<OrbComponent
    orb_id="2" >
</OrbComponent>
```

*   **`orb_id`**: A unique identifier for this specific orb type, set to "2".

### Sprite Component

Determines the visual representation of the orb.

```xml
<SpriteComponent
    image_file="data/items_gfx/orbs/orb_02.xml"
    >
</SpriteComponent>
```

*   **`image_file`**: Specifies the graphical asset used for the orb's sprite.

### Variable Storage Component

Stores custom variables associated with the orb.

```xml
<VariableStorageComponent
    name="card_name"
    value_string="TENTACLE"
/>
```

*   **`name`**: The name of the variable, "card\_name".
*   **`value_string`**: The string value assigned to this variable, "TENTACLE". This likely corresponds to the in-game name or identifier for the orb.

## Particle Effects

This section defines additional visual effects attached to the orb.

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

*   **`InheritTransformComponent`**: Allows the particle effects to inherit the position of the parent orb.
    *   **`Transform`**: Specifies a relative offset for the particles.
        *   `position.x="0"`: No horizontal offset.
        *   `position.y="-11"`: A slight upward offset for the particles.
*   **`Base file="data/entities/items/orbs/orb_particles_base.xml"`**: Inherits the standard particle effects defined for orbs.