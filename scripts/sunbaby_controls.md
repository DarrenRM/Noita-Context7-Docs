---
title: Sunbaby Controls
category: scripts
---

---

# Sunbaby Controls

This script defines the behavior of the "Sunbaby" entity, primarily focusing on its interaction with projectiles and "moon_energy" entities. It manipulates its own velocity based on these interactions.

## Key Behaviors

### Projectile Interaction

The Sunbaby reacts to nearby projectiles.

*   **Targeting:** It searches for entities with the tag "projectile" within a radius of 56 units.
*   **Lightning Projectile Exclusion:** It specifically ignores projectiles tagged with "projectile\_lightning".
*   **Force Application:** For valid projectiles, it applies a force to itself proportional to the projectile's velocity (0.33x).
*   **Projectile Destruction:** All targeted projectiles are destroyed.

### Moon Energy Interaction

The Sunbaby also reacts to "moon\_energy" entities.

*   **Targeting:** It searches for entities with the tag "moon\_energy" within a radius of 400 units.
*   **Light Component Check:** It only reacts if the "moon\_energy" entity has a "LightComponent".
*   **Force Application:** If the conditions are met, it applies a significant force (240 units) towards the "moon\_energy" entity.

### Self-Velocity Dampening

The Sunbaby's own velocity is gradually reduced over time.

*   **Dampening Factor:** Its velocity is multiplied by 0.95 each frame, causing it to slow down.

## Lua Script Snippets

```lua
-- Get the entity's ID and current position
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform(entity_id)

-- Find nearby projectiles (excluding lightning)
local targets = EntityGetInRadiusWithTag(x, y, 56, "projectile")
-- Find nearby moon energy
local targets2 = EntityGetInRadiusWithTag(x, y, 400, "moon_energy")

local vel_x, vel_y = 0, 0

-- Process projectiles
for i, v in ipairs(targets) do
    if (i == 1) and (EntityHasTag(v, "projectile_lightning") == false) then
        -- Get projectile velocity
        edit_component(v, "VelocityComponent", function(comp, vars)
            vel_x, vel_y = ComponentGetValueVector2(comp, "mVelocity")
        end)

        -- Apply force if projectile is moving
        if (vel_x ~= 0) or (vel_y ~= 0) then
            PhysicsApplyForce(entity_id, vel_x * 0.33, vel_y * 0.33)
        end
    end
    -- Destroy the projectile
    EntityKill(v)
end

-- Process moon energy
for i, v in ipairs(targets2) do
    local tx, ty = EntityGetTransform(v)
    local test = EntityGetFirstComponent(v, "LightComponent")

    if (test ~= nil) then
        -- Calculate direction and apply force
        local dir = 0 - math.atan2(ty - y, tx - x)
        vel_x = math.cos(dir) * 240
        vel_y = 0 - math.sin(dir) * 240
        PhysicsApplyForce(entity_id, vel_x, vel_y)
    end
end

-- Dampen self-velocity
edit_component(entity_id, "VelocityComponent", function(comp, vars)
    vel_x, vel_y = ComponentGetValueVector2(comp, "mVelocity")
    vel_x = vel_x * 0.95
    vel_y = vel_y * 0.95
    ComponentSetValueVector2(comp, "mVelocity", vel_x, vel_y)
end)
```