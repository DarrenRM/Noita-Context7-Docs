---
title: Invisibility Effect (Short Duration)
category: entities
---

# Invisibility Effect (Short Duration)

This entity defines a short-duration invisibility effect in Noita. It's primarily used to grant the player temporary invisibility.

## Key Components

### GameEffectComponent

This component dictates the core functionality of the effect.

*   **`effect`**: `INVISIBILITY` - Specifies the type of game effect.
*   **`frames`**: `900` - The duration of the effect in game frames (approximately 15 seconds at 60 FPS).

### AudioComponent

This entity includes audio feedback for the invisibility effect.

*   **First `AudioComponent`**:
    *   `file`: `data/audio/Desktop/misc.bank`
    *   `event_root`: `game_effect/invisibility` - Triggers the sound associated with becoming invisible.
*   **Second `AudioComponent`**:
    *   `file`: `data/audio/Desktop/misc.bank`
    *   `event_root`: `game_effect/electrocution` - **Note:** This appears to be an unintentional inclusion or a placeholder, as it's not directly related to invisibility. It might be a remnant from a previous entity or a mistake.

## XML Structure

```xml
<Entity>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
        effect="INVISIBILITY"
        frames="900"
    >
	</GameEffectComponent >

	<AudioComponent
		file="data/audio/Desktop/misc.bank"
		event_root="game_effect/invisibility" >
	</AudioComponent>

	<AudioComponent
		file="data/audio/Desktop/misc.bank"
		event_root="game_effect/electrocution" >
	</AudioComponent>

</Entity>
```