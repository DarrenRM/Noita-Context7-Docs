---
title: Orb 11 - The Orb of the Void
category: entities
---

# Orb 11 - The Orb of the Void

This document details the configuration for Orb 11, also known as the Orb of the Void, within Noita. It primarily defines its visual representation and its base properties inherited from `orb_base.xml`.

## Key Attributes

This orb is characterized by its unique visual appearance and its designation as a non-teleportable item.

### Entity Configuration

*   **`tags`**: `hittable,teleportable_NOT`
    *   `hittable`: Indicates the orb can be affected by damage.
    *   `teleportable_NOT`: Crucially, this tag prevents the orb from being teleported.

### Base Configuration

*   **`Base file="data/entities/items/orbs/orb_base.xml"`**: Inherits core functionality and properties from the generic orb definition.

### Orb Component

*   **`OrbComponent orb_id="11"`**: Assigns this specific orb instance the ID "11", linking it to its unique game logic and effects.

### Sprite Component

*   **`SpriteComponent image_file="data/items_gfx/orb_11.xml"`**: Defines the visual asset used for this orb. The sprite is loaded from `data/items_gfx/orb_11.xml`.

### Particle Effects

*   **`Entity`**: Contains a nested entity for particle effects.
    *   **`InheritTransformComponent`**:
        *   **`Transform position.x="0" position.y="-11"`**: Offsets the particle effect slightly above the orb's center.
    *   **`Base file="data/entities/items/orbs/orb_particles_base.xml"`**: Inherits standard particle effects associated with orbs.

---
```xml
<Entity tags="hittable,teleportable_NOT">
	
	<Base file="data/entities/items/orbs/orb_base.xml">

		<OrbComponent
			orb_id="11" >
		</OrbComponent>
		
		<SpriteComponent 
			image_file="data/items_gfx/orb_11.xml" 
			>
		</SpriteComponent>

	</Base>
	
	<Entity>
		<InheritTransformComponent>
			<Transform 
				position.x="0"   
				position.y="-11" 
				>
			</Transform>
		</InheritTransformComponent>
		
		<Base file="data/entities/items/orbs/orb_particles_base.xml" />
	</Entity>

</Entity>
```