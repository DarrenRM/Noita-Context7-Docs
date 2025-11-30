---
title: Debug Animal AI Target Entity
category: entities
---

# Debug Animal AI Target Entity

This entity is a debug tool for Noita's AI system, specifically for testing animal AI targeting. It's designed to be a simple, controllable target that can be followed by AI.

## Key Components and Attributes

### Entity Tags

The entity possesses several tags that define its behavior and interactions:

*   `mortal`: Indicates the entity can be killed.
*   `human`: Suggests it's a humanoid type.
*   `hittable`: Can be targeted and damaged.
*   `peasant`: Implies a role within the game's world.
*   `prey`: Identifies it as a potential target for predators.
*   `player_unit`: Can be controlled or interacted with by the player.
*   `teleportable`: Can be affected by teleportation effects.

### GenomeDataComponent

This component provides information relevant to the AI's understanding of the entity's place in the ecosystem.

*   `food_chain_rank`: A numerical value representing its position in the food chain. A higher rank suggests it's higher up, or a more desirable target.

### DebugFollowMouseComponent

This is the core component for its debug functionality.

*   When present, this entity will actively follow the player's mouse cursor. This is invaluable for manually placing and observing AI behavior in real-time.

### SpriteComponent

Defines the visual representation of the entity.

*   `image_file`: Specifies the texture used for the sprite. In this case, it uses `data/ui_gfx/mouse_cursor.png`, making it visually similar to the mouse cursor itself.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.
*   `z_index`: Determines the rendering order. A `z_index` of `-1` places it behind most other game elements.

```xml
<Entity tags="mortal,human,hittable,peasant,prey,player_unit,teleportable" >
   
	<GenomeDataComponent
		food_chain_rank="100"
		>
	</GenomeDataComponent>

    <DebugFollowMouseComponent></DebugFollowMouseComponent>
  

	<SpriteComponent 
		image_file="data/ui_gfx/mouse_cursor.png" 
		offset_x="6"
		offset_y="6"
		z_index="-1"
		>
	</SpriteComponent>

</Entity>
```