---
title: Mimic Wake-Up Logic
category: scripts
---

---

# Mimic Wake-Up Logic

This script defines the behavior for waking up a Mimic entity in Noita. It triggers when the Mimic collides with something or receives damage.

## Core Functions

### `collision_trigger()`

*   **Purpose:** Called when the Mimic entity collides with another entity.
*   **Action:** Calls the `wake_up()` function for the colliding entity.

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

*   **Purpose:** Called when the Mimic entity takes damage.
*   **Parameters:**
    *   `damage`: The amount of damage taken.
    *   `desc`: Description of the damage source.
    *   `entity_who_caused`: The entity that caused the damage.
    *   `is_fatal`: Boolean indicating if the damage was fatal.
*   **Action:** Calls the `wake_up()` function for the damaged entity.

### `wake_up(entity_id)`

*   **Purpose:** Activates various components of the Mimic entity, making it active and responsive.
*   **Action:** Enables the following components for the given `entity_id`:
    *   `PhysicsAIComponent`: Enables physics-based AI.
    *   `LightComponent`: Enables the entity's light source.
    *   `AnimalAIComponent`: Enables animal-specific AI behaviors.
    *   `SpriteParticleEmitterComponent`: Enables particle effects.