---
title: Boss Limb Damage Handling
category: entities
---

---

# Boss Limb Damage Handling

This document outlines the Lua script responsible for handling damage received by boss limbs in Noita. It focuses on visual feedback and state transitions upon taking damage.

## Core Functions

### `set_main_animation( current_name, next_name )`

This function is responsible for updating the sprite's animation state. It checks if the current animation is in an "opened" or "open" state before proceeding to animate the sprite. This prevents animations from playing out of sequence or when not intended.

### `animate_sprite( sprite, current_name, next_name )`

A helper function to directly set the sprite's current and next animation states.

### `damage_received( damage, desc, entity_who, is_fatal )`

This is the primary callback function triggered when the boss limb entity receives damage.

## Key Attributes/Elements

*   **`damage_received` function:** This is the entry point for all damage events.
*   **`set_main_animation` call:** When damage is received, this function is called to visually indicate the hit.
*   **Animation States:**
    *   `"hurt"`: The animation played immediately upon taking damage.
    *   `"opened"`: The subsequent animation state after the "hurt" animation, likely representing a recovery or idle state.

This script ensures that boss limbs react visually to incoming damage, providing important feedback to the player.