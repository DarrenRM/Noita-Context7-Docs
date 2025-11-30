---
title: player
category: enemies_gfx
source: https://github.com/NathanSnail/noitadata/tree/main/data/enemies_gfx/player.xml
---

# player

This `player.xml` file defines the visual animations and sprite properties for the player character in Noita. It dictates how the player appears in various states, including standing, walking, running, jumping, and reacting to damage or environmental effects. This file is crucial for the game's visual presentation of the player character, linking sprite sheets and animation sequences to specific in-game actions and states.

## File Structure

The file is structured as an XML document. The root element is `<Sprite>`, which encapsulates all the animation definitions for the player.

*   **`<Sprite>`**: This is the main container element.
    *   `filename`: Specifies the path to the main sprite sheet image for the player.
    *   `hotspots_filename`: Points to an image file that defines specific points (hotspots) within the sprite sheet, likely used for collision detection or interaction points.
    *   `offset_x`, `offset_y`: These attributes define a global offset for the entire sprite, adjusting its position relative to its origin.
    *   `default_animation`: Specifies the name of the animation that should play by default when the player character is loaded.

*   **`<RectAnimation>`**: This element defines a specific animation sequence. Multiple `<RectAnimation>` elements are nested within the `<Sprite>` tag, each representing a distinct player action or state.
    *   `name`: A unique identifier for the animation (e.g., "stand", "walk", "jump_up").
    *   `frame_count`: The total number of frames in this animation sequence.
    *   `frame_width`, `frame_height`: The dimensions of each individual frame within the sprite sheet.
    *   `frames_per_row`: How many frames are arranged horizontally in the sprite sheet. This is used to calculate the position of each frame.
    *   `pos_x`, `pos_y`: The starting coordinates (top-left corner) of the animation's frames within the sprite sheet.
    *   `frame_wait`: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `loop`: If set to "0", the animation will not loop. By default, animations are assumed to loop.
    *   `shrink_by_one_pixel`: A boolean attribute (indicated by "1" or "0") that suggests a minor adjustment to the sprite's dimensions for certain animations.

*   **`<Event>`**: Nested within `<RectAnimation>`, these elements define specific events that can occur at certain frames of an animation.
    *   `name`: The type of event (e.g., "step", "kick", "throw").
    *   `frame`: The specific frame number within the animation at which this event should trigger.
    *   `probability`: The chance (0 to 1) that this event will occur when the specified frame is reached.
    *   `on_finished`: If set to "1", the event will trigger when the animation finishes.
    *   `max_distance`: Potentially related to the range or effect of the event.
    *   `check_physics_material`: A boolean attribute that might indicate whether the event's behavior is dependent on the physics material of the player's current surface.

## Key Patterns

*   **Animation Naming Convention**: Animations are generally named descriptively, reflecting the player's action (e.g., `stand`, `walk`, `run`, `jump_up`, `hurt`, `slide_start`).
*   **Sprite Sheet Layout**: The `pos_y` attribute for `<RectAnimation>` elements increases sequentially, suggesting that different animations are laid out in rows on the sprite sheet. The `frames_per_row` attribute is consistent (often "8"), indicating a standard grid layout.
*   **Animation Timing**: `frame_wait` values vary, with shorter durations (e.g., `0.05`, `0.08`) for faster animations and longer durations for slower ones.
*   **Event Triggers**: Events are often tied to specific frames within an animation, such as the start or middle of a movement, to trigger game logic (e.g., sound effects, particle effects, damage application).
*   **`check_physics_material` Attribute**: This attribute appears in events related to movement and actions, suggesting that certain game mechanics might adapt based on the surface the player is interacting with.
*   **Looping vs. Non-Looping**: Most movement and idle animations appear to be looping by default, while specific actions like `jump_up` or `kick_alt` are explicitly set to `loop="0"`, meaning they play once.

## Sample Entries

**1. `stand` Animation:**
```xml
	<RectAnimation 
		frame_count="6" 
		frame_height="19" 
		frame_wait="0.2" 
		frame_width="12" 
		frames_per_row="8" 
		name="stand" 
		pos_x="0" 
		pos_y="1" >
	</RectAnimation>
```
This defines the player's idle animation. It consists of 6 frames, each 12 pixels wide and 19 pixels high. The frames are laid out in a grid with 8 frames per row, starting at `pos_x="0"` and `pos_y="1"` on the sprite sheet. Each frame is displayed for 0.2 seconds, and the animation loops by default.

**2. `walk` Animation with `step` Events:**
```xml
	<RectAnimation 
		frame_count="6" 
		frame_height="19" 
		frame_wait="0.105" 
		frame_width="12" 
		frames_per_row="8" 
		name="walk" 
		pos_x="0" 
		pos_y="21" >

		<Event 
			check_physics_material="1" 
			frame="0" 
			max_distance="500" 
			name="step" 
			on_finished="0" 
			probability="1" >

		</Event>

		<Event 
			check_physics_material="1" 
			frame="3" 
			max_distance="500" 
			name="step" 
			on_finished="0" 
			probability="1" >

		</Event>
	</RectAnimation>
```
This defines the player's walking animation. It also has 6 frames of the same dimensions as `stand`, but starts at `pos_y="21"` on the sprite sheet. The `frame_wait` is shorter at 0.105 seconds, making it faster. Crucially, it includes two `<Event>` tags named "step". These events are set to trigger at frame 0 and frame 3 of the animation, with a probability of 1. The `check_physics_material="1"` suggests that these "step" events might play different sounds or spawn different particles depending on the surface the player is walking on.

**3. `kick_alt` Animation:**
```xml
	<RectAnimation 
		frame_count="3" 
		frame_height="20" 
		frame_wait="0.11" 
		frame_width="13" 
		frames_per_row="8" 
		loop="0" 
		name="kick_alt" 
		pos_x="0" 
		pos_y="221" 
		shrink_by_one_pixel="1" >

		<Event 
			check_physics_material="0" 
			frame="2" 
			max_distance="500" 
			name="kick" 
			on_finished="0" 
			probability="1" >

		</Event>
	</RectAnimation>
```
This defines an alternative kick animation. It has 3 frames, each 13 pixels wide and 20 pixels high, starting at `pos_y="221"`. The `loop="0"` attribute indicates this animation plays only once. It has a `shrink_by_one_pixel="1"` attribute, which might adjust its visual size slightly. An event named "kick" is set to trigger at frame 2, likely to apply damage or trigger a visual effect associated with the kick.

## Reference

This file contains 1117 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/enemies_gfx/player.xml).

---