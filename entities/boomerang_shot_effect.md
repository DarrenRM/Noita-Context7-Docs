---
title: Boomerang Shot Effect
category: guides
---

<Entity>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <ShotEffectComponent
        extra_modifier="projectile_homing_shooter"
		>
	</ShotEffectComponent>
	
	<LifetimeComponent
		lifetime="3600"
		>
	</LifetimeComponent>

</Entity>
```

---
title: Boomerang Shot Effect
category: entities
---

# Boomerang Shot Effect

This entity defines a projectile that gains homing properties.

## Key Components

### `ShotEffectComponent`

This component is responsible for applying special effects to projectiles.

*   **`extra_modifier`**: `projectile_homing_shooter` - This is the core modifier that grants the projectile homing capabilities.

### `LifetimeComponent`

Determines how long the projectile exists.

*   **`lifetime`**: `3600` - The projectile will persist for 3600 game frames.