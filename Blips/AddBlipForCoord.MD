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

![Multiple blips](https://i.imgur.com/ULgFH5U.jpg)