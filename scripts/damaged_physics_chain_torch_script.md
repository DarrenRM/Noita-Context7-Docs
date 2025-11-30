---
title: Damaged Physics Chain Torch Script
category: scripts
---

---

# Damaged Physics Chain Torch Script

This script defines the behavior for a damaged physics chain torch in Noita. When the torch is destroyed, it triggers a specific death sequence.

## Core Functionality

### `physics_body_modified( is_destroyed )`

This function is called when the physics body of the entity is modified, typically when it's destroyed.

-   **`entity_id = GetUpdatedEntityID()`**: Retrieves the ID of the entity that triggered the event.
-   **`EntityKill( entity_id )`**: Immediately kills the entity. This is the primary action taken upon destruction.
-   **`edit_all_components( entity_id, "PhysicsBodyComponent", function(comp,vars) ... end)`**: This is a utility function (likely from `utilities.lua`) that iterates through all `PhysicsBodyComponent`s attached to the entity.
    -   **`vars.on_death_really_leave_body = 1`**: Within the `PhysicsBodyComponent`, this specific attribute is set to `1`. This likely controls how the physics body behaves upon death, potentially ensuring it fully dissipates or leaves no lingering physics presence.

## Notes on Removed Code

The commented-out section in the original script indicates a previous or alternative approach to handling entity destruction. This section would have:

-   Explicitly removed specific components like `ParticleEmitterComponent`, `SpriteComponent`, `LightComponent`, and `PhysicsBodyComponent`.
-   Cleared the `script_physics_body_modified` variable from any `LuaComponent`s.

The current implementation relies on `EntityKill` and the modification of `on_death_really_leave_body` within the `PhysicsBodyComponent` for its destruction logic.