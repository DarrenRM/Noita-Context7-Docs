---
title: aacbd4d9cbf4cc419bea41812bb2623f
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/aacbd4d9cbf4cc419bea41812bb2623f.xml
---

# aacbd4d9cbf4cc419bea41812bb2623f

This XML file, identified by the hash `aacbd4d9cbf4cc419bea41812bb2623f`, defines a schema for game data within Noita. Schemas in Noita are blueprints that describe the structure and types of data used for various game entities, components, and behaviors. This particular schema likely governs the configuration and parameters for AI-related functionalities, as indicated by the presence of components like `AIAttackComponent`, `AIComponent`, and `PathFindingComponent`. Understanding these schemas is crucial for comprehending how game elements are defined and how they interact, and it forms the foundation for modding the game.

## File Structure

The file is structured as an XML document. The root element is `<Schema>`, which contains a `hash` attribute. Inside the `<Schema>` element, there are multiple `<Component>` elements. Each `<Component>` element represents a distinct set of properties or a specific functionality and has a `component_name` attribute.

Within each `<Component>`, there are `<Var>` elements. These `<Var>` elements define individual variables or properties associated with that component. Each `<Var>` element has the following attributes:

*   `name`: The name of the variable.
*   `size`: The size of the variable in bytes.
*   `type`: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, `__int64`, `class ceng::math::CVector2<float>`).

The `<Var>` elements can be empty, indicating that their values are defined elsewhere or are implicitly handled.

**Example Structure:**

```xml
<Schema hash="aacbd4d9cbf4cc419bea41812bb2623f" >
  <Component component_name="ComponentName" >
    <Var name="variable_name_1" size="4" type="int" >
    </Var>
    <Var name="variable_name_2" size="8" type="float" >
    </Var>
    </Component>
  <Component component_name="AnotherComponent" >
    <Var name="another_variable" size="1" type="bool" >
    </Var>
  </Component>
</Schema>
```

## Key Patterns

Several patterns are evident from the sampled content:

*   **Component-Based Design:** The schema is organized around distinct `Component` elements, suggesting a modular approach to defining game entity properties and behaviors.
*   **Variable Definitions:** Each component contains `Var` elements that specify the name, size, and type of data it manages. This provides a clear definition of the data structure for each component.
*   **Data Types:** A variety of data types are used, including primitive types like `int`, `float`, and `bool`, as well as more complex types like `class std::basic_string` (for strings) and `class ceng::math::CVector2<float>` (likely for 2D vectors). The `__int64` type is used for larger integer values.
*   **AI Focus:** The presence of components like `AIAttackComponent`, `AIComponent`, and `PathFindingComponent` strongly indicates that this schema is heavily involved in defining the artificial intelligence behaviors of game entities. This includes parameters for attacking, movement, and decision-making.
*   **Numerical Parameters:** Many variables are numerical (`int`, `float`), suggesting that they control values like speed, distance, angles, durations, and probabilities.
*   **Boolean Flags:** `bool` types are used for enabling or disabling specific features or behaviors (e.g., `attack_ranged_enabled`, `affect_flying`, `can_fly`).

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`AIAttackComponent`:**
    This component defines parameters related to an AI's attack capabilities.
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
      <Var name="attack_ranged_use_laser_sight" size="1" type="bool" >
      </Var>
    </Component>
    ```
    This shows how an AI's attack range, probabilities, and the specific projectile or entity it uses for ranged attacks are defined.

2.  **`BossDragonComponent`:**
    This component appears to define parameters specific to a "BossDragon" entity, likely controlling its movement and physical properties.
    ```xml
    <Component component_name="BossDragonComponent" >
      <Var name="speed" size="4" type="float" >
      </Var>
      <Var name="speed_hunt" size="4" type="float" >
      </Var>
      <Var name="gravity" size="4" type="float" >
      </Var>
      <Var name="part_distance" size="4" type="float" >
      </Var>
    </Component>
    ```
    This illustrates how specific entities can have their own unique sets of configurable parameters, such as different speeds for normal movement versus hunting.

3.  **`PathFindingComponent`:**
    This component details the parameters that govern an entity's pathfinding capabilities.
    ```xml
    <Component component_name="PathFindingComponent" >
      <Var name="search_depth_max_no_goal" size="4" type="int" >
      </Var>
      <Var name="iterations_max_no_goal" size="4" type="int" >
      </Var>
      <Var name="cost_of_flying" size="4" type="float" >
      </Var>
      <Var name="can_fly" size="1" type="bool" >
      </Var>
    </Component>
    ```
    This shows how the AI's ability to navigate the game world is configured, including limits on search depth, iteration counts, and whether the entity can fly.

## Reference

This file contains 6552 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/aacbd4d9cbf4cc419bea41812bb2623f.xml).
---