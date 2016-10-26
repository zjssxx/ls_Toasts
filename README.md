## ls: Toasts
Replacement for default alert system. Better toasts, cheers!

![image](http://i.imgur.com/PvzX6VF.gif)

## Download
- [WoWInterface](http://www.wowinterface.com/downloads/info24123.html)
- [Curse](http://mods.curse.com/addons/wow/ls-toasts)

## Features
- One design for all toasts. Special alert frames have unique backgrounds;
- In-game config. Use **/lstoasts** command to open config panel. From there you can disable sounds, move alert frames, etc;
- DND mode. You can enable DND mode for different toast groups. Toasts in DND mode won't be displayed in combat, but will be queued up in the system. Once you leave combat, they'll start popping up. Available from in-game config;

## Usage
- Install it;
- _(Optional)_ Configure it;
- Done.

**Note #1:** By default, there's no ls: Toasts entry in Interface > AddOns section. You can create one by using **/lstoasts** command. It's a workaround for infamous CompactRaidFrame* taint, and few others. It's a really old Blizz bug, and I don't think it'll ever be fixed.

I strongly recommend to **/reload** UI after you're done setting up the addon. Even if you opened and closed config panel without changing anything, **/reload** UI. By doing so, you'll remove config entry from the system and prevent possible taints.

## How to Mod
If you're UI developer, you may want to reskin my toasts. To do so, you'll need to override special dummy function by adding something like this to your addon code:

```Lua
local toast_F = ls_Toasts[1]

function toast_F:SkinToast(toast, toastType)
	-- do something here
end
```

This function is called after colours, textures and texts are set, but before toast is shown. Toast and its type are passed as arguments.

For toasts' structures, see definitions of `CreateBaseToastButton` and `GetToast` functions.

You can also access addon's config. It's **the config** that is used by ls: Toasts, **not a copy** of it.

```Lua
local toast_C = ls_Toasts[2]

-- changes growth direction to "UP"
toast_C.growth_direction = "UP"
```

These changes will be saved to addon's variables.

For config's content see `DEFAULTS` table.

## Feedback and Feature Requests
If you found a bug or want to share an idea on how to improve my addon, either report to [Issue Tracker](https://github.com/ls-/ls_Toasts/issues) on my GitHub page, or post a comment on [WoWInterfrace](http://www.wowinterface.com/downloads/info24123.html#comments) or [Curse](http://mods.curse.com/addons/wow/ls-toasts#comments).

## FAQ
**Q:** Will you add group/master loot roll frames to your addon?<br/>
**A:** Maybe later, I'm not sure yet.

## License
Please see [LICENSE](https://github.com/ls-/ls_Toasts/blob/master/LICENSE.txt) file.
