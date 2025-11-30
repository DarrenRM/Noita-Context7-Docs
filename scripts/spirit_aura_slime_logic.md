---
title: Spirit Aura Slime Logic
category: scripts/
---

# Spirit Aura Slime Logic

This script defines the behavior of a "spirit aura slime" entity in Noita. Its primary function is to detect nearby entities with specific tags ("homing_target" or "player_unit") and apply a "spirit slime" effect to them.

## Core Functionality

The script iterates through entities within a radius of 220 units around the slime. If a valid target is found, it attempts to attach an `effect_spirit_slime.xml` entity to it.

### Target Detection

-   **Radius:** 220 units.
-   **Target Tags:**
    -   `homing_target`
    -   `player_unit`

### Effect Application

-   An entity with the ID `effect_spirit_slime.xml` is loaded and attached as a child to the target entity.
-   This effect is only applied if the target entity does not already have a "spirit_slime" component.
-   The script prevents applying the effect multiple times to the same root entity.

## Key Attributes and Logic

-   `entity_id`: The unique identifier of the spirit aura slime itself.
-   `x`, `y`: The current position of the slime.
-   `r`: The detection radius.
-   `targets`, `targets2`: Tables storing detected entities based on their tags.
-   `done`: A table used to track entities that have already received the spirit slime effect, preventing duplicates.
-   `EntityGetInRadiusWithTag`: Function used to find entities within a specified radius and with a given tag.
-   `EntityHasTag`: Checks if an entity possesses a specific tag.
-   `EntityGetAllChildren`: Retrieves all child entities of a given entity.
-   `EntityGetRootEntity`: Gets the root entity of a hierarchical entity structure.
-   `EntityGetComponent`: Retrieves a specific component from an entity.
-   `EntityLoad`: Loads an entity from an XML file at a given position.
-   `EntityAddChild`: Attaches one entity as a child to another.

## Example Usage (Conceptual)

This script would typically be attached to an entity defined in an XML file, like:

```xml
<entity name="spirit_aura_slime">
    <components>
        <custom_component class="EntityLogicComponent" script_id="spirit_aura_slime" />
        <!-- Other components like SpriteComponent, PhysicsComponent, etc. -->
    </components>
</entity>
```

The `effect_spirit_slime.xml` would define the visual and functional aspects of the applied spirit slime effect.