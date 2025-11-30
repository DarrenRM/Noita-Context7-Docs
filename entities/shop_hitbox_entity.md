---
title: Shop Hitbox Entity
category: entities
---

---

# Shop Hitbox Entity

This entity defines the collision area for shop interactions.

## Entity Definition

The core of this entity is the `HitboxComponent`, which specifies the bounding box for the shop's interaction zone.

### Key Attributes

*   **`aabb_min_x`**: The minimum X-coordinate of the hitbox.
*   **`aabb_min_y`**: The minimum Y-coordinate of the hitbox.
*   **`aabb_max_x`**: The maximum X-coordinate of the hitbox.
*   **`aabb_max_y`**: The maximum Y-coordinate of the hitbox.

```xml
<Entity tags="shop">
	<HitboxComponent
		aabb_min_x="-495"
		aabb_min_y="-112"
		aabb_max_x="490"
		aabb_max_y="145">
	</HitboxComponent>
</Entity>