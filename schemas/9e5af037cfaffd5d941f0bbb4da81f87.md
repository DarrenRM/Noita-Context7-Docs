---
title: 9e5af037cfaffd5d941f0bbb4da81f87
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/9e5af037cfaffd5d941f0bbb4da81f87.xml
---

# 9e5af037cfaffd5d941f0bbb4da81f87

This XML file, identified by the hash `9e5af037cfaffd5d941f0bbb4da81f87`, serves as a schema definition for various game components within Noita. It outlines the structure and properties of different game entities and their behaviors. Essentially, it acts as a blueprint for how certain game elements are defined and configured, influencing everything from enemy AI and character statistics to visual effects and physics. Understanding this schema is crucial for anyone looking to delve into the game's data structure, particularly for modding purposes.

## File Structure

The file is structured as a root `<Schema>` element containing multiple `<Component>` elements. Each `<Component>` represents a distinct type of game logic or data that can be attached to game entities. Within each `<Component>`, there are `<Var>` elements, which define individual properties or variables associated with that component.

The `<Var>` elements have the following common attributes:
*   `name`: The identifier for the variable.
*   `size`: The size of the variable in bytes.
*   `type`: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, `class ConfigExplosion`, `class ceng::math::CVector2<float>`).

The `type` attribute often indicates a C++ class or fundamental data type, suggesting the underlying implementation of these game components. String types are represented by `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, and complex types like explosions or vector math are represented by their respective class names.

## Key Patterns

Several patterns emerge from the sampled content:

*   **Component-Based Architecture:** The game appears to use a component-based system, where entities are composed of various functional components. This file defines the structure of these components.
*   **AI and Behavior Definitions:** Components like `AIAttackComponent` and `AIComponent` clearly define parameters related to enemy artificial intelligence, including attack ranges, probabilities, animations, and movement behaviors.
*   **Physical and Visual Properties:** Components such as `CollisionTriggerComponent` and `LightComponent` define physical dimensions and visual characteristics like light radius, color, and fading.
*   **Particle and Effect Systems:** Components like `ParticleEmitterComponent` (implied by the presence of variables like `y_vel_max`, `gravity`, `lifetime_min`, `count_min`) are likely responsible for defining particle effects and their behavior.
*   **Data Types:** A mix of fundamental C++ types (`int`, `float`, `bool`) and custom class types are used, indicating a structured and potentially complex data model. String types are consistently represented by `std::basic_string`.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `AIAttackComponent`:**
This component defines the parameters for an AI's attack capabilities.
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
    <Var name="state_duration_frames" size="4" type="int" >
    </Var>
    <Var name="animation_name" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="attack_ranged_entity_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="attack_ranged_entity_count_min" size="4" type="int" >
    </Var>
  </Component>
```
This sample shows variables controlling attack probability, range, angular spread, animation, and the specific entity file and count for ranged attacks.

**2. `CollisionTriggerComponent`:**
This component defines properties related to collision detection and triggers.
```xml
  <Component component_name="CollisionTriggerComponent" >
    <Var name="width" size="4" type="float" >
    </Var>
    <Var name="height" size="4" type="float" >
    </Var>
    <Var name="radius" size="4" type="float" >
    </Var>
    <Var name="required_tag" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
  </Component>
```
This defines the geometric dimensions (width, height, radius) for collision and a `required_tag` which might be used to specify what other entities this component should interact with.

**3. `LightComponent`:**
This component defines the properties of a light source.
```xml
  <Component component_name="LightComponent" >
    <Var name="radius" size="4" type="float" >
    </Var>
    <Var name="r" size="4" type="unsigned int" >
    </Var>
    <Var name="g" size="4" type="unsigned int" >
    </Var>
    <Var name="b" size="4" type="unsigned int" >
    </Var>
    <Var name="fade_out_time" size="4" type="float" >
    </Var>
    <Var name="blinking_freq" size="4" type="float" >
    </Var>
  </Component>
```
This shows how light color (RGB), radius, and dynamic properties like fade-out time and blinking frequency are defined.

## Reference

This file contains 6196 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/9e5af037cfaffd5d941f0bbb4da81f87.xml).

---