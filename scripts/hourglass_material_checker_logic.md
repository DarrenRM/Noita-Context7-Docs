---
title: Hourglass Material Checker Logic
category: scripts
---

# Hourglass Material Checker Logic

This script defines the behavior for an "hourglass" entity that checks for specific material conditions and triggers corresponding events.

## Core Functionality: `material_area_checker_success`

This function is called when the hourglass entity successfully detects the required material.

### Key Actions:

*   **Entity State Update:**
    *   Enables components tagged with `"enabled_by_liquid"`.
    *   Disables components tagged with `"disabled_by_liquid"`.
*   **Self-Preservation & Cleanup:**
    *   Kills any other entities with the tag `"hourglass_entity"` within a 150-unit radius, ensuring only one active hourglass.
*   **Conditional Jingle/Music Events:**
    *   Checks for specific tags on the hourglass entity to trigger unique music sequences.

### Music Event Triggers:

| Tag                 | Description                                     | Music Event                                    |
| :------------------ | :---------------------------------------------- | :--------------------------------------------- |
| `"hourglass_blood"` | Triggers when the hourglass is associated with blood. | `music/oneshot/heaven_02_no_drs` (with fade out) |
| `"hourglass_teleport"` | Triggers when the hourglass is associated with teleportation. | `music/oneshot/heaven_03` (with fade out)      |

### Special Flag:

*   If the `"hourglass_teleport"` tag is present, the persistent flag `"secret_hourglass"` is added to the game state.