---
title: Necromancy Effect
category: entities
---

# Necromancy Effect

This entity defines a custom game effect related to necromancy, specifically for creating ragdoll AI entities.

## GameEffectComponent

This component governs the behavior of the custom effect.

### Key Attributes:

*   **`effect`**: Set to `CUSTOM`, indicating a user-defined effect.
*   **`custom_effect_id`**: Identifies the specific custom effect as `PHYSICS_RAGDOLL_AI`. This likely triggers the creation of a ragdoll entity with AI capabilities.
*   **`frames`**: Specifies the duration of the effect in frames, set to `200`.
*   **`ragdoll_effect`**: Defines the type of ragdoll effect, set to `CUSTOM_RAGDOLL_ENTITY`.
*   **`ragdoll_effect_custom_entity_file`**: Points to the XML file that defines the custom ragdoll entity, located at `data/entities/misc/physics_ragdoll_ai.xml`.
*   **`ragdoll_fx_custom_entity_apply_only_to_largest_body`**: A boolean attribute set to `1`, meaning the ragdoll effect will only be applied to the largest body of the spawned entity.