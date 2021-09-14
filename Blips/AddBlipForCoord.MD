## AddBlipForCoord
This native allows you to place a blip on an exact co-ordinate in the world.

| Parameters  | Example     |
| ----------- | ----------- |
| X           | -58.0       |
| Y           | -488.0      |
| Z           | 40.0        |

***

**Code:**
```lua
local blip = AddBlipForCoord(-58.0, -488.0, 40.0)
```

**Result:**

![Blip Result](https://i.imgur.com/C7AdukT.jpg)

***

## Formatting
There are many different natives we can use to change the way the blip is displayed in-game.

### SetBlipAsShortRange
This native allows us to set the blip to only show on the minimap when the player is close enough to the blip.

| Parameters    | Example     |
| -----------   | ----------- |
| (Blip) Blip   | blip        |
| (Bool) Toggle | true        |

**Example:**

```lua
local blip = AddBlipForCoord(-58.0, -488.0, 40.0)
SetBlipAsShortRange(blip, true)
```

### SetBlipColour
This native allows us to set the colour of the blip of the map, this will have a different effect on different sprites.

| Parameters    | Example     |
| -----------   | ----------- |
| (Blip) Blip   | blip        |
| (Int) Colour  | 4           |

**Example:**

```lua
local blip = AddBlipForCoord(-58.0, -488.0, 40.0)
SetBlipColour(blip, 4)
```

You can find all of the colours here: https://docs.fivem.net/natives/?_0x03D7FB09E75D6B7E

### SetBlipRoute
This native allows us to set the route to this blip, this can be useful for commands.

| Parameters    | Example     |
| -----------   | ----------- |
| (Blip) Blip   | blip        |
| (Bool) Toggle | true        |

**Example:**

```lua
local blip = AddBlipForCoord(-58.0, -488.0, 40.0)
SetBlipRoute(blip, true)
```

### SetBlipRouteColour
This native allows us to set the colour of the route to the blip.

| Parameters    | Example     |
| -----------   | ----------- |
| (Blip) Blip   | blip        |
| (Int) Colour  | 4           |

**Example:**

```lua
local blip = AddBlipForCoord(-58.0, -488.0, 40.0)
SetBlipRouteColour(blip, 4)
```

You can find all of the colours here: https://docs.fivem.net/natives/?_0x03D7FB09E75D6B7E

***

## Efficient way for multiple blips
When creating many blips it is not efficient to constantly declare different variables for each blip, so we will use loops in this example.

**Code:**

```lua
local blips = {
    {name = "Police Station", x = -58.0, y = -488.0, z = 40.0, id = 60, colour = 3 },
    {name = "Police Station", x = -58.0, y = -488.0, z = 40.0, id = 60, colour = 3 },
    {name = "Police Station", x = -58.0, y = -488.0, z = 40.0, id = 60, colour = 3 }
}

Citizen.CreateThread(function()
    for blip, info in pairs(blips) do
        local blip = AddBlipForCoord(info.x, info.y, info.z)
        SetBlipSprite(blip, info.id)
        SetBlipColour(blip, info.colour)
        SetBlipAsShortRange(blip, true)
        BeginTextCommandSetBlipName("STRING")
        AddTextComponentString(info.name)
        EndTextCommandSetBlipName(blip)
    end
end)
```

**Result:**