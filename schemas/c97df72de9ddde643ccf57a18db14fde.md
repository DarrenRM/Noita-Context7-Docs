---
title: c97df72de9ddde643ccf57a18db14fde
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/c97df72de9ddde643ccf57a18db14fde.xml
---

# c97df72de9ddde643ccf57a18db14fde

This XML file, identified by the hash `c97df72de9ddde643ccf57a18db14fde`, defines the structure and properties of various game components and entities within Noita. It acts as a schema, outlining the data types, sizes, and names of variables that make up these game elements. This file is crucial for the game's engine to understand and instantiate objects, behaviors, and attributes, essentially serving as a blueprint for game data. By defining these components, the game can manage everything from enemy AI and player controls to visual effects and scripting logic.

## File Structure

The file is structured as a collection of `<Component>` elements, each representing a distinct functional part of a game entity. Each `<Component>` has a `component_name` attribute that identifies its purpose. Inside each `<Component>`, there are `<Var>` elements, which define individual variables.

Each `<Var>` element has the following attributes:
*   `name`: The name of the variable.
*   `size`: The size of the variable in bytes.
*   `type`: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` for strings, or custom class types).

The structure is hierarchical: the root element is `<Schema>`, containing multiple `<Component>` elements, which in turn contain multiple `<Var>` elements.

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

Several patterns emerge from the sampled data:

*   **Component-Based Design:** The game utilizes a component-based architecture, where entities are composed of various functional components. This is evident from the distinct `<Component>` tags like `AIAttackComponent`, `AIComponent`, `ControlsComponent`, and `LightningComponent`.
*   **Variable Definitions:** Each component is defined by a set of variables (`<Var>`) that hold its specific data. These variables cover a wide range of data types, including integers (`int`), floating-point numbers (`float`), booleans (`bool`), and strings (represented by `class std::basic_string...`).
*   **AI and Behavior:** Components like `AIAttackComponent` and `AIComponent` suggest detailed definitions for enemy behavior, including attack parameters (distance, angles, animations), movement, and environmental awareness (wall/floor detection).
*   **Player and Input:** The `ControlsComponent` indicates how player input and specific actions like polymorphing are handled.
*   **Visual and Effect Components:** Components like `LightningComponent` point to the definition of visual effects, including sprite files, explosion configurations, and projectile properties.
*   **Scripting Integration:** The presence of components related to scripting (e.g., `script_source_file`, `vm_type`, `execute_on_added`) highlights the game's reliance on Lua scripting for dynamic behavior and events.
*   **Data Types and Sizes:** The `size` attribute often corresponds to standard data type sizes (e.g., 4 bytes for `int` and `float`, 1 byte for `bool`). String types (`class std::basic_string...`) have larger sizes, likely accommodating the string data itself and internal management structures.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `AIAttackComponent`:**
This component defines parameters for an AI's attack capabilities.

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
    ...
  </Component>
```
This shows how an AI's attack can be configured with probabilities, ranges, and specific projectile or effect files.

**2. `AIComponent` (partial):**
This component likely governs general AI behavior and environmental interaction.

```xml
  <Component component_name="AIComponent" >
    <Var name="wall_detection_aabb_min_y" size="4" type="float" >
    </Var>
    <Var name="floor_detection_aabb_max_x" size="4" type="float" >
    </Var>
    <Var name="floor_detection_aabb_max_y" size="4" type="float" >
    </Var>
  </Component>
```
This snippet illustrates how the AI might detect its surroundings, using axis-aligned bounding box (AABB) parameters for wall and floor detection.

**3. `LightningComponent`:**
This component defines properties for lightning-based effects.

```xml
  <Component component_name="LightningComponent" >
    <Var name="config_explosion" size="364" type="class ConfigExplosion" >
    </Var>
    <Var name="sprite_lightning_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="is_projectile" size="1" type="bool" >
    </Var>
    <Var name="explosion_type" size="4" type="int" >
    </Var>
    <Var name="arc_lifetime" size="4" type="int" >
    </Var>
  </Component>
```
This shows that lightning effects can be configured with explosion data, sprite assets, and properties like whether they are projectiles and their lifetime.

**4. Scripting Component (partial):**
This component, likely part of a broader scripting system, defines how scripts are executed.

```xml
    <Var name="script_source_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="vm_type" size="4" type="enum LUA_VM_TYPE::Enum" >
    </Var>
    <Var name="execute_on_added" size="1" type="bool" >
    </Var>
    <Var name="execute_every_n_frame" size="4" type="int" >
    </Var>
    <Var name="remove_after_executed" size="1" type="bool" >
    </Var>
```
This indicates that scripts can be loaded from files, run in specific virtual machine types, and triggered by game events like entity addition or at regular frame intervals.

## Reference

This file contains 6776 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/c97df72de9ddde643ccf57a18db14fde.xml).

---