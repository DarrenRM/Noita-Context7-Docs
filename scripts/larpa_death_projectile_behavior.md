---
title: Larpa Death Projectile Behavior
category: scripts
---

# Larpa Death Projectile Behavior

This script defines the behavior of a projectile when it "dies" or is destroyed, specifically for the "Larpa Death" projectile. It's designed to spawn multiple copies of another projectile in a radial pattern.

## Key Functionality

The primary purpose of this script is to trigger the spawning of a predefined projectile when the entity it's attached to is destroyed.

### Projectile Spawning Logic

*   **Conditional Spawning:** The script checks for a specific variable named `"projectile_file"` within a `VariableStorageComponent`. If this variable is found and contains a valid projectile file path, the spawning logic is initiated.
*   **Radial Distribution:** When spawning, the script calculates an angle and velocity for each new projectile. It then distributes `how_many` (defaulting to 8) projectiles in a circular pattern around the death point.
*   **Cloning Tag:** Each spawned projectile is given the tag `"projectile_cloned"` for potential further processing or identification.

## Key Attributes and Variables

*   **`projectile_file` (VariableStorageComponent):** This is the most crucial element. It's a string variable that must be set on the entity containing this script. It specifies the file path (e.g., `"data/projectiles/my_new_projectile.xml"`) of the projectile to be spawned.
*   **`length` (Local Variable):** Determines the initial velocity magnitude of the spawned projectiles. A higher value means they will travel faster and further. (Default: 1500)
*   **`how_many` (Local Variable):** Controls the number of projectiles spawned. (Default: 8)
*   **`angle_inc` (Local Variable):** Calculated based on `how_many`, this determines the angular separation between each spawned projectile.

## Example Usage (Conceptual)

To use this script, you would typically create an entity (e.g., a projectile) and attach this script to it. You would also need to add a `VariableStorageComponent` to that entity and set the `"projectile_file"` variable to the path of the projectile you want to be spawned upon its destruction.

For instance, in an entity's XML definition:

```xml
<Entity tags="projectile">
    <VariableStorageComponent
        name="projectile_file"
        value_string="data/projectiles/larpa_child.xml"
    />
    <ScriptComponent
        script_path="data/scripts/projectiles/larpa_death.lua"
    />
    <!-- Other components like ProjectileComponent, etc. -->
</Entity>
```

When the entity with this setup is destroyed, it will spawn 8 instances of `larpa_child.xml` projectiles, each with a velocity determined by the `length` variable and distributed radially.