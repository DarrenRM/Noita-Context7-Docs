---
title: Blood Spray Sound
category: entities
---

# Blood Spray Sound

This entity defines the sound played when blood sprays in Noita. It utilizes an `AudioLoopComponent` to manage the sound playback.

## Key Components

### AudioLoopComponent

This component is responsible for playing a looping sound effect.

*   **`_tags`**: `sound_spray` - This tag likely categorizes the sound for internal game logic or other systems.
*   **`file`**: `data/audio/Desktop/materials.bank` - Specifies the audio bank file containing the sound.
*   **`event_name`**: `materials/spray_animal` - The specific event name within the audio bank that triggers the sound.
*   **`volume_autofade_speed`**: `0.25` - Controls how quickly the sound's volume fades out automatically.