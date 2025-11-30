---
title: Tiny Ghost Activation/Deactivation Sound and Particle Effect
category: scripts
---

---

# Tiny Ghost Activation/Deactivation Sound and Particle Effect

This script handles the visual and auditory feedback when a "tiny ghost" entity is enabled or disabled in Noita.

## Function: `enabled_changed`

This function is triggered when the `is_enabled` state of an entity changes.

### Parameters

*   `entity_id`: The unique identifier of the entity whose state has changed.
*   `is_enabled`: A boolean value indicating whether the entity has been enabled (`true`) or disabled (`false`).

### Behavior

1.  **If `is_enabled` is `true` (Entity Activated):**
    *   It retrieves the transform (position) of the parent entity.
    *   It plays the "activate" sound effect for the tiny ghost from the `animals.bank` audio file at the parent entity's location.

2.  **If `is_enabled` is `false` (Entity Deactivated):**
    *   It retrieves the transform (position) of the entity itself.
    *   It plays the "deactivate" sound effect for the tiny ghost from the `animals.bank` audio file at the entity's location.

3.  **In both cases (Activation and Deactivation):**
    *   It loads and spawns a particle effect named `tiny_ghost_poof.xml` at the determined `x, y` coordinates. This creates a visual "poof" effect.

## Key Elements

*   **Sound Triggering:** Uses `GamePlaySound` to play specific audio cues based on activation or deactivation.
*   **Particle Effect:** Uses `EntityLoad` to instantiate a visual particle effect for feedback.
*   **Entity Hierarchy Awareness:** Can access the parent entity's transform, suggesting the tiny ghost might be a child component.
*   **Coordinate Retrieval:** Dynamically gets the `x, y` coordinates for sound and particle placement.

## Dependencies

*   `data/scripts/lib/utilities.lua`: Assumed to contain helper functions, though not directly used in the provided snippet.
*   `data/audio/Desktop/animals.bank`: The audio bank containing the sound effects.
*   `data/entities/particles/tiny_ghost_poof.xml`: The entity file defining the particle effect.