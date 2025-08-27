# anes_interaction
a fivem stand alone simple interaction system

preview : 

<img width="982" height="486" alt="image" src="https://github.com/user-attachments/assets/c8a84801-68a9-4f76-890b-7d9dc266827d" />

vedio : https://r2.fivemanage.com/V45yEeMAc4OMtms5av8mY/Desktop2025.08.27-14.03.43.03.DVR.mp4



no support





Usage :

#
```lua
exports['anes_interaction']:AddInteraction({
    id = "crimeBoss",
    label = "Talk With The Boss",
    icon = "fa-user-secret", -- Font Awesome icon
    coords = vec3(395.41, -1484.57, 29.21),
    distance = 3.0,       -- distance to interact
    distancedot = 18.0,   -- distance to show floating dot
    options = {
        {
            actionlabel = "Open Menu",
            actionkey = "E",
            event = "myResource:openBossMenu", -- triggers client event
        },
        {
            actionlabel = "Custom Action",
            actionkey = "K",
            action = function(ped, coords, args)
                lib.notify({
                    title = 'Boss',
                    description = 'You triggered a custom function!',
                    type = 'success'
                })
            end,
        }
    }
})



exports['anes_interaction']:AddEntityInteraction({
    id = "bossPedEntity",
    entity = bossPed,
    label = "Speak With Boss",
    icon = "fa-comments",
    distance = 2.5,
    distancedot = 10.0,
    options = {
        {
            actionlabel = "Talk",
            actionkey = "E",
            action = function()
                lib.notify({ title = 'Boss', description = 'Talking...', type = 'info' })
            end
        },
        {
            actionlabel = "Slap",
            actionkey = "G",
            action = function()
                lib.notify({ title = 'Boss', description = 'You slapped the boss!', type = 'error' })
            end
        }
    }
})

exports['anes_interaction']:AddModelInteraction(
    `prop_atm_02`,            -- model hash
    "ATM Machine",            -- label
    "fa-piggy-bank",          -- icon
    {
        {
            actionlabel = "Use ATM",
            actionkey = "E",
            serverEvent = "banking:openATM" -- triggers server event
        }
    },
    2.0,  -- interact distance
    8.0   -- dot display distance
)


exports['anes_interaction']:RemoveInteraction("crimeBoss")

```

Controls

By default uses these keys:

E (38)

G (47)

H (74)

K (311)

Y, U, L, X, Z, F also supported

You define which key each option uses with actionkey.



