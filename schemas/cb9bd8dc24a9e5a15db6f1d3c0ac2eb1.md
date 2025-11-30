---
title: cb9bd8dc24a9e5a15db6f1d3c0ac2eb1
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/cb9bd8dc24a9e5a15db6f1d3c0ac2eb1.xml
---

# cb9bd8dc24a9e5a15db6f1d3c0ac2eb1

This XML file defines various game components and their associated variables, serving as a schema for how these components are structured and configured within Noita. These components likely represent different functionalities, behaviors, or properties of entities, enemies, or game mechanics. By defining these components and their variables, the game can dynamically load and manage the characteristics of its diverse elements.

## File Structure

The file is structured as a collection of `<Component>` elements, each representing a distinct game component. The root element `<Schema>` encloses all these components and has a `hash` attribute, likely for internal game referencing or integrity checks.

Each `<Component>` element has a `component_name` attribute that clearly identifies the type of component it defines. Inside each component, there are `<Var>` elements, which represent individual variables or properties associated with that component.

The `<Var>` elements have the following key attributes:
*   `name`: The name of the variable (e.g., `use_probability`, `min_distance`, `recognized_entity_tags`).
*   `size`: The size of the variable in bytes. This can vary significantly, indicating different data types or complex structures.
*   `type`: The data type of the variable. This can range from primitive types like `int`, `float`, and `bool` to more complex C++ types such as `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` (which represents a string) and `class ceng::math::CVector2<float>` (a 2D vector of floats).

The structure is hierarchical:
```xml
<Schema hash="...">
  <Component component_name="...">
    <Var name="..." size="..." type="...">
    </Var>
    <Var name="..." size="..." type="...">
    </Var>
    ...
  </Component>
  <Component component_name="...">
    ...
  </Component>
  ...
</Schema>
```

## Key Patterns

*   **Component-Based Design:** The file clearly follows a component-based architecture, where distinct functionalities are encapsulated into named components.
*   **Variable Definitions:** Each component is defined by a set of variables, specifying its configurable parameters.
*   **Data Type Variety:** The `type` attribute shows a mix of fundamental data types and more complex C++ class representations, indicating how game data is stored and managed.
*   **String Representation:** Strings are consistently represented using `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`.
*   **Vector Representation:** Vector types, like `CVector2<float>`, are also represented as class types.
*   **Boolean Representation:** Booleans are represented with `size="1"` and `type="bool"`.
*   **Numeric Types:** Integers are `type="int"` and floats are `type="float"`.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `AIAttackComponent`:**
This component appears to define parameters related to an AI's attacking behavior.
```xml
  <Component component_name="AIAttackComponent" >
    <Var name="use_probability" size="4" type="int" >
    </Var>
    <Var name="min_distance" size="4" type="float" >
    </Var>
    <Var name="max_distance" size="4" type="float" >
    </Var>
    <Var name="angular_range_deg" size="4" type="float" >
    </Var>
    <Var name="animation_name" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="attack_ranged_entity_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
  </Component>
```
This sample shows variables for attack range, angles, animation triggers, and the entity file used for ranged attacks.

**2. `AltarComponent`:**
This component seems to define the behavior and properties of altars in the game.
```xml
  <Component component_name="AltarComponent" >
    <Var name="recognized_entity_tags" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="good_fx_material" size="4" type="int" >
    </Var>
    <Var name="uses_remaining" size="4" type="int" >
    </Var>
  </Component>
```
Here, we see variables for tags of entities the altar recognizes, material IDs for visual effects, and the number of uses left.

**3. `IKLimbWalkerComponent`:**
This component likely governs the movement and locomotion of entities with articulated limbs.
```xml
  <Component component_name="IKLimbWalkerComponent" >
    <Var name="ground_attachment_min_spread" size="4" type="float" >
    </Var>
    <Var name="leg_velocity_coeff" size="4" type="float" >
    </Var>
    <Var name="mTarget" size="8" type="class ceng::math::CVector2<float>" >
    </Var>
    <Var name="mState" size="4" type="int" >
    </Var>
  </Component>
```
This example includes parameters for leg movement, target positions (`mTarget`), and the current state of the component.

## Reference

This file contains 6124 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/cb9bd8dc24a9e5a15db6f1d3c0ac2eb1.xml).

---