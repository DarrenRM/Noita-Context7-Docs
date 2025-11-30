---
title: Shotgunner Hell Sprite Data
category: data/enemies_gfx
---

# Shotgunner Hell Sprite Data

This document details the sprite and animation data for the "Shotgunner Hell" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Shotgunner Hell.

```xml
<Sprite
 filename="data/enemies_gfx/shotgunner_hell.png"
 hotspots_filename="data/enemies_gfx/shotgunner_hotspots.png"
 offset_x="8"
 offset_y="7.5"
 default_animation="stand" >
 
	<Hotspot 
		color="ff0000" 
		name="hand" >
	</Hotspot>
</Sprite>
```

### Key Attributes:

*   **filename**: Path to the primary sprite texture.
*   **hotspots_filename**: Path to the texture defining collision and interaction points.
*   **offset\_x, offset\_y**: Adjustments to the sprite's origin point.
*   **default\_animation**: The animation to play when the enemy spawns or is idle.
*   **Hotspot**: Defines specific points on the sprite, like "hand", used for gameplay mechanics.

## Animations

The following table summarizes the key animations defined for the Shotgunner Hell. Each animation is defined by a `RectAnimation` tag.

| Animation Name    | Description                               | Frame Count | Frame Width | Frame Height | Frame Wait | Loop | Events