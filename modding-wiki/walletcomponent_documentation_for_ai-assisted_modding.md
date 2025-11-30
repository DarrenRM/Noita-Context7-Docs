---
title: WalletComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:WalletComponent
category: modding-wiki
---

# WalletComponent Documentation for AI-Assisted Modding

This documentation details the `WalletComponent` in Noita, a crucial component for managing in-game currency. Understanding its properties and how to interact with it is essential for modders looking to implement custom economy systems, modify item prices, or create new ways for players to earn or spend gold.

## Understanding the WalletComponent

The `WalletComponent` is attached to entities that can hold and manage gold. It primarily governs the amount of gold an entity possesses and provides methods for interacting with that gold.

### Component Properties

The `WalletComponent` has the following key properties that can be accessed and modified via Lua scripting:

| Property Name | Type   | Description                                                                 |
| :------------ | :----- | :-------------------------------------------------------------------------- |
| `m_gold`      | `int`  | The current amount of gold the entity possesses.                            |
| `m_maxGold`   | `int`  | The maximum amount of gold the entity can hold. (Often set to a very high value or -1 for unlimited). |

### Component Methods

The `WalletComponent` provides several methods for programmatic interaction with an entity's gold. These are accessible through the entity's `WalletComponent` instance.

*   **`AddGold(amount)`**: Adds a specified amount of gold to the wallet.
    *   `amount`: The integer value of gold to add.
*   **`SpendGold(amount)`**: Attempts to remove a specified amount of gold from the wallet. Returns `true` if successful, `false` otherwise (if insufficient gold).
    *   `amount`: The integer value of gold to spend.
*   **`GetGold()`**: Returns the current amount of gold the entity possesses.
*   **`HasEnoughGold(amount)`**: Checks if the entity has at least the specified amount of gold. Returns `true` if sufficient, `false` otherwise.
    *   `amount`: The integer value of gold to check against.

## Modding Examples

Here are some common scenarios and how to implement them using the `WalletComponent`.

### Giving Gold to the Player

This example demonstrates how to add gold to the player's wallet when a specific item is picked up.

```lua
-- Assuming this script is attached to an item that, when picked up,
-- should give the player gold.
local function on_pickup(entity, item_entity)
    local player_wallet = EntityGetFirstComponent(item_entity, "WalletComponent")
    if player_wallet then
        -- Add 100 gold to the player
        player_wallet.AddGold(100)
        print("Player received 100 gold!")
    end
end

-- Register the pickup callback (this is a simplified example, actual registration
-- might involve specific component callbacks or event systems)
-- For instance, if this is a custom item, you might have a component that
-- triggers this function on pickup.
```

### Creating a Vendor that Buys Items

This example shows how to create a simple vendor entity that can buy items from the player.

```lua
-- This script would be attached to the vendor entity.
local vendor_entity = GetUpdatedEntityID(self) -- Assuming 'self' refers to the vendor entity

local function buy_item(player_entity, item_to_buy_entity)
    local player_wallet = EntityGetFirstComponent(player_entity, "WalletComponent")
    local vendor_wallet = EntityGetFirstComponent(vendor_entity, "WalletComponent")

    if not player_wallet or not vendor_wallet then
        print("Error: Wallet components not found for player or vendor.")
        return
    end

    -- Determine the buy price of the item (this would be more complex in a real mod)
    -- For simplicity, let's assume items have a 'buy_price' component or property.
    local item_price_component = EntityGetFirstComponent(item_to_buy_entity, "ItemPriceComponent") -- Hypothetical component
    local buy_price = 0
    if item_price_component then
        buy_price = item_price_component.m_buyPrice or 0 -- Assuming a 'm_buyPrice' property
    else
        -- Fallback or default price if no specific price component
        buy_price = 50
    end

    if vendor_wallet.HasEnoughGold(buy_price) then
        if vendor_wallet.SpendGold(buy_price) then
            player_wallet.AddGold(buy_price)
            -- Remove the item from the player's inventory and give it to the vendor
            EntityRemove(item_to_buy_entity)
            -- In a real scenario, you'd add the item to the vendor's inventory
            print("Vendor bought item for " .. buy_price .. " gold.")
        else
            print("Vendor does not have enough gold to buy this item.")
        end
    else
        print("Vendor does not have enough gold to buy this item.")
    end
end

-- This function would be called when the player interacts with the vendor
-- and chooses to sell an item. You would need to implement the UI and
-- interaction logic to call this function with the correct entities.
```

### Modifying Item Prices

You can modify the price of items by accessing their `ItemComponent` and potentially adding custom components or logic. While `WalletComponent` itself doesn't directly set item prices, it's the target for transactions. To modify prices, you'd typically interact with components that define an item's value.

For example, if an item has an `ItemComponent` with a `m_price` property, you could modify it:

```lua
-- Assuming 'item_entity' is the entity of the item you want to modify the price of.
local item_component = EntityGetFirstComponent(item_entity, "ItemComponent")
if item_component then
    -- Increase the price of the item by 50%
    item_component.m_price = item_component.m_price * 1.5
    print("Item price increased.")
end
```

## Further Modding Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity System](https://noita.wiki.gg/wiki/Modding:_Entity_System)
*   [Components](https://noita.wiki.gg/wiki/Modding:_Components)