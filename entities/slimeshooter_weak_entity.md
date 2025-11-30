---
title: Slimeshooter (Weak) Entity
category: entities
---

# Slimeshooter (Weak) Entity

This document details the configuration for the "Slimeshooter (Weak)" entity in Noita, primarily focusing on its AI, damage, and visual components. This entity inherits its base functionality from `slimeshooter.xml`.

## Key Attributes

### Base Entity Inheritance

The Slimeshooter (Weak) entity inherits its core properties from a base entity.

```xml
<Base file="data/entities/animals/slimeshooter.xml">
```

### AnimalAIComponent

This component governs the AI behavior of the creature.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `attack_ranged_entity_file` | Specifies the projectile entity file used for ranged attacks.            |

```xml
<AnimalAIComponent
    attack_ranged_entity_file="data/entities/projectiles/radioactive_blob.xml"
    >
</AnimalAIComponent>
```

### DamageModelComponent

This component defines the health and damage-related properties of the entity.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `ragdoll_filenames_file` | Points to the file containing the filenames for the entity's ragdoll.    |
| `hp`                   | The hit points of the entity. A low value indicates a weaker variant.    |

```xml
<DamageModelComponent
    ragdoll_filenames_file="data/ragdolls/slimeshooter_weak/filenames.txt"
    hp="0.3"
    >
</DamageModelComponent>
```

### SpriteComponent

This component handles the visual representation of the entity.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `image_file`           | Specifies the XML file defining the entity's sprite and animations.      |

```xml
<SpriteComponent
    image_file="data/enemies_gfx/slimeshooter_weak.xml"
    >
</SpriteComponent>
```

## Visual Appendages (Tentacles)

The Slimeshooter (Weak) entity also includes several appended entities, likely representing its tentacles, which are defined using `verlet_chains`.

### Tentacle 1

```xml
<Entity>
    <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_alt_01.xml">
        <InheritTransformComponent>
            <Transform position.x="-3" position.y="-6"></Transform>
        </InheritTransformComponent>
    </Base>
</Entity>
```

### Tentacle 2

```xml
<Entity>
    <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_alt_01.xml">
        <InheritTransformComponent>
            <Transform position.x="3" position.y="-6"></Transform>
        </InheritTransformComponent>
    </Base>
</Entity>
```