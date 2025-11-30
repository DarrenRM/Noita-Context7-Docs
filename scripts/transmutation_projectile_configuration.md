---
title: Transmutation Projectile Configuration
category: scripts
---

---

# Transmutation Projectile Configuration

This script defines the behavior of a projectile that can transmute materials in Noita. It randomly selects a target material, with a small chance of choosing a rarer, more potent liquid.

## Key Attributes

### Material Conversion

*   **`material_options`**: A table containing common materials that the projectile can transmute into.
    *   Examples: `"water"`, `"oil"`, `"lava"`, `"acid"`, `"sand"`, `"blood"`, `"honey"`.
*   **`material_options_rare`**: A table containing rarer, more potent liquid materials for transmutation.
    *   Examples: `"acid"`, `"magic_liquid_teleportation"`, `"magic_liquid_polymorph"`, `"magic_liquid_invisibility"`.
*   **Random Selection**: The script uses `Random()` to pick a material from either `material_options` or `material_options_rare` based on a probability check.

### Rarity and Probability

*   **`rare`**: A boolean flag indicating whether a rare material should be chosen.
*   **`rnd`**: A random number generated between 1 and 100.
*   **Rarity Trigger**: If `rnd` is greater than 98 (a 2% chance), the `rare` flag is set to `true`, selecting from `material_options_rare`.

### Component Interaction

*   **`MagicConvertMaterialComponent`**: The script targets entities with this component.
*   **`from_material`**: Reads the material the component is set to convert *from*.
*   **`to_material`**: Sets the material the component will convert *to*. If the target material matches the `from_material`, it's not changed (though the commented-out code suggests a potential for converting to smoke).

## Script Logic

1.  **Initialization**:
    *   Gets the entity ID and its position.
    *   Enables the `"transmutation"` tag on the entity.
    *   Retrieves any existing `MagicConvertMaterialComponent`s.
    *   Sets a random seed based on the entity's position.

2.  **Material Selection**:
    *   Defines tables for common and rare material options.
    *   Determines if a rare material should be selected based on a random roll.
    *   Selects a material from the appropriate table.
    *   Converts the material name string to its internal type using `CellFactory_GetType()`.

3.  **Component Update**:
    *   Iterates through all `MagicConvertMaterialComponent`s found on the entity.
    *   For each component, it checks if the `to_material` should be set to the randomly selected `material`.
    *   The `to_material` of the component is updated.

4.  **Cleanup**:
    *   Disables the `LuaComponent` associated with this script after its execution.