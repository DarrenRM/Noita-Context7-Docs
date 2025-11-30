---
title: Physics Fungus Acid Huge
category: entities
---

# Physics Fungus Acid Huge

This entity represents a large, physics-enabled fungus that leaks acid when damaged. It's designed to be a destructible environmental hazard.

## Key Components and Attributes

### PhysicsBody2Component
This component defines the physical properties of the fungus.

*   **is\_static**: `0` - The fungus is not fixed in place and can move.
*   **allow\_sleep**: `1` - The physics body can go to sleep to save performance when not in motion.
*   **linear\_damping**: `0.5` - Reduces linear velocity over time.
*   **init\_offset\_y**: `73` - Initial vertical offset for the physics body.

### PhysicsImageShapeComponent
These components define the visual and physical shapes of the fungus, composed of a cap and multiple stalk segments.

*   **image\_file**: Specifies the sprite for each part (cap, stalk, foot).
*   **material**: `fungus_loose_green` - The material used for collision and visual representation.
*   **offset\_x**, **offset\_y**: Position of each shape relative to the body.

### PhysicsJoint2Component
These components connect the various `PhysicsImageShapeComponent` parts together, forming the fungus's structure.

*   **type**: `REVOLUTE_JOINT` - Creates a joint that allows rotation.
*   **body1\_id**, **body2\_id**: Identifies the two physics bodies being connected.
*   **break\_force**: `10` - The force required to break the joint.
*   **break\_distance**: `5` - The distance at which the joint breaks.
*   **REVOLUTE\_JOINT\_ATTACH\_TO\_NEARBY\_SURFACE**: A special joint type that anchors the lowest part of the fungus to the ground.

### MaterialInventoryComponent
Manages the materials contained within the fungus.

*   **on\_death\_spill**: `1` - The contents will spill out upon death.
*   **leak\_on\_damage\_percent**: `1` - The fungus will leak its contents when damaged.
*   **leak\_pressure\_min**, **leak\_pressure\_max**: Controls the pressure of the leaked material.
*   **kill\_when\_empty**: `1` - The fungus entity is destroyed when its material is depleted.
*   **count\_per\_material\_type**:
    *   **Material material**: `acid` - The type of material contained.
    *   **count**: `1200` - The amount of acid.

### DamageModelComponent
Defines how the fungus takes damage and its properties.

*   **hp**: `0.8` - The health points of the fungus.
*   **blood\_material**: `slime_green` - The material that spills when damaged (not blood in this case).
*   **blood\_sprite\_directional**, **blood\_sprite\_large**: Sprites used for visual feedback on damage.
*   **damage\_multipliers**:
    *   **fire**: `40.0` - Takes significantly more damage from fire.

### ExplodeOnDamageComponent
Determines if and how the fungus explodes when damaged.

*   **explode\_on\_death\_percent**: `1` - Will explode when its health reaches a certain percentage (implied by `physics_body_destruction_required`).
*   **physics\_body\_destruction\_required**: `0.25` - The explosion is triggered when 25% of the physics body is destroyed.
*   **config\_explosion**: Contains detailed settings for the explosion.
    *   **camera\_shake**: `40` - Intensity of camera shake.
    *   **explosion\_radius**: `60` - The area of effect for the explosion.
    *   **damage**: `2` - Damage dealt by the explosion.
    *   **particle\_effect**: `1` - Enables particle effects for the explosion.
    *   **physics\_explosion\_power**: `0.8` to `1.8` - The force of the physics-based explosion.
    *   **spark\_material**: `acid` - Sparks created by the explosion are acid.
    *   **audio\_event\_name**: `explosions/slime` - The sound effect played on explosion.

### LightComponent
Adds a light source to the entity.

*   **radius**: `120` - The range of the light.
*   **r**, **g**, **b**: `32`, `255`, `250` - Defines the greenish-cyan color of the light.

### LuaComponent
Attaches a Lua script for custom behavior.

*   **script\_source\_file**: `data/scripts/props/physics_fungus.lua` - The script controlling the fungus's logic.
*   **execute\_every\_n\_frame**: `1` - The script runs every frame.

### AudioLoopComponent
Plays a looping sound effect.

*   **event\_name**: `materials/spray_fungus` - The specific sound event to play.