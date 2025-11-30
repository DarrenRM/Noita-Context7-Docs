---
title: Noita Lua API Documentation
source: https://noita.wiki.gg/wiki/Modding:_Lua_API
category: modding-wiki
---

# Noita Lua API Documentation

This document serves as a comprehensive reference for the Noita Lua API, detailing the functions, hooks, and global variables available to modders. Understanding this API is crucial for creating custom content, modifying game mechanics, and extending the Noita experience.

## Version

The current modding API version is **12**.

## Lua Tables

Noita utilizes Lua 5.1. The API is divided into two categories: Restricted (Safe) and Unrestricted (Unsafe). The Unrestricted API is only accessible if "Unsafe mods" is enabled in the game settings.

### Restricted API

The restricted API includes:

*   **Basic Functions**: Standard Lua functions, excluding `load`, `loadstring`, `require`, `gcinfo`, and `collectgarbage`.
*   **Table Manipulation**: Functions from the `table` library.
*   **String Manipulation**: Functions from the `string` library.
*   **Mathematical Functions**: Functions from the `math` library.
*   **BitOp**: Functions from the `bit` library.
*   **jit.\* Library**: Functions from the `jit` library.
*   `newproxy()`: A hidden, undocumented function.

### Unrestricted API

The unrestricted API encompasses all functions from the Lua Reference Manual (version 5.1), in addition to the `bit` library, `jit.*` library, and `newproxy()`.

## Core Functions

These are top-level functions defined by Noita.

### do\_mod\_appends

`do_mod_appends( filename:string )`

Appends the content of a specified file to the current mod's script execution.

### dofile

`dofile( filename:string ) -> (nil|script_return_type)|(nil,error_string)`

Noita overrides the built-in `dofile` function. It executes a Lua script file and returns its return value, or `nil, error_string` if the script encounters errors.

### dofile\_once

`dofile_once( filename:string ) -> (nil|script_return_type)|(nil,error_string)`

Executes a Lua script file only once per Lua context. It returns the script's return value or `nil, error_string` if errors occur. For performance, `dofile_once` is recommended unless the standard `dofile` behavior is explicitly needed.

### loadfile

`loadfile( filename:string ) -> (nil|script_as_function)|(nil,error_string)`

Noita overrides the built-in `loadfile` function. This function loads a Lua file and returns a function representing the script, along with an error string if loading fails.

### print

`print`

Noita overrides the built-in `print` function.

### print\_error

`print_error`

Similar to `print`, but also writes the output to `logger.txt` in the Noita game folder.

## Hooks

Hooks are functions that Noita calls at specific points in its execution, allowing mods to react to game events.

### OnBiomeConfigLoaded

`OnBiomeConfigLoaded()`

This hook is called during mod initialization, and it's the earliest point where `CellFactory_*` functions can be safely used.

### OnCountSecrets

`OnCountSecrets() -> int,int`

This hook is called to count secrets. It returns two integers: the total number of secrets and the number of secrets found.

### OnMagicNumbersAndWorldSeedInitialized

`OnMagicNumbersAndWorldSeedInitialized()`

This hook is called after magic numbers and the world seed have been initialized.

### OnModInit

`OnModInit()`

Called once for each mod after `OnModPreInit` and before `OnModPostInit`.

### OnModPostInit

`OnModPostInit()`

Called once for each mod after `OnModPreInit` and `OnModInit`.

### OnModPreInit

`OnModPreInit()`

Called once for each mod before `OnModInit` and `OnModPostInit`.

### OnModSettingsChanged

`OnModSettingsChanged()`

This hook is intended to be called when the game is unpaused if mod settings were changed while paused. However, it is reported to be unreliable, and modders often use `OnPausedChanged` instead.

### OnPausePreUpdate

`OnPausePreUpdate()`

Called when the game is paused, either through the pause menu or inventory screens. Use with caution, as not all game systems may behave correctly when called during a paused state.

### OnPausedChanged

`OnPausedChanged( is_paused:bool, is_inventory_pause:bool )`

Called when the pause state of the game changes.
*   `is_paused`: A boolean indicating if the game is now paused.
*   `is_inventory_pause`: A boolean indicating if the pause is due to an inventory screen.

### OnPlayerDied

`OnPlayerDied( player_entity:int )`

Called when the player character dies. The `player_entity` ID is passed as an argument. This hook also runs when starting a new game within the same session.

### OnPlayerSpawned

`OnPlayerSpawned( player_entity:int )`

Called whenever the player entity is spawned in the game. The `player_entity` ID is passed as an argument. This hook runs at the start of a new game and when a game is loaded.

### OnWorldInitialized

`OnWorldInitialized()`

Called when a new world is created or loaded. Note that `OnWorldPreUpdate` and `OnWorldPostUpdate` will be called at least once before this hook.

### OnWorldPostUpdate

`OnWorldPostUpdate()`

Called after the game has finished updating the world state for the current frame.

### OnWorldPreUpdate

`OnWorldPreUpdate()`

Called just before the game begins updating the world state for the current frame.

## Game Callback Order

The following is the order in which initialization hooks are called:

1.  `OnModPreInit`
2.  `OnModInit`
3.  `OnModPostInit`
4.  `OnMagicNumbersAndWorldSeedInitialized`
5.  `OnBiomeConfigLoaded`
6.  `OnWorldPreUpdate`
7.  `OnWorldPostUpdate`
8.  `OnWorldInitialized`
9.  `OnPlayerSpawned`

The game first executes the hook in `data/scripts/init.lua` (if it exists), followed by each mod's hooks in their respective load order.

## Mod Settings (settings.lua)

These hooks are defined within a mod's `settings.lua` file to manage custom mod settings.

### ModSettingsGui

`ModSettingsGui( gui, in_main_menu:bool )`

This function is responsible for drawing the mod's settings UI. If this function is not defined correctly, the mod's settings will not appear in the game's mod settings menu.

*   `gui`: An object representing the GUI context for drawing.
*   `in_main_menu`: A boolean indicating if the settings are being displayed in the main menu.

### ModSettingsUpdate

`ModSettingsUpdate( init_scope:int )`

This function ensures that the correct setting values are available to the game via `ModSettingGet()`. If this function is not defined, mod settings may not function correctly.

This function is called in several scenarios:

*   When entering the mod settings menu (`init_scope` will be `MOD_SETTING_SCOPE_ONLY_SET_DEFAULT`).
*   Before mod initialization when starting a new game (`init_scope` will be `MOD_SETTING_SCOPE_NEW_GAME`).
*   When entering the game after a restart (`init_scope` will be `MOD_SETTING_SCOPE_RESTART`).
*   At the end of an update when mod settings have been changed via `ModSettingSetNextValue()` and the game is unpaused (`init_scope` will be `MOD_SETTING_SCOPE_RUNTIME`).

*Note: The exact values for the `init_scope` constants are not fully documented, but they range from 0 to 3.*

### ModSettingsGuiCount

`ModSettingsGuiCount() -> int`

This function should return the number of UI elements for the mod's settings. If this function is not implemented correctly, the mod's settings may not be displayed.

If your mod's settings change dynamically, you might need custom logic here. Currently, returning 0 or 1 is acceptable, but this behavior is not guaranteed for future versions. This function is called every frame while the settings menu is open.

## General functions

This section details general-purpose functions for interacting with entities, the game world, and various game systems.

### EntityLoad

`EntityLoad( filename:string, pos_x:number = 0, pos_y:number = 0 ) -> entity_id:int`

Creates an entity (game object) at a specified position.

*   `filename`: The path to the entity's XML definition file.
*   `pos_x`: The x-coordinate for the entity's position (defaults to 0).
*   `pos_y`: The y-coordinate for the entity's position (defaults to 0).

Returns the ID of the newly created entity.

**Example:**

```lua
-- Get the ID of the entity currently being updated.
local entity_id = GetUpdatedEntityID()

-- Get the position of the current entity.
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Load an entity from a file at the current entity's position.
local new_entity_id = EntityLoad( "data/entities/particles/image_emitters/spell_refresh_effect.xml", pos_x, pos_y )
```

*Note: `GetUpdatedEntityID()` is only reliable within entity scripts. In other contexts, it returns `nil`. Alternative methods for obtaining positions include `GameGetCameraPos()`, `DEBUG_GetMouseWorld()`, or `EntityGetTransform()` on other entities like the player.*

### EntityLoadEndGameItem

`EntityLoadEndGameItem( filename:string, pos_x:number = 0, pos_y:number = 0 ) -> entity_id:int`

Loads an entity that is specifically designated as an "end game item."

### EntityLoadCameraBound

`EntityLoadCameraBound( filename:string, pos_x:number = 0, pos_y:number = 0 )`

Loads an entity that is bound to the camera's view.

### EntityLoadToEntity

`EntityLoadToEntity( filename:string, entity:int )`

Loads components from a specified XML file into an existing entity. This function does not load tags or other metadata.

### EntitySave

`EntitySave( entity_id:int, filename:string )`

Saves an entity to a specified XML file. This function is intended for development builds and should be used with caution as it can overwrite existing files.

*   `entity_id`: The ID of the entity to save.
*   `filename`: The path and name of the XML file to save to.

**Example:**

```lua
-- Load an entity from a file.
local entity_id = EntityLoad("data/entities/test_sprite.xml")

-- Save the entity to a new XML file.
EntitySave(entity_id, "data/entities/saved_entity.xml")
```

### EntityCreateNew

`EntityCreateNew( filename:string ) -> entity_id:int`

Creates a new entity based on the provided XML definition.

### EntityKill

`EntityKill( entity_id:int )`

Destroys the specified entity.

### EntityGetIsAlive

`EntityGetIsAlive( entity_id:int ) -> bool`

Checks if an entity is currently alive.

### EntityAddComponent

`EntityAddComponent( entity_id:int, component_name:string, component_data:table ) -> component_id:int`

Adds a component to an entity.

*   `entity_id`: The ID of the entity to add the component to.
*   `component_name`: The name of the component to add (e.g., "DamageModelComponent").
*   `component_data`: A table containing the data for the new component.

Returns the ID of the newly added component.

### EntityRemoveComponent

`EntityRemoveComponent( entity_id:int, component_id:int )`

Removes a component from an entity using its component ID.

### EntityGetAllComponents

`EntityGetAllComponents( entity_id:int ) -> table`

Retrieves a list of all components attached to an entity.

### EntityGetComponent

`EntityGetComponent( entity_id:int, component_name:string ) -> component_id:int`

Retrieves the ID of a component attached to an entity by its name. If multiple components of the same name exist, it returns the first one found.

### EntityGetFirstComponent

`EntityGetFirstComponent( entity_id:int, component_name:string ) -> component_id:int`

Similar to `EntityGetComponent`, but specifically retrieves the first component of a given name.

### EntityGetComponentIncludingDisabled

`EntityGetComponentIncludingDisabled( entity_id:int, component_name:string ) -> component_id:int`

Retrieves the ID of a component, even if it is currently disabled.

### EntityGetFirstComponentIncludingDisabled

`EntityGetFirstComponentIncludingDisabled( entity_id:int, component_name:string ) -> component_id:int`

Retrieves the ID of the first component, even if it is currently disabled.

### EntitySetTransform

`EntitySetTransform( entity_id:int, x:number, y:number, rotation:number )`

Sets the position and rotation of an entity.

### EntityApplyTransform

`EntityApplyTransform( entity_id:int, x:number, y:number, rotation:number )`

Applies a transformation to an entity's current position and rotation.

### EntityGetTransform

`EntityGetTransform( entity_id:int ) -> x:number, y:number, rotation:number`

Retrieves the current position and rotation of an entity.

### EntityAddChild

`EntityAddChild( parent_entity_id:int, child_entity_id:int )`

Makes one entity a child of another.

### EntityGetAllChildren

`EntityGetAllChildren( entity_id:int ) -> table`

Retrieves a list of all direct children of an entity.

### EntityGetParent

`EntityGetParent( entity_id:int ) -> parent_entity_id:int`

Retrieves the ID of the parent entity.

### EntityGetRootEntity

`EntityGetRootEntity( entity_id:int ) -> root_entity_id:int`

Retrieves the ID of the root entity in a hierarchy.

### EntityRemoveFromParent

`EntityRemoveFromParent( entity_id:int )`

Removes an entity from its parent.

### EntitySetComponentsWithTagEnabled

`EntitySetComponentsWithTagEnabled( entity_id:int, tag:string, enabled:bool )`

Enables or disables all components of an entity that have a specific tag.

### EntitySetComponentIsEnabled

`EntitySetComponentIsEnabled( component_id:int, enabled:bool )`

Enables or disables a specific component.

### EntityGetName

`EntityGetName( entity_id:int ) -> name:string`

Retrieves the name of an entity.

### EntitySetName

`EntitySetName( entity_id:int, name:string )`

Sets the name of an entity.

### EntityGetTags

`EntityGetTags( entity_id:int ) -> table`

Retrieves a list of all tags associated with an entity.

### EntityGetWithTag

`EntityGetWithTag( tag:string ) -> entity_id:int`

Retrieves the ID of an entity that has a specific tag. If multiple entities have the tag, it returns the first one found.

### EntityGetInRadius

`EntityGetInRadius( pos_x:number, pos_y:number, radius:number ) -> table`

Retrieves a list of entity IDs within a specified radius around a point.

### EntityGetInRadiusWithTag

`EntityGetInRadiusWithTag( pos_x:number, pos_y:number, radius:number, tag:string ) -> table`

Retrieves a list of entity IDs within a specified radius that also have a specific tag.

### EntityGetClosest

`EntityGetClosest( pos_x:number, pos_y:number ) -> entity_id:int`

Finds the entity closest to a given point.

### EntityGetClosestWithTag

`EntityGetClosestWithTag( pos_x:number, pos_y:number, tag:string ) -> entity_id:int`

Finds the entity closest to a given point that also has a specific tag.

### EntityGetWithName

`EntityGetWithName( name:string ) -> entity_id:int`

Retrieves the ID of an entity by its name.

### EntityAddTag

`EntityAddTag( entity_id:int, tag:string )`

Adds a tag to an entity.

### EntityRemoveTag

`EntityRemoveTag( entity_id:int, tag:string )`

Removes a tag from an entity.

### EntityHasTag

`EntityHasTag( entity_id:int, tag:string ) -> bool`

Checks if an entity has a specific tag.

### EntityGetFilename

`EntityGetFilename( entity_id:int ) -> filename:string`

Retrieves the filename used to load an entity.

### EntitiesGetMaxID

`EntitiesGetMaxID() -> max_id:int`

Returns the highest entity ID currently in use.

### ComponentAddTag

`ComponentAddTag( component_id:int, tag:string )`

Adds a tag to a component.

### ComponentRemoveTag

`ComponentRemoveTag( component_id:int, tag:string )`

Removes a tag from a component.

### ComponentHasTag

`ComponentHasTag( component_id:int, tag:string ) -> bool`

Checks if a component has a specific tag.

### ComponentGetTags

`ComponentGetTags( component_id:int ) -> table`

Retrieves a list of all tags associated with a component.

### ComponentGetValue2

`ComponentGetValue2( component_id:int, key:string ) -> value`

Retrieves the value of a specific field within a component.

### ComponentSetValue2

`ComponentSetValue2( component_id:int, key:string, value )`

Sets the value of a specific field within a component.

### ComponentObjectGetValue2

`ComponentObjectGetValue2( component_id:int, object_key:string, field_key:string ) -> value`

Retrieves a value from a nested object within a component.

### ComponentObjectSetValue2

`ComponentObjectSetValue2( component_id:int, object_key:string, field_key:string, value )`

Sets a value within a nested object of a component.

### EntityAddComponent2

`EntityAddComponent2( entity_id:int, component_name:string, component_data:table ) -> component_id:int`

An alternative function for adding components to an entity.

### ComponentGetVectorSize

`ComponentGetVectorSize( component_id:int, vector_name:string ) -> size:int`

Gets the size of a vector field within a component.

### ComponentGetVectorValue

`ComponentGetVectorValue( component_id:int, vector_name:string, index:int ) -> value`

Gets a specific element from a vector field within a component.

### ComponentGetVector

`ComponentGetVector( component_id:int, vector_name:string ) -> table`

Retrieves an entire vector field from a component.

### ComponentGetEntity

`ComponentGetEntity( component_id:int ) -> entity_id:int`

Retrieves the entity ID that a component belongs to.

### ComponentGetIsEnabled

`ComponentGetIsEnabled( component_id:int ) -> bool`

Checks if a component is currently enabled.

### ComponentGetMembers

`ComponentGetMembers( component_id:int ) -> table`

Retrieves a list of all members (fields) of a component.

### ComponentObjectGetMembers

`ComponentObjectGetMembers( component_id:int, object_key:string ) -> table`

Retrieves the members of a nested object within a component.

### ComponentGetTypeName

`ComponentGetTypeName( component_id:int ) -> type_name:string`

Retrieves the type name of a component.

### GetUpdatedEntityID

`GetUpdatedEntityID() -> entity_id:int`

Returns the ID of the entity currently being processed by the game loop. This function is only reliable within entity scripts.

### GetUpdatedComponentID

`GetUpdatedComponentID() -> component_id:int`

Returns the ID of the component currently being processed by the game loop.

### SetTimeOut

`SetTimeOut( callback:function, delay_frames:int )`

Schedules a function to be called after a specified number of frames.

### RegisterSpawnFunction

`RegisterSpawnFunction( entity_filename:string, spawn_function:function )`

Registers a custom function to be called when a specific entity is spawned.

### SpawnActionItem

`SpawnActionItem( item_filename:string, pos_x:number, pos_y:number ) -> entity_id:int`

Spawns an item that can be picked up and used as an action.

### SpawnStash

`SpawnStash( stash_filename:string, pos_x:number, pos_y:number ) -> entity_id:int`

Spawns a stash container.

### SpawnApparition

`SpawnApparition( apparition_filename:string, pos_x:number, pos_y:number ) -> entity_id:int`

Spawns an apparition entity.

### LoadEntityToStash

`LoadEntityToStash( entity_id:int, stash_entity_id:int )`

Loads an entity into a stash.

### AddMaterialInventoryMaterial

`AddMaterialInventoryMaterial( entity_id:int, material_name:string )`

Adds a material to an entity's material inventory.

### RemoveMaterialInventoryMaterial

`RemoveMaterialInventoryMaterial( entity_id:int, material_name:string )`

Removes a material from an entity's material inventory.

### GetMaterialInventoryMainMaterial

`GetMaterialInventoryMainMaterial( entity_id:int ) -> material_name:string`

Retrieves the primary material from an entity's material inventory.

### GameScreenshake

`GameScreenshake( intensity:number, duration:number )`

Triggers a screen shake effect.

### GameOnCompleted

`GameOnCompleted()`

Triggers the game completion sequence.

### GameGiveAchievement

`GameGiveAchievement( achievement_id:string )`

Grants a specific achievement to the player.

### GameDoEnding2

`GameDoEnding2( ending_id:int )`

Initiates a specific game ending.

### GetParallelWorldPosition

`GetParallelWorldPosition( pos_x:number, pos_y:number ) -> parallel_x:number, parallel_y:number`

Gets the corresponding position in a parallel world.

### BiomeMapLoad\_KeepPlayer

`BiomeMapLoad_KeepPlayer( biome_map_filename:string )`

Loads a biome map while keeping the player's current position.

### GameIsIntroPlaying

`GameIsIntroPlaying() -> bool`

Checks if the game's intro sequence is currently playing.

### GameGetIsGamepadConnected

`GameGetIsGamepadConnected() -> bool`

Checks if a gamepad is connected.

### GameGetWorldStateEntity

`GameGetWorldStateEntity() -> entity_id:int`

Retrieves the entity representing the game's world state.

### GameGetPlayerStatsEntity

`GameGetPlayerStatsEntity() -> entity_id:int`

Retrieves the entity containing player statistics.

### GameGetOrbCountAllTime

`GameGetOrbCountAllTime() -> count:int`

Returns the total number of orbs collected throughout all runs.

### GameGetOrbCountThisRun

`GameGetOrbCountThisRun() -> count:int`

Returns the number of orbs collected in the current run.

### GameGetOrbCollectedThisRun

`GameGetOrbCollectedThisRun() -> count:int`

Returns the number of orbs collected in the current run (synonym for `GameGetOrbCountThisRun`).

### GameGetOrbCollectedAllTime

`GameGetOrbCollectedAllTime() -> count:int`

Returns the total number of orbs collected throughout all runs (synonym for `GameGetOrbCountAllTime`).

### GameClearOrbsFoundThisRun

`GameClearOrbsFoundThisRun()`

Resets the count of orbs found in the current run.

### GameGetOrbCountTotal

`GameGetOrbCountTotal() -> count:int`

Returns the total number of orbs available in the game.

### CellFactory\_GetName

`CellFactory_GetName( cell_id:int ) -> name:string`

Gets the name of a cell type.

### CellFactory\_GetType

`CellFactory_GetType( cell_id:int ) -> type:string`

Gets the type of a cell (e.g., "LIQUID", "SOLID").

### CellFactory\_GetUIName

`CellFactory_GetUIName( cell_id:int ) -> ui_name:string`

Gets the user-interface name of a cell type.

### CellFactory\_GetAllLiquids

`CellFactory_GetAllLiquids() -> table`

Returns a list of all liquid cell IDs.

### CellFactory\_GetAllSands

`CellFactory_GetAllSands() -> table`

Returns a list of all sand cell IDs.

### CellFactory\_GetAllGases

`CellFactory_GetAllGases() -> table`

Returns a list of all gas cell IDs.

### CellFactory\_GetAllFires

`CellFactory_GetAllFires() -> table`

Returns a list of all fire cell IDs.

### CellFactory\_GetAllSolids

`CellFactory_GetAllSolids() -> table`

Returns a list of all solid cell IDs.

### CellFactory\_HasTag

`CellFactory_HasTag( cell_id:int, tag:string ) -> bool`

Checks if a cell type has a specific tag.

### CellFactory\_GetTags

`CellFactory_GetTags( cell_id:int ) -> table`

Returns a list of all tags associated with a cell type.

### GameGetCameraPos

`GameGetCameraPos() -> x:number, y:number`

Retrieves the current camera position.

### GameSetCameraPos

`GameSetCameraPos( x:number, y:number )`

Sets the camera's position.

### GameSetCameraFree

`GameSetCameraFree( enabled:bool )`

Enables or disables free camera movement.

### GameGetCameraBounds

`GameGetCameraBounds() -> x1:number, y1:number, x2:number, y2:number`

Retrieves the boundaries of the camera's view.

### GameRegenItemAction

`GameRegenItemAction( item_entity_id:int )`

Regenerates the actions for a specific inventory item.

### GameRegenItemActionsInContainer

`GameRegenItemActionsInContainer( container_entity_id:int )`

Regenerates actions for all items within a container.

### GameRegenItemActionsInPlayer

`GameRegenItemActionsInPlayer( player_entity_id:int )`

Regenerates actions for all items held by the player.

### GameKillInventoryItem

`GameKillInventoryItem( item_entity_id:int )`

Destroys a specific inventory item.

### GamePickUpInventoryItem

`GamePickUpInventoryItem( item_entity_id:int )`

Simulates the player picking up an inventory item.

### GameGetAllInventoryItems

`GameGetAllInventoryItems() -> table`

Retrieves a list of all inventory items in the game.

### GameDropAllItems

`GameDropAllItems()`

Drops all inventory items held by the player.

### GameDropPlayerInventoryItems

`GameDropPlayerInventoryItems( player_entity_id:int )`

Drops all inventory items held by a specific player.

### GameDestroyInventoryItems

`GameDestroyInventoryItems( player_entity_id:int )`

Destroys all inventory items held by a specific player.

### GameIsInventoryOpen

`GameIsInventoryOpen() -> bool`

Checks if the player's inventory is currently open.

### GameTriggerGameOver

`GameTriggerGameOver()`

Initiates the game over sequence.

### LoadPixelScene

`LoadPixelScene( filename:string, pos_x:number, pos_y:number )`

Loads a pixel scene at a specified location.

### LoadBackgroundSprite

`LoadBackgroundSprite( filename:string, pos_x:number, pos_y:number, layer:number )`

Loads a background sprite.

### RemovePixelSceneBackgroundSprite

`RemovePixelSceneBackgroundSprite( sprite_entity_id:int )`

Removes a specific background sprite.

### RemovePixelSceneBackgroundSprites

`RemovePixelSceneBackgroundSprites( pixel_scene_entity_id:int )`

Removes all background sprites associated with a pixel scene.

### GameCreateCosmeticParticle

`GameCreateCosmeticParticle( particle_filename:string, pos_x:number, pos_y:number )`

Creates a cosmetic particle effect.

### GameCreateCosmeticParticle\_2

`GameCreateCosmeticParticle( particle_filename:string, pos_x:number, pos_y:number, scale:number )`

Creates a cosmetic particle effect with a specified scale.

### GameCreateParticle

`GameCreateParticle( particle_filename:string, pos_x:number, pos_y:number )`

Creates a general particle effect.

### GameCreateSpriteForXFrames

`GameCreateSpriteForXFrames( sprite_filename:string, num_frames:int, pos_x:number, pos_y:number )`

Creates a sprite entity that animates through a specified number of frames.

### GameShootProjectile

`GameShootProjectile( projectile_filename:string, pos_x:number, pos_y:number, velocity_x:number, velocity_y:number, owner_entity_id:int )`

Fires a projectile from a specified position with a given velocity.

### EntityInflictDamage

`EntityInflictDamage( entity_id:int, damage:number, damage_type:string, instigator_entity_id:int )`

Inflicts damage on an entity.

### EntityIngestMaterial

`EntityIngestMaterial( entity_id:int, material_name:string )`

Causes an entity to ingest a specific material.

### EntityRemoveIngestionStatusEffect

`EntityRemoveIngestionStatusEffect( entity_id:int, status_effect_name:string )`

Removes a status effect related to material ingestion from an entity.

### EntityAddRandomStains

`EntityAddRandomStains( entity_id:int, num_stains:int )`

Adds random stains to an entity.

### EntitySetDamageFromMaterial

`EntitySetDamageFromMaterial( entity_id:int, material_name:string )`

Sets the damage an entity takes from a specific material.

### EntityRefreshSprite

`EntityRefreshSprite( entity_id:int )`

Refreshes the sprite of an entity.

### EntityGetWandCapacity

`EntityGetWandCapacity( entity_id:int ) -> capacity:int`

Retrieves the wand capacity of an entity.

### GamePlayAnimation

`GamePlayAnimation( animation_name:string, entity_id:int, pos_x:number, pos_y:number )`

Plays an animation on an entity.

### GameGetVelocityCompVelocity

`GameGetVelocityCompVelocity( entity_id:int ) -> velocity_x:number, velocity_y:number`

Retrieves the velocity from an entity's velocity component.

### GameGetGameEffect

`GameGetGameEffect( effect_name:string ) -> effect_id:int`

Retrieves the ID of a game effect by its name.

### GameGetGameEffectCount

`GameGetGameEffectCount() -> count:int`

Returns the total number of game effects.

### LoadGameEffectEntityTo

`LoadGameEffectEntityTo( effect_id:int, entity_id:int )`

Applies a game effect to an entity.

### GetGameEffectLoadTo

`GetGameEffectLoadTo( entity_id:int ) -> effect_id:int`

Retrieves the game effect applied to an entity.

### SetPlayerSpawnLocation

`SetPlayerSpawnLocation( pos_x:number, pos_y:number )`

Sets the player's spawn location.

### UnlockItem

`UnlockItem( item_id:string )`

Unlocks a specific item for the player.

### GameGetPotionColorUint

`GameGetPotionColorUint( potion_entity_id:int ) -> color_uint:int`

Retrieves the uint representation of a potion's color.

### EntityGetFirstHitboxCenter

`EntityGetFirstHitboxCenter( entity_id:int ) -> center_x:number, center_y:number`

Retrieves the center coordinates of an entity's first hitbox.

### Raytrace

`Raytrace( x1:number, y1:number, x2:number, y2:number ) -> hit_x:number, hit_y:number, entity_id:int, material_id:int`

Performs a raycast to detect collisions with the world.

### RaytraceSurfaces

`RaytraceSurfaces( x1:number, y1:number, x2:number, y2:number ) -> hit_x:number, hit_y:number, entity_id:int, material_id:int`

Performs a raycast that specifically detects collisions with world surfaces.

### RaytraceSurfacesAndLiquiform

`RaytraceSurfacesAndLiquiform( x1:number, y1:number, x2:number, y2:number ) -> hit_x:number, hit_y:number, entity_id:int, material_id:int`

Performs a raycast that detects collisions with surfaces and liquiform materials.

### RaytracePlatforms

`RaytracePlatforms( x1:number, y1:number, x2:number, y2:number ) -> hit_x:number, hit_y:number, entity_id:int, material_id:int`

Performs a raycast that detects collisions with platforms.

### FindFreePositionForBody

`FindFreePositionForBody( x:number, y:number, radius:number ) -> free_x:number, free_y:number`

Finds a free position for a circular body within a given radius.

### GetSurfaceNormal

`GetSurfaceNormal( x:number, y:number ) -> normal_x:number, normal_y:number`

Retrieves the surface normal at a given point.

### DoesWorldExistAt

`DoesWorldExistAt( x:number, y:number ) -> bool`

Checks if the world exists at a given coordinate.

### StringToHerdId

`StringToHerdId( herd_name:string ) -> herd_id:int`

Converts a herd name string to its corresponding ID.

### HerdIdToString

`HerdIdToString( herd_id:int ) -> herd_name:string`

Converts a herd ID to its corresponding name string.

### GetHerdRelation

`GetHerdRelation( herd_id1:int, herd_id2:int ) -> relation:number`

Gets the relationship value between two herds.

### EntityGetHerdRelation

`EntityGetHerdRelation( entity_id:int, target_entity_id:int ) -> relation:number`

Gets the herd relationship between two entities.

### EntityGetHerdRelationSafe

`EntityGetHerdRelationSafe( entity_id:int, target_entity_id:int ) -> relation:number`

Safely gets the herd relationship between two entities, returning 0 if either entity is invalid.

### PolymorphTableAddEntity

`PolymorphTableAddEntity( entity_id:int )`

Adds an entity to the polymorph table.

### PolymorphTableRemoveEntity

`PolymorphTableRemoveEntity( entity_id:int )`

Removes an entity from the polymorph table.

### PolymorphTableGet

`PolymorphTableGet( entity_id:int ) -> polymorphed_entity_id:int`

Retrieves the entity that another entity has polymorphed into.

### PolymorphTableSet

`PolymorphTableSet( entity_id:int, polymorphed_entity_id:int )`

Sets the polymorphed entity for a given entity.

### EntityGetClosestWormAttractor

`EntityGetClosestWormAttractor( entity_id:int ) -> attractor_entity_id:int`

Finds the closest worm attractor entity to a given entity.

### EntityGetClosestWormDetractor

`EntityGetClosestWormDetractor( entity_id:int ) -> detractor_entity_id:int`

Finds the closest worm detractor entity to a given entity.

### GamePrint

`GamePrint( message:string )`

Prints a message to the game console.

### GamePrintImportant

`GamePrintImportant( message:string )`

Prints an important message to the game console, often highlighted.

### DEBUG\_GetMouseWorld

`DEBUG_GetMouseWorld() -> mouse_x:number, mouse_y:number`

Gets the world coordinates of the mouse cursor.

### DEBUG\_MARK

`DEBUG_MARK( x:number, y:number, r:number, g:number, b:number, a:number )`

Draws a debug marker at a specified position with a given color.

### GameGetFrameNum

`GameGetFrameNum() -> frame_number:int`

Returns the current game frame number.

### GameGetRealWorldTimeSinceStarted

`GameGetRealWorldTimeSinceStarted() -> time_seconds:number`

Returns the real-world time elapsed since the game started, in seconds.

### InputIsKeyDown

`InputIsKeyDown( key_code:string ) -> bool`

Checks if a specific key is currently held down.

### InputIsKeyJustDown

`InputIsKeyJustDown( key_code:string ) -> bool`

Checks if a specific key was just pressed down in this frame.

### InputIsKeyJustUp

`InputIsKeyJustUp( key_code:string ) -> bool`

Checks if a specific key was just released in this frame.

### InputGetMousePosOnScreen

`InputGetMousePosOnScreen() -> mouse_x:number, mouse_y:number`

Gets the mouse position relative to the screen.

### InputIsMouseButtonDown

`InputIsMouseButtonDown( button_id:int ) -> bool`

Checks if a specific mouse button is currently held down (0: Left, 1: Right, 2: Middle).

### InputIsMouseButtonJustDown

`InputIsMouseButtonJustDown( button_id:int ) -> bool`

Checks if a specific mouse button was just pressed down in this frame.

### InputIsMouseButtonJustUp

`InputIsMouseButtonJustUp( button_id:int ) -> bool`

Checks if a specific mouse button was just released in this frame.

### IsPlayer

`IsPlayer( entity_id:int ) -> bool`

Checks if an entity is a player character.

### IsInvisible

`IsInvisible( entity_id:int ) -> bool`

Checks if an entity is currently invisible.

### GameIsDailyRun

`GameIsDailyRun() -> bool`

Checks if the current run is a daily run.

### GameIsDailyRunOrDailyPracticeRun

`GameIsDailyRunOrDailyPracticeRun() -> bool`

Checks if the current run is a daily run or a daily practice run.

### GameIsModeFullyDeterministic

`GameIsModeFullyDeterministic() -> bool`

Checks if the current game mode is fully deterministic.

### GlobalsSetValue

`GlobalsSetValue( key:string, value )`

Sets a global variable.

### GlobalsGetValue

`GlobalsGetValue( key:string ) -> value`

Retrieves a global variable.

### MagicNumbersGetValue

`MagicNumbersGetValue( key:string ) -> value`

Retrieves a value from the game's magic numbers.

### SetWorldSeed

`SetWorldSeed( seed:number )`

Sets the world seed for the current game session.

### SessionNumbersGetValue

`SessionNumbersGetValue( key:string ) -> value`

Retrieves a value from session-specific numbers.

### SessionNumbersSetValue

`SessionNumbersSetValue( key:string, value )`

Sets a value for session-specific numbers.

### SessionNumbersSave

`SessionNumbersSave()`

Saves the current session numbers.

### AutosaveDisable

`AutosaveDisable()`

Disables autosaving.

### StatsGetValue

`StatsGetValue( stat_name:string ) -> value`

Retrieves a player statistic.

### StatsGlobalGetValue

`StatsGlobalGetValue( stat_name:string ) -> value`

Retrieves a global player statistic.

### StatsBiomeGetValue

`StatsBiomeGetValue( biome_name:string, stat_name:string ) -> value`

Retrieves a statistic specific to a biome.

### StatsBiomeReset

`StatsBiomeReset( biome_name:string )`

Resets statistics for a specific biome.

### StatsLogPlayerKill

`StatsLogPlayerKill( killer_entity_id:int, victim_entity_id:int )`

Logs a player kill event for statistics.

### CreateItemActionEntity

`CreateItemActionEntity( item_action_filename:string, pos_x:number, pos_y:number ) -> entity_id:int`

Creates an entity representing an item action.

### GetRandomActionWithType

`GetRandomActionWithType( action_type:string ) -> action_filename:string`

Gets a random action filename of a specified type.

### GetRandomAction

`GetRandomAction() -> action_filename:string`

Gets a random action filename.

### GameGetDateAndTimeUTC

`GameGetDateAndTimeUTC() -> year:int, month:int, day:int, hour:int, minute:int, second:int`

Gets the current date and time in UTC.

### GameGetDateAndTimeLocal

`GameGetDateAndTimeLocal() -> year:int, month:int, day:int, hour:int, minute:int, second:int`

Gets the current date and time in the local timezone.

### GameEmitRainParticles

`GameEmitRainParticles( pos_x:number, pos_y:number, count:int )`

Emits rain particles at a specified location.

### GameCutThroughWorldVertical

`GameCutThroughWorldVertical( x:number, y:number, height:number )`

Creates a vertical cut through the world at a given position.

### BiomeMapGetVerticalPositionInsideBiome

`BiomeMapGetVerticalPositionInsideBiome( biome_map_filename:string, x:number, y:number ) -> vertical_pos:number`

Gets the vertical position within a biome map at a given coordinate.

### BiomeMapGetName

`BiomeMapGetName( biome_map_entity_id:int ) -> biome_name:string`

Gets the name of a biome map entity.

### SetRandomSeed

`SetRandomSeed( seed:number )`

Sets the seed for the random number generator.

### Random

`Random( min:number, max:number ) -> random_number:number`

Generates a random integer between min and max (inclusive).

### Randomf

`Randomf( min:number, max:number ) -> random_number:number`

Generates a random float between min and max.

### RandomDistribution

`RandomDistribution( distribution_table:table ) -> random_value`

Generates a random value based on a probability distribution table.

### RandomDistributionf

`RandomDistributionf( distribution_table:table ) -> random_value`

Generates a random float based on a probability distribution table.

### ProceduralRandom

`ProceduralRandom( min:number, max:number ) -> random_number:number`

Generates a random number using a procedural generator.

### ProceduralRandomf

`ProceduralRandomf( min:number, max:number ) -> random_number:number`

Generates a random float using a procedural generator.

### ProceduralRandomi

`ProceduralRandomi( min:int, max:int ) -> random_number:int`

Generates a random integer using a procedural generator.

### PhysicsAddBodyImage

`PhysicsAddBodyImage( entity_id:int, image_filename:string, density:number, friction:number, restitution:number )`

Adds a physics body to an entity based on an image.

### PhysicsAddBodyCreateBox

`PhysicsAddBodyCreateBox( entity_id:int, width:number, height:number, density:number, friction:number, restitution:number )`

Adds a rectangular physics body to an entity.

### PhysicsAddJoint

`PhysicsAddJoint( joint_type:string, entity1_id:int, entity2_id:int, anchor1_x:number, anchor1_y:number, anchor2_x:number, anchor2_y:number )`

Adds a physics joint between two entities.

### PhysicsApplyForce

`PhysicsApplyForce( entity_id:int, force_x:number, force_y:number )`

Applies a force to an entity's physics body.

### PhysicsApplyTorque

`PhysicsApplyTorque( entity_id:int, torque:number )`

Applies torque to an entity's physics body.

### PhysicsApplyTorqueToComponent

`PhysicsApplyTorqueToComponent( component_id:int, torque:number )`

Applies torque to a specific physics component.

### PhysicsApplyForceOnArea

`PhysicsApplyForceOnArea( x1:number, y1:number, x2:number, y2:number, force_x:number, force_y:number )`

Applies force to all physics bodies within a specified area.

### PhysicsRemoveJoints

`PhysicsRemoveJoints( entity_id:int )`

Removes all physics joints connected to an entity.

### PhysicsSetStatic

`PhysicsSetStatic( entity_id:int, is_static:bool )`

Sets an entity's physics body to be static or dynamic.

### PhysicsGetComponentVelocity

`PhysicsGetComponentVelocity( component_id:int ) -> velocity_x:number, velocity_y:number`

Retrieves the velocity of a physics component.

### PhysicsGetComponentAngularVelocity

`PhysicsGetComponentAngularVelocity( component_id:int ) -> angular_velocity:number`

Retrieves the angular velocity of a physics component.

### PhysicsBody2InitFromComponents

`PhysicsBody2InitFromComponents( entity_id:int )`

Initializes a physics body from an entity's components.

### PhysicsVecToGameVec

`PhysicsVecToGameVec( physics_x:number, physics_y:number ) -> game_x:number, game_y:number`

Converts physics coordinates to game coordinates.

### GameVecToPhysicsVec

`GameVecToPhysicsVec( game_x:number, game_y:number ) -> physics_x:number, physics_y:number`

Converts game coordinates to physics coordinates.

### LooseChunk

`LooseChunk( entity_id:int, material_name:string, amount:number )`

Causes an entity to shed a specified amount of a material.

### AddFlagPersistent

`AddFlagPersistent( flag_name:string )`

Adds a persistent flag to the game state.

### RemoveFlagPersistent

`RemoveFlagPersistent( flag_name:string )`

Removes a persistent flag from the game state.

### HasFlagPersistent

`HasFlagPersistent( flag_name:string ) -> bool`

Checks if a persistent flag is set.

### GameAddFlagRun

`GameAddFlagRun( flag_name:string )`

Adds a flag that is active only for the current run.

### GameRemoveFlagRun

`GameRemoveFlagRun( flag_name:string )`

Removes a run-specific flag.

### GameHasFlagRun

`GameHasFlagRun( flag_name:string ) -> bool`

Checks if a run-specific flag is set.

### GameTriggerMusicEvent

`GameTriggerMusicEvent( event_name:string )`

Triggers a music event.

### GameTriggerMusicCue

`GameTriggerMusicCue( cue_name:string )`

Triggers a specific music cue.

### GameTriggerMusicFadeOutAndDequeueAll

`GameTriggerMusicFadeOutAndDequeueAll()`

Fades out all currently playing music and clears the queue.

### GamePlaySound

`GamePlaySound( sound_name:string, volume:number )`

Plays a sound effect.

### GameEntityPlaySound

`GameEntityPlaySound( entity_id:int, sound_name:string, volume:number )`

Plays a sound effect associated with an entity.

### GameEntityPlaySoundLoop

`GameEntityPlaySoundLoop( entity_id:int, sound_name:string, volume:number )`

Plays a looping sound effect associated with an entity.

### GameSetPostFxParameter

`GameSetPostFxParameter( parameter_name:string, value:number )`

Sets a parameter for a post-processing effect.

### GameUnsetPostFxParameter

`GameUnsetPostFxParameter( parameter_name:string )`

Unsets a parameter for a post-processing effect.

### GameTextGetTranslatedOrNot

`GameTextGetTranslatedOrNot( text_id:string ) -> translated_text:string`

Retrieves translated text for a given text ID, or the ID itself if no translation is found.

### GameTextGet

`GameTextGet( text_id:string ) -> translated_text:string`

Retrieves translated text for a given text ID.

### GuiCreate

`GuiCreate() -> gui_id:int`

Creates a new GUI element.

### GuiDestroy

`GuiDestroy( gui_id:int )`

Destroys a GUI element.

### GuiStartFrame

`GuiStartFrame()`

Starts a new GUI frame.

### GuiOptionsAdd

`GuiOptionsAdd( option_name:string, option_value )`

Adds an option to the current GUI element.

### GuiOptionsRemove

`GuiOptionsRemove( option_name:string )`

Removes an option from the current GUI element.

### GuiOptionsClear

`GuiOptionsClear()`

Clears all options from the current GUI element.

### GuiOptionsAddForNextWidget

`GuiOptionsAddForNextWidget( option_name:string, option_value )`

Adds an option that will apply to the next GUI widget.

### GuiColorSetForNextWidget

`GuiColorSetForNextWidget( r:number, g:number, b:number, a:number )`

Sets the color for the next GUI widget.

### GuiZSet

`GuiZSet( z_value:number )`

Sets the Z-order for GUI elements.

### GuiZSetForNextWidget

`GuiZSetForNextWidget( z_value:number )`

Sets the Z-order for the next GUI widget.

### GuiIdPush

`GuiIdPush( id:number )`

Pushes an ID onto the GUI ID stack.

### GuiIdPushString

`GuiIdPushString( id_string:string )`

Pushes a string ID onto the GUI ID stack.

### GuiIdPop

`GuiIdPop()`

Pops an ID from the GUI ID stack.

### GuiAnimateBegin

`GuiAnimateBegin()`

Begins an animation sequence for GUI elements.

### GuiAnimateEnd

`GuiAnimateEnd()`

Ends an animation sequence.

### GuiAnimateAlphaFadeIn

`GuiAnimateAlphaFadeIn( duration:number )`

Starts an alpha fade-in animation for the next GUI widget.

### GuiAnimateScaleIn

`GuiAnimateScaleIn( duration:number )`

Starts a scale-in animation for the next GUI widget.

### GuiText

`GuiText( text:string ) -> bool`

Draws text in the GUI. Returns true if the text was clicked.

### GuiImage

`GuiImage( image_filename:string, width:number, height:number ) -> bool`

Draws an image in the GUI. Returns true if the image was clicked.

### GuiImageNinePiece

`GuiImageNinePiece( image_filename:string, width:number, height:number, left_border:number, right_border:number, top_border:number, bottom_border:number ) -> bool`

Draws a nine-piece sliced image in the GUI.

### GuiButton

`GuiButton( text:string ) -> bool`

Draws a button with text. Returns true if the button was clicked.

### GuiImageButton

`GuiImageButton( image_filename:string ) -> bool`

Draws a button with an image. Returns true if the button was clicked.

### GuiSlider

`GuiSlider( value:number, min_value:number, max_value:number ) -> new_value:number`

Draws a slider control. Returns the new value of the slider.

### GuiTextInput

`GuiTextInput( current_text:string ) -> new_text:string`

Draws a text input field. Returns the updated text.

### GuiBeginAutoBox

`GuiBeginAutoBox( width:number, height:number )`

Begins an auto-sizing box for GUI elements.

### GuiEndAutoBoxNinePiece

`GuiEndAutoBoxNinePiece( image_filename:string, left_border:number, right_border:number, top_border:number, bottom_border:number )`

Ends an auto-sizing box with a nine-piece sliced background.

### GuiTooltip

`GuiTooltip( text:string )`

Displays a tooltip for the current GUI element.

### GuiBeginScrollContainer

`GuiBeginScrollContainer( width:number, height:number ) -> scroll_y:number`

Begins a scrollable container. Returns the current scroll position.

### GuiEndScrollContainer()

Ends a scrollable container.

### GuiLayoutBeginHorizontal

`GuiLayoutBeginHorizontal()`

Begins a horizontal layout group for GUI elements.

### GuiLayoutBeginVertical

`GuiLayoutBeginVertical()`

Begins a vertical layout group for GUI elements.

### GuiLayoutAddHorizontalSpacing

`GuiLayoutAddHorizontalSpacing( spacing:number )`

Adds horizontal spacing to the current layout.

### GuiLayoutAddVerticalSpacing

`GuiLayoutAddVerticalSpacing( spacing:number )`

Adds vertical spacing to the current layout.

### GuiLayoutEnd()

Ends the current layout group.

### GuiLayoutBeginLayer

`GuiLayoutBeginLayer()`

Begins a new GUI layer.

### GuiLayoutEndLayer()

Ends the current GUI layer.

### GuiGetScreenDimensions

`GuiGetScreenDimensions() -> width:number, height:number`

Gets the dimensions of the game screen.

### GuiGetTextDimensions

`GuiGetTextDimensions( text:string ) -> width:number, height:number`

Gets the dimensions of a given text string.

### GuiGetImageDimensions

`GuiGetImageDimensions( image_filename:string ) -> width:number, height:number`

Gets the dimensions of an image file.

### GuiGetPreviousWidgetInfo

`GuiGetPreviousWidgetInfo() -> x:number, y:number, width:number, height:number, was_clicked:bool`

Retrieves information about the previously drawn GUI widget.

### GameIsBetaBuild

`GameIsBetaBuild() -> bool`

Checks if the game is running a beta build.

### DebugGetIsDevBuild

`DebugGetIsDevBuild() -> bool`

Checks if the game is running a developer build.

### DebugEnableTrailerMode

`DebugEnableTrailerMode()`

Enables trailer mode for debugging.

### GameGetIsTrailerModeEnabled

`GameGetIsTrailerModeEnabled() -> bool`

Checks if trailer mode is currently enabled.

### Debug\_SaveTestPlayer

`Debug_SaveTestPlayer()`

Saves the current player state for testing purposes.

### DebugBiomeMapGetFilename

`DebugBiomeMapGetFilename( biome_map_entity_id:int ) -> filename:string`

Gets the filename of a biome map entity.

### EntityConvertToMaterial

`EntityConvertToMaterial( entity_id:int, material_name:string )`

Converts an entity into a specified material.

### ConvertEverythingToGold

`ConvertEverythingToGold()`

Converts all world materials to gold.

### ConvertMaterialEverywhere

`ConvertMaterialEverywhere( from_material:string, to_material:string )`

Converts all instances of one material to another throughout the world.

### ConvertMaterialOnAreaInstantly

`ConvertMaterialOnAreaInstantly( x1:number, y1:number, x2:number, y2:number, from_material:string, to_material:string )`

Instantly converts materials within a specified area.

### LoadRagdoll

`LoadRagdoll( entity_id:int, ragdoll_filename:string )`

Loads a ragdoll for an entity.

### GetDailyPracticeRunSeed

`GetDailyPracticeRunSeed() -> seed:number`

Retrieves the seed for the current daily practice run.

### ModIsEnabled

`ModIsEnabled( mod_id:string ) -> bool`

Checks if a specific mod is enabled.

### ModGetActiveModIDs

`ModGetActiveModIDs() -> table`

Retrieves a list of IDs for all currently active mods.

### ModGetAPIVersion

`ModGetAPIVersion() -> version:int`

Retrieves the current modding API version.

### ModSettingGet

`ModSettingGet( setting_name:string ) -> value`

Retrieves the value of a mod setting.

### ModSettingSet

`ModSettingSet( setting_name:string, value )`

Sets the value of a mod setting.

### ModSettingGetNextValue

`ModSettingGetNextValue( setting_name:string ) -> value`

Retrieves the next value for a mod setting (used for cycling through options).

### ModSettingSetNextValue

`ModSettingSetNextValue( setting_name:string, value )`

Sets the next value for a mod setting.

### ModSettingRemove

`ModSettingRemove( setting_name:string )`

Removes a mod setting.

### ModSettingGetCount

`ModSettingGetCount() -> count:int`

Retrieves the total number of mod settings.

### ModSettingGetAtIndex

`ModSettingGetAtIndex( index:int ) -> setting_name:string`

Retrieves the name of a mod setting at a specific index.

### StreamingGetIsConnected

`StreamingGetIsConnected() -> bool`

Checks if the game is connected to a streaming service.

### StreamingGetConnectedChannelName

`StreamingGetConnectedChannelName() -> channel_name:string`

Retrieves the name of the connected streaming channel.

### StreamingGetVotingCycleDurationFrames

`StreamingGetVotingCycleDurationFrames() -> duration_frames:int`

Gets the duration of a voting cycle in frames.

### StreamingGetRandomViewerName

`StreamingGetRandomViewerName() -> viewer_name:string`

Retrieves a random viewer name from the connected stream.

### StreamingGetSettingsGhostsNamedAfterViewers

`StreamingGetSettingsGhostsNamedAfterViewers() -> bool`

Checks if ghosts are named after viewers according to streaming settings.

### StreamingSetCustomPhaseDurations

`StreamingSetCustomPhaseDurations( phase_durations:table )`

Sets custom durations for streaming phases.

### StreamingForceNewVoting

`StreamingForceNewVoting()`

Forces a new voting session to start.

### StreamingSetVotingEnabled

`StreamingSetVotingEnabled( enabled:bool )`

Enables or disables voting for streaming events.

### SetValueNumber

`SetValueNumber( key:string, value:number )`

Sets a numerical value associated with a key.

### GetValueNumber

`GetValueNumber( key:string ) -> value:number`

Retrieves a numerical value associated with a key.

### SetValueInteger

`SetValueInteger( key:string, value:int )`

Sets an integer value associated with a key.

### GetValueInteger

`GetValueInteger( key:string ) -> value:int`

Retrieves an integer value associated with a key.

### SetValueBool

`SetValueBool( key:string, value:bool )`

Sets a boolean value associated with a key.

### GetValueBool

`GetValueBool( key:string ) -> value:bool`

Retrieves a boolean value associated with a key.

## Available only inside a custom BIOME\_MAP

These functions are specifically designed for use within custom biome map scripts.

### BiomeMapSetSize

`BiomeMapSetSize( width:int, height:int )`

Sets the dimensions of the biome map.

### BiomeMapGetSize

`BiomeMapGetSize() -> width:int, height:int`

Retrieves the dimensions of the biome map.

### BiomeMapSetPixel

`BiomeMapSetPixel( x:int, y:int, pixel_value:int )`

Sets the pixel value at a specific coordinate in the biome map.

### BiomeMapGetPixel

`BiomeMapGetPixel( x:int, y:int ) -> pixel_value:int`

Retrieves the pixel value at a specific coordinate in the biome map.

### BiomeMapConvertPixelFromUintToInt

`BiomeMapConvertPixelFromUintToInt( uint_pixel:int ) -> int_pixel:int`

Converts a uint pixel value to an int pixel value.

### BiomeMapLoadImage

`BiomeMapLoadImage( image_filename:string )`

Loads an image to be used as a biome map.

### BiomeMapLoadImageCropped

`BiomeMapLoadImageCropped( image_filename:string, x:int, y:int, width:int, height:int )`

Loads a cropped portion of an image to be used as a biome map.

## Available only during mod initialization

These functions are intended for use during the mod initialization phase.

### ModLuaFileAppend

`ModLuaFileAppend( filename:string )`

Appends the content of a Lua file to the current mod's script.

#### Function Detours

This section likely refers to advanced techniques for intercepting and modifying function calls during initialization, often used for patching or extending existing game functions. Specific details would require further context or documentation.

### ModTextFileGetContent

`ModTextFileGetContent( filename:string ) -> content:string`

Retrieves the content of a text file within the mod's assets.

### ModTextFileSetContent

`ModTextFileSetContent( filename:string, content:string )`

Sets the content of a text file within the mod's assets.

### ModTextFileWhoSetContent

`ModTextFileWhoSetContent( filename:string, content:string )`

Similar to `ModTextFileSetContent`, but may have different implications for file handling or mod loading order.

### ModMagicNumbersFileAdd

`ModMagicNumbersFileAdd( filename:string )`

Adds a custom magic numbers file for the mod.

### ModMaterialsFileAdd

`ModMaterialsFileAdd( filename:string )`

Adds a custom materials file for the mod.

### ModRegisterAudioEventMappings

`ModRegisterAudioEventMappings( mappings_filename:string )`

Registers custom audio event mappings for the mod.

### ModDevGenerateSpriteUVsForDirectory

`ModDevGenerateSpriteUVsForDirectory( directory_path:string )`

Generates sprite UV coordinates for all sprites in a given directory. This is typically a development tool.

### BiomeSetValue

`BiomeSetValue( biome_name:string, key:string, value )`

Sets a value for a specific biome property.

### BiomeGetValue

`BiomeGetValue( biome_name:string, key:string ) -> value`

Retrieves a value for a specific biome property.

### BiomeObjectSetValue

`BiomeObjectSetValue( biome_name:string, object_type:string, key:string, value )`

Sets a value for a specific property of a biome object type.

### BiomeVegetationSetValue

`BiomeVegetationSetValue( biome_name:string, vegetation_type:string, key:string, value )`

Sets a value for a specific property of a biome vegetation type.

### BiomeMaterialSetValue

`BiomeMaterialSetValue( biome_name:string, material_name:string, key:string, value )`

Sets a value for a specific property of a biome material.

### BiomeMaterialGetValue

`BiomeMaterialGetValue( biome_name:string, material_name:string, key:string ) -> value`

Retrieves a value for a specific property of a biome material.

## Available only in data/scripts/gun/gun.lua

These functions are specific to the `gun.lua` script, which handles weapon and projectile logic.

### RegisterProjectile

`RegisterProjectile( projectile_filename:string )`

Registers a custom projectile definition.

### RegisterGunAction

`RegisterGunAction( action_filename:string )`

Registers a custom gun action.

### RegisterGunShotEffects

`RegisterGunShotEffects( effects_filename:string )`

Registers custom shot effects for guns.

### BeginProjectile

`BeginProjectile( projectile_filename:string )`

Starts the definition of a projectile.

### EndProjectile()

Ends the definition of a projectile.

### BeginTriggerTimer

`BeginTriggerTimer( delay_frames:int )`

Starts a timer trigger for projectile behavior.

### BeginTriggerHitWorld

`BeginTriggerHitWorld()`

Starts a trigger that activates when the projectile hits the world.

### BeginTriggerDeath

`BeginTriggerDeath()`

Starts a trigger that activates when the projectile is destroyed.

### EndTrigger()

Ends the current trigger definition.

### SetProjectileConfigs

`SetProjectileConfigs( configs_table:table )`

Sets various configuration options for projectiles.

### StartReload

`StartReload()`

Initiates the reload sequence for a gun.

### ActionUsesRemainingChanged

`ActionUsesRemainingChanged( action_index:int, uses_remaining:int )`

Called when the number of uses remaining for a gun action changes.

### ActionUsed

`ActionUsed( action_index:int )`

Called when a gun action is used.

### LogAction

`LogAction( action_index:int )`

Logs the use of a gun action.

### OnActionPlayed

`OnActionPlayed( action_index:int )`

Called when a gun action is played.

### OnNotEnoughManaForAction

`OnNotEnoughManaForAction( action_index:int )`

Called when there is not enough mana to perform a gun action.

### BaabInstruction

`BaabInstruction( instruction_type:string, value )`

Executes a "Baab" instruction, likely related to AI or complex gun behaviors.

### ConfigGunActionInfo\_ReadToGame

`ConfigGunActionInfo_ReadToGame()`

Reads gun action information into the game's internal structures.

### Hooks

#### ConfigGun\_ReadToLua

`ConfigGun_ReadToLua()`

Reads gun configuration data into Lua.

#### ConfigGunActionInfo\_ReadToLua

`ConfigGunActionInfo_ReadToLua()`

Reads gun action information into Lua.

#### \_\_clear\_deck

`__clear_deck()`

Clears the gun's deck of actions.

#### \_\_add\_card\_to\_deck

`__add_card_to_deck( card_filename:string )`

Adds a card (action) to the gun's deck.

#### \_\_change\_action\_uses\_remaining

`__change_action_uses_remaining( action_index:int, new_uses:int )`

Changes the remaining uses for a specific gun action.

#### \_\_play\_permanent\_card

`__play_permanent_card( card_filename:string )`

Plays a permanent card action.

#### \_\_set\_gun

`__set_gun( gun_filename:string )`

Sets the current gun to a new definition.

#### \_\_set\_gun2

`__set_gun2( gun_filename:string )`

An alternative function for setting the current gun.

#### \_\_start\_shot

`__start_shot()`

Initiates the firing of a shot.

#### \_\_add\_extra\_modifier\_to\_shot

`__add_extra_modifier_to_shot( modifier_filename:string )`

Adds an extra modifier to the current shot.

#### \_\_draw\_actions\_for\_shot

`__draw_actions_for_shot()`

Draws the available actions for the current shot.

#### \_\_handle\_reload

`__handle_reload()`

Handles the reload process for the gun.

## Available only in data/scripts/gun/gun\_collect\_metadata.lua

This script is used for collecting metadata about guns and projectiles.

### RegisterGunAction

`RegisterGunAction( action_filename:string )`

Registers a gun action for metadata collection.

### Reflection\_RegisterProjectile

`Reflection_RegisterProjectile( projectile_filename:string )`

Registers a projectile for reflection-based metadata collection.

## Available only in data/scripts/status\_effects/status\_reflect.lua

This script is related to status effects and reflection mechanics.

### GameRegisterStatusEffect

`GameRegisterStatusEffect( status_effect_filename:string )`

Registers a custom status effect definition.

## Available only in data/scripts/perks/perk\_reflect.lua

This script is related to perks and their reflection mechanics.

### RegisterPerk

`RegisterPerk( perk_filename:string )`

Registers a custom perk definition.

## Available only in data/scripts/streaming\_integration/event\_list.lua

This script handles integration with streaming services and events.

### RegisterStreamingEvent

`RegisterStreamingEvent( event_filename:string )`

Registers a custom streaming event.

### Hooks

#### \_\_reflect

`__reflect()`

A hook likely related to reflecting or processing streaming events.

#### \_\_streaming\_on\_vote\_start

`__streaming_on_vote_start()`

Called when a streaming vote begins.

#### \_\_streaming\_get\_event\_for\_vote

`__streaming_get_event_for_vote( vote_data:table ) -> event_filename:string`

Determines which streaming event to run based on vote data.

#### \_\_streaming\_run\_event

`__streaming_run_event( event_filename:string )`

Executes a registered streaming event.

#### \_\_streaming\_on\_irc

`__streaming_on_irc( message:string )`

Called when an IRC message is received from the stream.

#### \_\_streaming\_set\_event\_enabled

`__streaming_set_event_enabled( event_filename:string, enabled:bool )`

Enables or disables a specific streaming event.

## Other/Unspecified

This section contains functions that may not fit neatly into other categories or have less clear usage contexts.

### Hooks

#### wake\_up\_waiting\_threads

`wake_up_waiting_threads()`

Wakes up any threads that are currently waiting.

#### \_\_\_\_cached\_func

`____cached_func( func:function ) -> cached_function:function`

Wraps a function to cache its results.

#### biome\_modifiers\_inject\_spawns

`biome_modifiers_inject_spawns( biome_modifier_filename:string )`

Injects spawns defined by a biome modifier.

## Available only in data/scripts/debug/generate\_lua\_documentation.lua

This script is used for generating Lua documentation, likely for internal use or advanced modding tools.

### \_\_\_main

`___main()`

The main function for the documentation generation script.

### in\_function\_signatures

`in_function_signatures( file_content:string ) -> function_signatures:table`

Extracts function signatures from Lua code.

### out\_html

`out_html( function_signatures:table )`

Outputs documentation in HTML format.

### out\_json

`out_json( function_signatures:table )`

Outputs documentation in JSON format.

## Deprecated

These functions are no longer recommended for use and may be removed in future versions.

### ComponentGetValue

`ComponentGetValue( component_id:int, key:string ) -> value`

**Deprecated**: Use `ComponentGetValue2` instead. Retrieves the value of a specific field within a component.

### ComponentSetValue

`ComponentSetValue( component_id:int, key:string, value )`

**Deprecated**: Use `ComponentSetValue2` instead. Sets the value of a specific field within a component.