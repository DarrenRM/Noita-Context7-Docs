---
title: Energy Shield Sector Card
category: entities
---

# Energy Shield Sector Card

This entity defines a custom wand card that grants the player an "Energy Shield Sector" effect. It inherits its base functionality from `energy_shield.xml` and modifies specific visual and behavioral components.

## Key Components

### SpriteComponent
- **image_file**: `data/ui_gfx/gun_actions/energy_shield_sector.png`
  - This specifies the visual representation of the card in the game's UI.

### ItemActionComponent
- **_tags**: `enabled_in_world`
  - Indicates that this action is available when the player is in the game world.
- **action_id**: `ENERGY_SHIELD_SECTOR`
  - A unique identifier for this specific wand action.

### InheritTransformComponent
- **use_root_parent**: `1`
  - The entity's transform will inherit from its root parent.
- **always_use_immediate_parent_rotation**: `1`
  - The entity will always use the rotation of its immediate parent.

### EnergyShieldComponent
- **sector_degrees**: `170`
  - This is the core attribute defining the shield's shape. It creates a shield that covers 170 degrees of a circle.

### ParticleEmitterComponent (x3)
- **area_circle_sector_degrees**: `170`
  - Each of these components is responsible for emitting particles in a sector shape corresponding to the shield's coverage (170 degrees). This likely contributes to the visual effect of the shield.