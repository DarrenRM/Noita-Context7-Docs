---
title: e22f58faf7c5ab9f0cdabd7d97594be7
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/e22f58faf7c5ab9f0cdabd7d97594be7.xml
---

# e22f58faf7c5ab9f0cdabd7d97594be7

This XML file defines the schema for various game components and their properties within Noita. It acts as a blueprint for how different game entities (like enemies, items, or environmental objects) are structured and configured. By defining these components and their associated variables, the game engine knows how to load, interpret, and utilize these elements to create the game world, its mechanics, and its behaviors. This schema file is crucial for understanding the underlying data structure of game assets and is a primary reference for modders.

## File Structure

The file is structured as a series of `<Component>` elements, each representing a distinct type of game logic or functionality. Within each `<Component>`, there are `<Var>` elements that define individual properties or variables associated with that component.

*   **`<Schema>`:** The root element, containing a `hash` attribute.
*   **`<Component>`:** Represents a specific game component. It has a `component_name` attribute that identifies the type of component (e.g., `AIAttackComponent`, `AIComponent`, `ItemPickUpperComponent`).
*   **`<Var>`:** Defines a variable within a component. Each `<Var>` element has the following attributes:
    *   `name`: The name of the variable (e.g., `use_probability`, `min_distance`, `cost`).
    *   `size`: The size of the variable in bytes.
    *   `type`: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, `class ceng::math::CVector2<float>`).

The structure is hierarchical, with components containing variables. The data types often reflect C++ class names, indicating the underlying programming language and libraries used in the game's development.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Component-Based Design:** The game utilizes a component-based architecture, where functionality is broken down into modular components. This is clearly reflected in the `<Component>` tags.
*   **Variable Definitions:** Each component's behavior is defined by a set of named variables (`<Var>`) with specified data types and sizes.
*   **AI and Attack Components:** A significant portion of the schema appears to be dedicated to AI behaviors and attack patterns. Components like `AIAttackComponent` and `AIComponent` suggest detailed control over enemy actions, targeting, and combat mechanics.
*   **Item Properties:** Components like `ItemPickUpperComponent` and `ItemStashComponent` define properties related to items, such as how they are picked up, dropped, or stored.
*   **Physics and Geometry:** Components like `PhysicsShapeComponent` define physical properties such as friction, restitution, and density, as well as shape characteristics (circle, box, capsule).
*   **String Representation:** String data types are represented using `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, which is a common C++ string implementation.
*   **Vector Types:** Vector data, likely for positions or directions, is represented using `class ceng::math::CVector2<float>`.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `AIAttackComponent` Variables:**

```xml
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
```

This snippet from the `AIAttackComponent` defines parameters for an AI's attack capabilities. `use_probability` likely controls how often an attack is attempted, `min_distance` and `max_distance` define the effective range, `angular_range_deg` specifies the cone of attack, `animation_name` links to a visual animation, and `attack_ranged_entity_file` points to the projectile or entity spawned by a ranged attack.

**2. `ItemPickUpperComponent` Variables:**

```xml
  <Component component_name="ItemPickUpperComponent" >

    <Var name="is_in_npc" size="1" type="bool" >
    </Var>

    <Var name="is_immune_to_kicks" size="1" type="bool" >
    </Var>

    <Var name="drop_items_on_death" size="1" type="bool" >
    </Var>

    <Var name="mLatestItemOverlapInfoBoxPosition" size="8" type="class ceng::math::CVector2<float>" >
    </Var>

  </Component>
```

This component defines properties related to how items are handled when picked up. `is_in_npc` might indicate if the item is currently held by an NPC, `is_immune_to_kicks` suggests if it can be kicked away, and `drop_items_on_death` determines if the item is dropped when its owner dies. `mLatestItemOverlapInfoBoxPosition` likely stores the position related to item interaction.

**3. `PhysicsShapeComponent` Variables:**

```xml
  <Component component_name="PhysicsShapeComponent" >

    <Var name="recreate" size="1" type="bool" >
    </Var>

    <Var name="is_circle" size="1" type="bool" >
    </Var>

    <Var name="is_box" size="1" type="bool" >
    </Var>

    <Var name="is_capsule" size="1" type="bool" >
    </Var>

    <Var name="friction" size="4" type="float" >
    </Var>

    <Var name="restitution" size="4" type="float" >
    </Var>

    <Var name="density" size="4" type="float" >
    </Var>

  </Component>
```

This component defines the physical properties of an object. `is_circle`, `is_box`, and `is_capsule` are boolean flags to indicate the shape type. `friction`, `restitution`, and `density` are standard physics parameters that govern how the object interacts with its environment.

## Reference

This file contains 6312 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/e22f58faf7c5ab9f0cdabd7d97594be7.xml).
---