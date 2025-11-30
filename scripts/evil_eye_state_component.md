---
title: Evil Eye State Component
category: scripts/
---

# Evil Eye State Component

This script defines the behavior for an "Evil Eye" entity, specifically how its associated platforms and components react to the entity being enabled or disabled.

## Core Functionality

The primary function `enabled_changed` handles the state transitions of the Evil Eye.

### `enabled_changed( entity_id, is_enabled )`

This function is triggered when the enabled state of the Evil Eye entity changes.

*   **`entity_id`**: The unique identifier of the Evil Eye entity.
*   **`is_enabled`**: A boolean indicating whether the entity is now enabled (`true`) or disabled (`false`).

#### Behavior when Enabled (`is_enabled == true`)

1.  **Locate Platforms**: It searches for entities with the tag `"magic_eye_platform"` within a 200-unit radius of the Evil Eye.
2.  **Enable Components**: For each found platform:
    *   It enables components tagged with `"magic_eye"`.
    *   It loads and attaches a `platform_wide_collision.xml` entity as a child to the platform, effectively adding collision to it.

#### Behavior when Disabled (`is_enabled == false`)

1.  **Locate Platforms**: It again searches for entities with the tag `"magic_eye_platform"` within a 200-unit radius.
2.  **Disable Components**: For each found platform:
    *   It disables components tagged with `"magic_eye"`.
    *   It iterates through all children of the platform and destroys them (this would include the `platform_wide_collision.xml` entities).

## Key Elements

*   **`magic_eye_platform` tag**: Identifies the platforms that are controlled by the Evil Eye.
*   **`magic_eye` component tag**: Refers to specific components on the platforms that are toggled.
*   **`platform_wide_collision.xml`**: An external entity file responsible for providing collision to the platforms when the Evil Eye is active.
*   **Radius Search**: The script uses a radius-based search (`EntityGetInRadiusWithTag`) to find relevant platforms, implying a proximity-based interaction.
*   **Entity Manipulation**: The script heavily relies on Noita's entity system functions like `EntityLoad`, `EntityAddChild`, `EntityKill`, and `EntitySetComponentsWithTagEnabled`.