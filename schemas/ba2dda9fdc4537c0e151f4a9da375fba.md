---
title: ba2dda9fdc4537c0e151f4a9da375fba
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ba2dda9fdc4537c0e151f4a9da375fba.xml
---

# ba2dda9fdc4537c0e151f4a9da375fba

This XML file, identified by the hash `ba2dda9fdc4537c0e151f4a9da375fba`, defines the structure and data types for various game components and entities within Noita. It acts as a schema, outlining how different game elements are configured and what properties they possess. This is crucial for the game engine to correctly load, interpret, and utilize these components, influencing everything from enemy AI behavior to the properties of magical wands and environmental interactions. Essentially, it's a blueprint for many of the game's systems.

## File Structure

The file is structured as a collection of `<Component>` elements, each representing a distinct game component. These components are identified by a `component_name` attribute. Within each `<Component>`, there are `<Var>` elements, which define individual variables or properties associated with that component.

Each `<Var>` element has the following key attributes:
*   `name`: The name of the variable.
*   `size`: The size of the variable in bytes.
*   `type`: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` for strings, `class ceng::math::CVector2<float>` for 2D vectors).

The structure is hierarchical, with the root element being `<Schema>` which contains all the `<Component>` definitions.

## Key Patterns

*   **Component-Based Design:** The file clearly follows a component-based architecture, where game entities are composed of various functional components. Each component encapsulates a specific set of behaviors or properties.
*   **Variable Definitions:** The `<Var>` tags are used to define the individual data fields for each component. The `type` attribute is particularly important for understanding how data is stored and interpreted.
*   **String Representation:** C++ string types are represented with a verbose `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`.
*   **Vector Representation:** 2D vectors are represented using `class ceng::math::CVector2<float>`.
*   **Boolean Representation:** Booleans are typically represented with a `size="1"` and `type="bool"`.
*   **Numerical Types:** Integers are `int` and floating-point numbers are `float`. Sizes vary, with `size="4"` being common for both.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`AIAttackComponent`:**
    ```xml
    <Component component_name="AIAttackComponent" >
      <Var name="use_probability" size="4" type="int" >
      </Var>
      <Var name="min_distance" size="4" type="float" >
      </Var>
      <Var name="attack_ranged_entity_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="attack_ranged_use_laser_sight" size="1" type="bool" >
      </Var>
    </Component>
    ```
    This component appears to define parameters for an AI's attack capabilities. It includes variables for attack probability, range (`min_distance`), the entity file to spawn for ranged attacks (`attack_ranged_entity_file`), and whether to use a laser sight for ranged attacks (`attack_ranged_use_laser_sight`).

2.  **`ConsumableTeleportComponent`:**
    ```xml
    <Component component_name="ConsumableTeleportComponent" >
      <Var name="create_other_end" size="1" type="bool" >
      </Var>
      <Var name="target_location" size="8" type="class ceng::math::CVector2<float>" >
      </Var>
      <Var name="mNextUsableFrame" size="4" type="int" >
      </Var>
    </Component>
    ```
    This component likely governs the behavior of consumable items that allow teleportation. It includes a boolean to determine if the other end of the teleport should be created (`create_other_end`), the target location for the teleport (`target_location`), and a frame counter for when the item can be used next (`mNextUsableFrame`).

3.  **`EnergyShieldComponent`:**
    ```xml
    <Component component_name="EnergyShieldComponent" >
      <Var name="radius" size="4" type="float" >
      </Var>
      <Var name="max_energy" size="4" type="float" >
      </Var>
      <Var name="recharge_speed" size="4" type="float" >
      </Var>
      <Var name="energy" size="4" type="float" >
      </Var>
    </Component>
    ```
    This component defines the properties of an energy shield. It includes variables for the shield's radius (`radius`), maximum energy capacity (`max_energy`), how quickly it recharges (`recharge_speed`), and its current energy level (`energy`).

## Reference

This file contains 6804 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ba2dda9fdc4537c0e151f4a9da375fba.xml).

---