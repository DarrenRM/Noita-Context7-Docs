---
title: Necrobot Super Ragdoll Sprites
category: ragdolls
---

# Necrobot Super Ragdoll Sprites

This documentation outlines the sprite assets used for the "Necrobot Super" ragdoll in Noita. These files define the visual components of the ragdoll when it is destroyed or dismembered.

## Sprite Files

The following PNG files represent individual parts of the Necrobot Super ragdoll.

*   `torso.png`: The main body sprite.
*   `head.png`: The head sprite.
*   `hand_right.png`: The right hand sprite.
*   `hand_left.png`: The left hand sprite.
*   `foot_1.png`: The first foot sprite.
*   `foot_2.png`: The second foot sprite.

## Usage

These sprites are typically referenced within the game's entity or AI definitions to determine how a specific enemy or object should break apart upon death. The filenames directly correspond to the visual assets used for each ragdoll segment.

## AI Modding Considerations

When modding AI or entities that utilize this ragdoll, understanding these sprite names is crucial for:

*   **Customizing destruction effects:** Replacing or modifying these sprites can alter the visual appearance of the Necrobot Super's demise.
*   **Debugging:** Identifying which sprite corresponds to which body part can aid in troubleshooting ragdoll behavior.
*   **Creating new entities:** If you are creating a new enemy that shares similar ragdoll mechanics, you might reference these sprite names as a template.