---
title: Friend Ragdoll Sprites
category: ragdolls
---

---

# Friend Ragdoll Sprites

This documentation describes the sprite assets used for the "friend" ragdoll in Noita. These files define the visual appearance of the ragdoll when it is in a non-animated, physics-driven state.

## Sprite Files

The following PNG files represent individual body parts of the friend ragdoll.

| Sprite Name   | Description        | File Path                      |
|---------------|--------------------|--------------------------------|
| torso         | The main body part | `data/ragdolls/friend/torso.png` |
| left_foot     | The left foot      | `data/ragdolls/friend/left_foot.png` |
| left_leg      | The left leg       | `data/ragdolls/friend/left_leg.png` |
| right_foot    | The right foot     | `data/ragdolls/friend/right_foot.png` |
| right_leg     | The right leg      | `data/ragdolls/friend/right_leg.png` |

## Usage in Modding

These sprite files are typically referenced within the game's entity definitions or ragdoll configuration files. When an entity breaks apart or dies in a way that triggers a ragdoll, these images will be used to render the individual pieces.

Modders can:

*   **Replace existing sprites:** To change the visual appearance of the friend ragdoll.
*   **Create new ragdolls:** By defining new sprite sets and associating them with entities.

## Key Considerations

*   **Image Format:** All sprites are in PNG format, supporting transparency.
*   **Resolution:** The resolution of these sprites will impact the visual detail of the ragdoll.
*   **Alignment:** Proper alignment of these sprites is crucial for a cohesive ragdoll appearance. The game engine will likely handle the physics-based positioning, but the sprites themselves need to be designed to fit together correctly.