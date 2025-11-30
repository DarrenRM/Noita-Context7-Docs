---
title: ControlsComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ControlsComponent
category: modding-wiki
---

# ControlsComponent Documentation for AI-Assisted Modding

This document details the `ControlsComponent` in Noita, a crucial element for defining how entities interact with player input and game controls. Understanding this component is vital for modders looking to create custom behaviors, new player abilities, or modify existing entity interactions with the game's control system.

## Understanding ControlsComponent

The `ControlsComponent` is an XML-based component that dictates an entity's response to player input. It allows for the mapping of specific actions to button presses, joystick movements, and other control inputs, enabling entities to perform actions or trigger events based on player interaction.

### Core Functionality

The primary purpose of `ControlsComponent` is to bridge the gap between player input and entity behavior. This is achieved through a series of XML tags that define:

*   **Input Mapping:** Which specific player inputs trigger which actions.
*   **Action Definitions:** What actions an entity can perform.
*   **Conditions:** Under what circumstances an action can be triggered.

### Component Structure (XML)

The `ControlsComponent` is defined within an entity's XML file, typically under the `<ControlsComponent>` tag.

```xml
<ControlsComponent
    entity_id="<entity_id>"
    <...>
>
    <Action
        name="<action_name>"
        <...>
    >
        <Input
            name="<input_name>"
            <...>
        />
        <Condition
            <...>
        />
        <...>
    </Action>
    <...>
</ControlsComponent>
```

### Key Attributes and Tags

#### `<ControlsComponent>` Attributes

*   `entity_id`: The unique identifier for the entity this component belongs to.

#### `<Action>` Tag

This tag defines a specific action that an entity can perform in response to input.

*   **Attributes:**
    *   `name`: A unique name for this action (e.g., "jump", "attack", "cast_spell").
    *   `action_id`: An optional numerical ID for the action.
    *   `input_device`: Specifies which input device this action is tied to (e.g., "keyboard", "gamepad"). If omitted, it applies to all devices.
    *   `input_type`: Defines the type of input (e.g., "button", "axis", "hat").
    *   `input_button`: The specific button or key for this action (e.g., "jump", "attack", "W", "Space").
    *   `input_axis`: For axis inputs, specifies the axis (e.g., "left_stick_x", "right_stick_y").
    *   `input_axis_threshold`: For axis inputs, the threshold at which the action is triggered (e.g., "0.5").
    *   `input_hat`: For hat switch inputs, specifies the direction (e.g., "up", "down", "left", "right").
    *   `input_hat_state`: The state of the hat switch (e.g., "pressed", "released").
    *   `input_modifier`: Specifies a modifier key that must be held down for this action (e.g., "shift", "ctrl").
    *   `input_combo`: Allows for defining input combinations (e.g., "ctrl+shift+attack").
    *   `input_hold_duration`: The duration (in seconds) the input must be held for the action to trigger.
    *   `input_release_duration`: The duration (in seconds) the input must be released for the action to trigger.
    *   `input_repeat_delay`: The delay (in seconds) between repeated triggers of the action when the input is held.
    *   `input_repeat_rate`: The rate (in Hz) at which the action is triggered when the input is held.
    *   `input_repeat_limit`: The maximum number of times the action can be repeated.
    *   `input_cooldown`: The cooldown period (in seconds) before this action can be triggered again.
    *   `input_cooldown_group`: Groups actions together for cooldown purposes.
    *   `input_priority`: The priority of this input if multiple inputs are active.
    *   `input_trigger_on_press`: Whether the action triggers on button press.
    *   `input_trigger_on_release`: Whether the action triggers on button release.
    *   `input_trigger_on_hold`: Whether the action triggers while the button is held.
    *   `input_trigger_on_hold_repeat`: Whether the action triggers repeatedly while the button is held.
    *   `input_trigger_on_hold_release`: Whether the action triggers when the button is released after being held.
    *   `input_trigger_on_hold_cancel`: Whether the action triggers when the hold is cancelled.
    *   `input_trigger_on_hold_timeout`: Whether the action triggers when the hold duration is exceeded.
    *   `input_trigger_on_axis_change`: Whether the action triggers when the axis value changes.
    *   `input_trigger_on_hat_change`: Whether the action triggers when the hat switch value changes.
    *   `input_trigger_on_modifier_press`: Whether the action triggers when a modifier key is pressed.
    *   `input_trigger_on_modifier_release`: Whether the action triggers when a modifier key is released.
    *   `input_trigger_on_modifier_hold`: Whether the action triggers while a modifier key is held.
    *   `input_trigger_on_modifier_hold_repeat`: Whether the action triggers repeatedly while a modifier key is held.
    *   `input_trigger_on_modifier_hold_release`: Whether the action triggers when a modifier key is released after being held.
    *   `input_trigger_on_modifier_hold_cancel`: Whether the action triggers when the modifier hold is cancelled.
    *   `input_trigger_on_modifier_hold_timeout`: Whether the action triggers when the modifier hold duration is exceeded.
    *   `input_trigger_on_combo_press`: Whether the action triggers when a combo is pressed.
    *   `input_trigger_on_combo_release`: Whether the action triggers when a combo is released.
    *   `input_trigger_on_combo_hold`: Whether the action triggers while a combo is held.
    *   `input_trigger_on_combo_hold_repeat`: Whether the action triggers repeatedly while a combo is held.
    *   `input_trigger_on_combo_hold_release`: Whether the action triggers when a combo is released after being held.
    *   `input_trigger_on_combo_hold_cancel`: Whether the action triggers when the combo hold is cancelled.
    *   `input_trigger_on_combo_hold_timeout`: Whether the action triggers when the combo hold duration is exceeded.

#### `<Input>` Tag

This tag specifies the actual input that triggers an action. It can be nested within an `<Action>` tag.

*   **Attributes:**
    *   `name`: The name of the input (e.g., "jump", "attack", "W", "Space", "left_stick_x").
    *   `device`: The input device (e.g., "keyboard", "gamepad").
    *   `type`: The type of input (e.g., "button", "axis", "hat").
    *   `axis`: For axis inputs, the specific axis.
    *   `axis_threshold`: The threshold for axis inputs.
    *   `hat`: For hat switch inputs, the direction.
    *   `hat_state`: The state of the hat switch.
    *   `modifier`: A modifier key.
    *   `combo`: A combo of inputs.
    *   `hold_duration`: Duration to hold for.
    *   `release_duration`: Duration to release for.
    *   `repeat_delay`: Delay between repeats.
    *   `repeat_rate`: Rate of repeats.
    *   `repeat_limit`: Limit on repeats.
    *   `cooldown`: Cooldown period.
    *   `cooldown_group`: Cooldown group.
    *   `priority`: Input priority.
    *   `trigger_on_press`: Trigger on press.
    *   `trigger_on_release`: Trigger on release.
    *   `trigger_on_hold`: Trigger on hold.
    *   `trigger_on_hold_repeat`: Trigger on hold repeat.
    *   `trigger_on_hold_release`: Trigger on hold release.
    *   `trigger_on_hold_cancel`: Trigger on hold cancel.
    *   `trigger_on_hold_timeout`: Trigger on hold timeout.
    *   `trigger_on_axis_change`: Trigger on axis change.
    *   `trigger_on_hat_change`: Trigger on hat change.
    *   `trigger_on_modifier_press`: Trigger on modifier press.
    *   `trigger_on_modifier_release`: Trigger on modifier release.
    *   `trigger_on_modifier_hold`: Trigger on modifier hold.
    *   `trigger_on_modifier_hold_repeat`: Trigger on modifier hold repeat.
    *   `trigger_on_modifier_hold_release`: Trigger on modifier hold release.
    *   `trigger_on_modifier_hold_cancel`: Trigger on modifier hold cancel.
    *   `trigger_on_modifier_hold_timeout`: Trigger on modifier hold timeout.
    *   `trigger_on_combo_press`: Trigger on combo press.
    *   `trigger_on_combo_release`: Trigger on combo release.
    *   `trigger_on_combo_hold`: Trigger on combo hold.
    *   `trigger_on_combo_hold_repeat`: Trigger on combo hold repeat.
    *   `trigger_on_combo_hold_release`: Trigger on combo hold release.
    *   `trigger_on_combo_hold_cancel`: Trigger on combo hold cancel.
    *   `trigger_on_combo_hold_timeout`: Trigger on combo hold timeout.

#### `<Condition>` Tag

This tag defines conditions that must be met for an action to be triggered.

*   **Attributes:**
    *   `check_entity_state`: Checks the state of the entity itself (e.g., "is_grounded", "is_flying").
    *   `check_game_state`: Checks the state of the game (e.g., "is_paused", "is_in_combat").
    *   `check_player_state`: Checks the state of the player (e.g., "has_mana", "is_invincible").
    *   `check_item_state`: Checks the state of an item the entity is holding or interacting with.
    *   `check_tag`: Checks if the entity has a specific tag.
    *   `check_component`: Checks if the entity has a specific component.
    *   `check_variable`: Checks the value of a custom variable.
    *   `check_distance`: Checks the distance to another entity.
    *   `check_angle`: Checks the angle relative to another entity.
    *   `check_line_of_sight`: Checks for line of sight to another entity.
    *   `check_collision`: Checks for collision with specific entities or layers.
    *   `check_random`: Triggers based on a random chance.
    *   `check_time`: Triggers based on elapsed time.
    *   `check_input_state`: Checks the current state of another input.
    *   `check_action_state`: Checks if another action is active.
    *   `check_animation_state`: Checks the current animation state.
    *   `check_sound_state`: Checks the current sound state.
    *   `check_particle_state`: Checks the current particle effect state.
    *   `check_script_variable`: Checks a variable within a Lua script.
    *   `check_script_function`: Calls a Lua function and checks its return value.
    *   `check_entity_type`: Checks the type of another entity.
    *   `check_entity_tag`: Checks the tags of another entity.
    *   `check_entity_component`: Checks the components of another entity.
    *   `check_entity_variable`: Checks a variable of another entity.
    *   `check_entity_distance`: Checks the distance to another entity.
    *   `check_entity_angle`: Checks the angle to another entity.
    *   `check_entity_line_of_sight`: Checks line of sight to another entity.
    *   `check_entity_collision`: Checks collision with another entity.
    *   `check_entity_random`: Triggers based on a random chance related to another entity.
    *   `check_entity_time`: Triggers based on elapsed time related to another entity.
    *   `check_entity_input_state`: Checks the input state of another entity.
    *   `check_entity_action_state`: Checks the action state of another entity.
    *   `check_entity_animation_state`: Checks the animation state of another entity.
    *   `check_entity_sound_state`: Checks the sound state of another entity.
    *   `check_entity_particle_state`: Checks the particle state of another entity.
    *   `check_entity_script_variable`: Checks a script variable of another entity.
    *   `check_entity_script_function`: Calls a script function of another entity and checks its return value.

#### `<Trigger>` Tag

This tag defines what happens when an action is triggered.

*   **Attributes:**
    *   `action`: The name of the action to trigger.
    *   `entity_id`: The ID of the entity to trigger the action on.
    *   `entity_tag`: The tag of entities to trigger the action on.
    *   `entity_type`: The type of entities to trigger the action on.
    *   `entity_component`: The component of entities to trigger the action on.
    *   `entity_variable`: A variable of entities to trigger the action on.
    *   `entity_distance`: Distance to trigger the action.
    *   `entity_angle`: Angle to trigger the action.
    *   `entity_line_of_sight`: Line of sight to trigger the action.
    *   `entity_collision`: Collision to trigger the action.
    *   `entity_random`: Random chance to trigger the action.
    *   `entity_time`: Time to trigger the action.
    *   `entity_input_state`: Input state to trigger the action.
    *   `entity_action_state`: Action state to trigger the action.
    *   `entity_animation_state`: Animation state to trigger the action.
    *   `entity_sound_state`: Sound state to trigger the action.
    *   `entity_particle_state`: Particle state to trigger the action.
    *   `entity_script_variable`: Script variable to trigger the action.
    *   `entity_script_function`: Script function to trigger the action.
    *   `spawn_entity`: The ID of an entity to spawn.
    *   `spawn_position`: The position to spawn the entity.
    *   `spawn_direction`: The direction to spawn the entity.
    *   `spawn_count`: The number of entities to spawn.
    *   `play_sound`: The name of a sound to play.
    *   `play_animation`: The name of an animation to play.
    *   `set_variable`: Sets a variable on the entity.
    *   `set_component_variable`: Sets a variable on a component of the entity.
    *   `set_entity_variable`: Sets a variable on another entity.
    *   `set_entity_component_variable`: Sets a variable on a component of another entity.
    *   `add_force`: Adds a force to the entity.
    *   `add_impulse`: Adds an impulse to the entity.
    *   `apply_damage`: Applies damage to the entity.
    *   `apply_status_effect`: Applies a status effect to the entity.
    *   `remove_component`: Removes a component from the entity.
    *   `destroy_entity`: Destroys the entity.
    *   `call_script_function`: Calls a Lua function on the entity.
    *   `send_message`: Sends a message to the entity.

### Example Usage

Here's a simplified example of a `ControlsComponent` for a player character that allows jumping when the "jump" button is pressed, provided the character is grounded.

```xml
<ControlsComponent
    entity_id="player_character"
>
    <Action
        name="jump"
        input_button="jump"
        input_device="keyboard"
        input_trigger_on_press="true"
    >
        <Condition
            check_entity_state="is_grounded"
        />
        <Trigger
            action="jump"
            entity_id="player_character"
        />
    </Action>
</ControlsComponent>
```

This example demonstrates how to:
1.  Define an action named "jump".
2.  Map it to the "jump" button on the keyboard.
3.  Ensure it only triggers on button press.
4.  Add a condition that the entity must be grounded.
5.  Specify that when triggered, the "jump" action should be executed on the "player_character" entity.

## Input Names and Values

The `ControlsComponent` relies on specific input names that correspond to Noita's internal input system. These names are case-sensitive.

### Keyboard Inputs

Common keyboard inputs include:

*   `W`, `A`, `S`, `D` (for movement)
*   `Space` (often for jump)
*   `Ctrl`, `Shift`, `Alt` (modifier keys)
*   `Enter`, `Escape`
*   `F1` through `F12`
*   `MouseLeft`, `MouseRight`, `MouseMiddle`
*   `MouseX`, `MouseY` (for mouse movement axes)

### Gamepad Inputs

Gamepad inputs are typically named based on their function or button position. Common examples include:

*   **Buttons:** `A`, `B`, `X`, `Y` (Xbox layout), `Cross`, `Circle`, `Square`, `Triangle` (PlayStation layout), `Start`, `Select`, `LB`, `RB`, `LT`, `RT`, `LSB`, `RSB` (Left Stick Button, Right Stick Button).
*   **Axes:** `left_stick_x`, `left_stick_y`, `right_stick_x`, `right_stick_y`, `trigger_left`, `trigger_right`.
*   **Hats:** `dpad_up`, `dpad_down`, `dpad_left`, `dpad_right`.

### Custom Input Names

Modders can define their own custom input names within their mod's input configuration files, which can then be referenced in the `ControlsComponent`.

## Useful Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) - For scripting interactions with components.
*   [Entity XML Structure](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Structure) - Understanding how components are integrated into entities.