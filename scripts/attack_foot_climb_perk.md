---
title: Attack Foot Climb Perk
category: scripts
---

# Attack Foot Climb Perk

This script implements the "Attack Foot Climb" perk, allowing the player to climb walls and surfaces using their feet. It modifies the player's gravity and movement behavior based on input and limb states.

## Key Attributes and Functionality

### Gravity Manipulation

The core of this perk lies in dynamically adjusting the player's `pixel_gravity`.

*   **`lerp_speed`**: Controls how quickly the gravity transitions between states. A value of `0.60` is used.
*   **`default_gravity`**: The standard gravity value when not actively climbing or swimming. Set to `350`.
*   **`fly_gravity`**: A modified, often negative, gravity value used for upward movement or flying. Initially `default_gravity * -0.8`. This value is significantly amplified when swimming.

### Movement States

The perk differentiates between several movement states:

*   **Swimming**: When `mFramesNotSwimming` is `0`, the player is considered swimming. In this state, `fly_gravity` is amplified significantly (multiplied by 15), allowing for rapid ascent.
*   **Climbing**: Detected when the player has attached limbs with the "attack\_foot\_walker" tag and their `IKLimbWalkerComponent` is in a state greater than `0`. This triggers a transition towards the calculated `gravity` value.
*   **Flying**: Activated when the player holds the "up" button (`mButtonDownUp`). This sets the `gravity` to `fly_gravity`.
*   **Stabilizing**: When no specific movement input is detected, gravity is adjusted based on the player's current vertical velocity (`-vy*200`).
*   **Falling**: If none of the above conditions are met, the player defaults to `default_gravity`.

### Input Handling

The script reads player input from the `ControlsComponent`.

*   **`mButtonDownDown`**: If the "down" button is held, the player's gravity is smoothly adjusted towards `default_gravity`, allowing them to descend or ignore walls.
*   **`mButtonDownUp`**: If the "up" button is held, the player enters a flying state with `fly_gravity`.

### Limb Detection

The perk checks for attached limbs that facilitate climbing.

*   **`EntityGetInRadiusWithTag(x, y, 2, "attack_foot_walker")`**: This function searches for entities within a 2-pixel radius of the player that have the tag "attack\_foot\_walker". These are assumed to be the player's climbing limbs.
*   **`IKLimbWalkerComponent`**: Each detected limb is checked for this component.
*   **`ComponentGetValue2(limb, "mState") > 0`**: If the limb's state is greater than 0, it indicates the limb is actively engaged in climbing.

### Component Interaction

The script directly modifies the `CharacterPlatformingComponent` of the player entity.

*   **`pixel_gravity`**: This is the primary attribute being modified to control the player's vertical movement.
*   **`mFramesNotSwimming`**: This counter is used to track whether the player is currently swimming.

```lua
-- Example of gravity lerping
comp.pixel_gravity = lerp(comp.pixel_gravity, gravity, lerp_speed)
```