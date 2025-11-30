---
title: Evil Eye Proximity Check
category: scripts
---

# Evil Eye Proximity Check

This script checks for the presence of "evil_eye" entities within a specified radius and enables/disables components based on the findings.

## Core Functionality

The script's primary purpose is to dynamically alter the behavior of an entity based on whether nearby "evil_eye" entities are present and possess a specific component.

### Key Attributes and Elements

*   **`radius`**: Defines the search radius for "evil_eye" entities. In this script, it's set to `200`.
*   **`"evil_eye"` tag**: Entities with this tag are targeted by the proximity check.
*   **`"magic_eye_check"` component**: This specific `LightComponent` is looked for on "evil_eye" entities. Its presence signifies a "magic eye."
*   **`"magic_eye"` tag**: Components with this tag on the entity running the script are enabled or disabled.
*   **`ParticleEmitterComponent`**: The script checks for the existence of this component to determine if particle effects should be triggered (though the `EntityLoad` calls are commented out).

## Logic Flow

1.  **Get Entity Information**: Retrieves the ID and transform (position) of the entity running the script.
2.  **Proximity Scan**: Searches for entities tagged `"evil_eye"` within the defined `radius`.
3.  **Magic Eye Detection**: Iterates through found `"evil_eye"` entities. For each, it attempts to find a `LightComponent` with the tag `"magic_eye_check"`. If found, `found` is set to `true`, and the loop breaks.
4.  **Component Toggling**:
    *   If `found` is `true` (magic eyes are present):
        *   If the entity *does not* have a `ParticleEmitterComponent`, it enables components tagged `"magic_eye"`.
    *   If `found` is `false` (no magic eyes present):
        *   If the entity *does* have a `ParticleEmitterComponent`, it disables components tagged `"magic_eye"`.

## Example Usage (Conceptual)

This script is likely intended to be attached to an entity that should react to the presence of "magic eyes." For instance, an entity might:

*   Activate a visual effect when magic eyes are near.
*   Deactivate a defensive mechanism when magic eyes are absent.
*   Trigger a sound or particle effect (if the `EntityLoad` calls were active).