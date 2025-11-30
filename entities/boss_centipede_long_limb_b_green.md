---
title: Boss Centipede Long Limb B (Green)
category: guides
---

<Entity 
	name="boss_centipede_limb_long_b_green" 
	tags="boss,boss_part,enemy,enemy_normal,no_boss_spawning"
	>
	
	<LuaComponent 
		script_path="data/entities/animals/boss_centipede/limbs/boss_centipede_limb.lua" 
		is_boss_part="1"
		>
	</LuaComponent>
	
	<Sprite 
		filename="data/entities/animals/boss_centipede/limbs/limb_long_B_green.png" 
		offset_x="0" 
		offset_y="8" 
		>
		
	  <RectAnimation 
		name="stand" 
		pos_x="0" 
		pos_y="0" 
		frame_count="4" 
		frame_width="80" 
		frame_height="16" 
		frame_wait="0.17" 
		frames_per_row="8" 
		loop="1"  >
	  </RectAnimation>
	  
	</Sprite>
	
	<Physics 
		num_pixels_x="80" 
		num_pixels_y="16" 
		is_solid="0" 
		is_ground_ף="0" 
		>
	</Physics>
	
	<DamageModelComponent 
		hp="100" 
		knockback_force_on_hit="0" 
		>
	</DamageModelComponent>
	
	<ExplodeOnDeath 
		explode_radius="0" 
		>
	</ExplodeOnDeath>
	
	<MaterialAreaConnector 
		material_tags="boss_part" 
		>
	</MaterialAreaConnector>
	
</Entity>
```

---
title: Boss Centipede Long Limb B (Green)
category: entities
---

# Boss Centipede Long Limb B (Green)

This entity represents a segment of the Boss Centipede, specifically a longer, green variant. It's designed to be a modular part of a larger boss entity.

## Key Components and Attributes

### Entity Definition
- **`name`**: `boss_centipede_limb_long_b_green` - Unique identifier for this entity.
- **`tags`**: `boss`, `boss_part`, `enemy`, `enemy_normal`, `no_boss_spawning` - Categorizes the entity for game logic, indicating it's a boss component, an enemy, and not to be spawned independently.

### Lua Component
- **`script_path`**: `data/entities/animals/boss_centipede/limbs/boss_centipede_limb.lua` - Links this limb to the core logic for boss centipede segments.
- **`is_boss_part`**: `1` - Explicitly marks this as a part of a boss.

### Sprite Component
- **`filename`**: `data/entities/animals/boss_centipede/limbs/limb_long_B_green.png` - The visual asset for this limb.
- **`offset_x`, `offset_y`**: `0`, `8` - Adjusts the sprite's position relative to its entity origin.

#### RectAnimation (stand)
- **`frame_count`**: `4` - The total number of animation frames.
- **`frame_width`**: `80` - The width of each animation frame.
- **`frame_height`**: `16` - The height of each animation frame.
- **`frame_wait`**: `0.17` - The duration (in seconds) each frame is displayed.
- **`frames_per_row`**: `8` - How many frames are arranged horizontally in the sprite sheet.
- **`loop`**: `1` - Indicates the animation should loop continuously.

### Physics Component
- **`num_pixels_x`**: `80` - The width of the entity's collision box in pixels.
- **`num_pixels_y`**: `16` - The height of the entity's collision box in pixels.
- **`is_solid`**: `0` - The entity is not solid to projectiles or other entities.
- **`is_ground_ף`**: `0` - The entity does not interact with the ground physics in a typical way.

### DamageModelComponent
- **`hp`**: `100` - The hit points of this limb segment.
- **`knockback_force_on_hit`**: `0` - This limb does not apply knockback when hit.

### ExplodeOnDeath Component
- **`explode_radius`**: `0` - This limb does not explode upon death.

### MaterialAreaConnector Component
- **`material_tags`**: `boss_part` - Connects this entity to materials tagged as `boss_part`.