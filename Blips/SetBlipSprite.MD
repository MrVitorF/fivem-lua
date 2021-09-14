## SetBlipRoute
This native allows us to set the sprite on a blip, useful to allow for different types of markers on your map.

| Parameters    | Example     |
| -----------   | ----------- |
| (Blip) Blip   | blip        |
| (int) Sprite  | 60          |

**Example:**

```lua
local blip = AddBlipForCoord(-58.0, -488.0, 40.0)
SetBlipSprite(blip, 69)
```

You can find all of the sprites here: https://docs.fivem.net/docs/game-references/blips/