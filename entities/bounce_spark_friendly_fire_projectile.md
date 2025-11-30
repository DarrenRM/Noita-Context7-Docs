---
title: Bounce Spark Friendly Fire Projectile
category: entities
---

# Bounce Spark Friendly Fire Projectile

This entity defines a variant of the "bounce_spark" projectile that can damage the player (friendly fire).

## Key Attributes

*   **`friendly_fire`**: Set to `1` to enable friendly fire.
*   **`collide_with_shooter_frames`**: Specifies the number of frames the projectile will ignore collisions with its shooter.

## Inheritance

This projectile inherits its base properties from `data/entities/projectiles/deck/bounce_spark.xml`.

```xml
<Entity name="$projectile_default" tags="projectile_player" >

	<Base file="data/entities/projectiles/deck/bounce_spark.xml">
		<ProjectileComponent
			friendly_fire="1"
			collide_with_shooter_frames="8"
			>
		</ProjectileComponent>
	</Base>

</Entity>
```