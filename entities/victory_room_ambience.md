---
title: Victory Room Ambience
category: entities
---

# Victory Room Ambience

This entity defines the ambient soundscape for the victory room in Noita.

## Entity Definition

The core of this entity is a simple XML structure that defines its behavior and properties.

### Key Attributes

*   **`tags`**: `victoryroom_ambience` - This tag likely identifies the entity as belonging to the victory room's ambient elements.

## Components

This entity utilizes a single component to manage its functionality.

### AudioLoopComponent

This component is responsible for playing a looping audio event.

*   **`file`**: `data/audio/Desktop/event_cues.bank` - Specifies the audio bank file containing the sound event.
*   **`event_name`**: `event_cues/midas/ambience_loop` - Identifies the specific looping audio event to be played.
*   **`auto_play`**: `1` - Ensures that the audio loop starts automatically when the entity is loaded.