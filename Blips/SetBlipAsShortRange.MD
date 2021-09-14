## SetBlipAsShortRange
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