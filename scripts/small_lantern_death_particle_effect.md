---
title: Small Lantern Death Particle Effect
category: scripts
---

# Small Lantern Death Particle Effect

This script defines the behavior for the particle effect that plays when a small lantern is destroyed.

## Function: `death`

This function is called when the entity associated with this script is destroyed.

### Parameters

*   `damage_type_bit_field`: A bitfield representing the type of damage that caused the entity's destruction.
*   `damage_message`: A string describing the damage message.
*   `entity_thats_responsible`: The entity ID of the object that caused the destruction.
*   `drop_items`: A boolean indicating whether items should be dropped upon destruction.

### Behavior

1.  Retrieves the current entity ID.
2.  Gets the position (`pos_x`, `pos_y`) of the entity.
3.  Loads and spawns the `lantern_small_death.xml` particle effect at the entity's position.

### Key Elements

*   **`EntityLoad("data/entities/particles/lantern_small_death.xml", pos_x, pos_y)`**: This is the core of the script, responsible for spawning the visual particle effect that signifies the lantern's demise.