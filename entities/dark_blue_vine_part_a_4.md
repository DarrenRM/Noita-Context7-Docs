---
title: Dark Blue Vine Part A (4)
category: guides
---

<Entity name="vine_dark_a_4">
  <Sprite
   filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_a.png"
   offset_x="0"
   offset_y="0"
   default_animation="stand" >
   <!-- animation -->
   <RectAnimation
    name="stand"
    pos_x="12"
    pos_y="0"
    frame_count="1"
    frame_width="4"
    frame_height="3"
    frame_wait="1"
    frames_per_row="8"
    loop="1" >
   </RectAnimation>
  </Sprite>
  <Physics
   gravity_x="0"
   gravity_y="0"
   velocity_x="0"
   velocity_y="0"
   friction="0"
   air_friction="0"
   mass="1"
   angular_damping="0"
   linear_damping="0"
   is_kinematic="1" >
  </Physics>
  <Velocity
   x="0"
   y="0" >
  </Velocity>
  <DamageHit
   damage_type="none" >
  </DamageHit>
  <Material
   material_type="vine" >
  </Material>
  <AreaDamage
   damage_type="none" >
  </AreaDamage>
  <Lifetime
   lifetime="0" >
  </Lifetime>
  <LuaComponent
   script_path="data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_a_4.lua" >
  </LuaComponent>
</Entity>
```

---
title: Dark Blue Vine Part A (4)
category: entities
---

# Dark Blue Vine Part A (4)

This entity represents a segment of a dark blue vine, specifically the fourth variation in the `vine_dark_a` sprite. It's designed to be part of a verlet chain, allowing for flexible and dynamic vine growth.

## Key Attributes

### Sprite
The visual representation of the vine segment.

| Attribute      | Value                                                              | Description