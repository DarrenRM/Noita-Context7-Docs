---
title: Telekinesis Perk Entity
category: entities
---

# Telekinesis Perk Entity

This entity defines the behavior and associated sounds for the Telekinesis perk in Noita.

## Core Components

### TelekinesisComponent

This component is the primary driver for the Telekinesis perk's functionality. While its XML definition is empty, it signifies the presence and activation of the perk's abilities.

### AudioLoopComponent (Object Move Sound)

This component handles the audio feedback when an object is being moved by Telekinesis.

*   **`_tags`**: `sound_telekinesis_move` - Identifies this audio component for the Telekinesis move sound.
*   **`file`**: `data/audio/Desktop/misc.bank` - Specifies the audio bank containing the sound effect.
*   **`event_name`**: `misc/telekinesis/object_move` - The specific event name within the audio bank for the object movement sound.
*   **`volume_autofade_speed`**: `0.05` - Controls how quickly the sound volume fades in or out.

### AudioLoopComponent (Hold Sound)

This component manages the audio feedback when an object is being held by Telekinesis.

*   **`_tags`**: `sound_telekinesis_hold` - Identifies this audio component for the Telekinesis hold sound.
*   **`file`**: `data/audio/Desktop/misc.bank` - Specifies the audio bank containing the sound effect.
*   **`event_name`**: `misc/telekinesis/hold` - The specific event name within the audio bank for the object holding sound.
*   **`volume_autofade_speed`**: `0.05` - Controls how quickly the sound volume fades in or out.