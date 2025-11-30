---
title: Physics Electricity Source
category: entities
---

# Physics Electricity Source

This entity defines a physics-based object that emits electricity. It's a foundational component for creating electrical hazards or interactive elements in the game world.

## Key Components

### PhysicsBodyComponent
This component governs the physical properties of the entity.

*   `allow_sleep`: If `1`, the body can enter a sleep state when inactive to save performance.
*   `fixed_rotation`: If `0`, the body can rotate freely.
*   `auto_clean`: If `1`, the body will be automatically removed when it's no longer needed (e.g., off-screen).
*   `on_death_leave_physics_body`: If `1`, the physics body remains even after the entity is destroyed.

### PhysicsImageShapeComponent
This component defines the visual representation and collision shape of the entity.

*   `image_file`: Specifies the graphical asset used for the entity.
*   `material`: Defines the physical material properties for collision and interaction.

### CameraBoundComponent
This component controls the entity's behavior relative to the camera.

*   `max_count`: Limits the number of these entities that can exist within the camera's view.
*   `distance`: The maximum distance from the camera at which the entity will be active.

### ElectricitySourceComponent
This is the core component that enables the entity to emit electricity.

*   `radius`: The area of effect for the emitted electricity.
*   `emission_interval_frames`: The frequency (in game frames) at which electricity is emitted.