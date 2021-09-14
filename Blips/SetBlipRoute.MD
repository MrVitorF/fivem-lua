## SetBlipRoute
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