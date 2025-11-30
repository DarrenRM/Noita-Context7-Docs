---
title: Squid Animation Script
category: scripts/
---

# Squid Animation Script

This script controls the animation of a squid-like entity by manipulating physics joints. It aims to create a wiggling or undulating motion.

## Core Functionality

The script iterates through `PhysicsJointComponent`s attached to the entity and modifies their motor properties to achieve animation.

### Key Attributes Modified:

*   **`mMotorEnabled`**: Set to `"1"` to enable motor control for the joint.
*   **`mMotorSpeed`**: Calculated using a sine wave based on game time and an offset, creating oscillating movement. The `dir` variable inverts the direction of the sine wave for alternating joints.
*   **`mMaxMotorTorque`**: Set to a fixed value (`100.0`) to provide sufficient torque for movement.

### Animation Logic:

The script uses a `dir` variable to alternate the direction of the sine wave for consecutive joints, creating a wave-like effect. An `offset` variable is incremented every four joints to introduce a phase shift, further enhancing the undulating motion.

```lua
local entity_id = GetUpdatedEntityID()
local comp_ids  = EntityGetComponent( entity_id, "PhysicsJointComponent" )

local dir    = 1.0
local offset = 0.5
local i      = 0

if( comp_ids ~= nil ) then
	for index,joint in ipairs(comp_ids) do
		local time = GameGetFrameNum() / 60.0 -- Calculate time in seconds

		-- Enable and set motor speed for the joint
		ComponentSetValue( joint, "mMotorEnabled",  "1" )
		ComponentSetValue( joint, "mMotorSpeed",     math.sin(offset + time * 1.0) * 5.0 * dir )
		ComponentSetValue( joint, "mMaxMotorTorque", 100.0 )

		-- Update direction and counter for wave effect
		dir = dir * -1.0
		i = i + 1
		if i == 4 then
			offset = offset + 0.5 -- Introduce phase shift every 4 joints
			i = 0
		end
	end
end
```