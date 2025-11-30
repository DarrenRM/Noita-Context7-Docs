---
title: Tentacle Boss Fish Segment
category: entities
---

---

# Tentacle Boss Fish Segment

This entity represents a segment of the Tentacle Boss Fish's body in Noita. It is a dynamic entity whose transform (position and rotation) is updated each frame.

## Key Attributes

### Transform Update

The primary function of this entity is to update its transform based on the game's frame number.

*   **`EntitySetTransform( entity_id, x, y, a )`**: This function is used to set the entity's position (`x`, `y`) and rotation (`a`).
*   **`GameGetFrameNum()`**: Retrieves the current frame number of the game.
*   **`angle = GameGetFrameNum() * 0.01`**: Calculates an angle based on the frame number, creating a smooth oscillation.
*   **`a = math.cos( angle ) * arc`**: Applies a cosine function to the calculated angle, scaled by `arc`, to determine the rotation. This results in a swaying motion.
*   **`arc = -0.2`**: Defines the maximum angular displacement for the swaying motion.

This setup creates a visual effect where the tentacle segment oscillates back and forth, contributing to the boss's animation.