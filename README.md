# Linora-Lib
The roblox lib, Linora with documentation! 
## Please star it if you enjoy all the documentation i make for random ui libs
> [!TIP]
> I recommend using my [gitbook](https://stratxgy.gitbook.io/linora-lib), as in my opinion it's better than this.

> [!IMPORTANT]  
> This is not mine. Find the real github [here](https://github.com/violin-suzutsuki/LinoriaLib)
>
> 
> ## Importing the library
```lua
local repo = 'https://raw.githubusercontent.com/violin-suzutsuki/LinoriaLib/main/'
local Library = loadstring(game:HttpGet(repo .. 'Library.lua'))()
local ThemeManager = loadstring(game:HttpGet(repo .. 'addons/ThemeManager.lua'))()
local SaveManager = loadstring(game:HttpGet(repo .. 'addons/SaveManager.lua'))()
```

## Creating a new window
```lua
local Window = Library:CreateWindow({
    Title = 'Example menu',
    Center = true, -- Set Center to true if you want the menu to appear in the center
    AutoShow = true, -- Set AutoShow to true if you want the menu to appear when it is created
    TabPadding = 8,
    MenuFadeTime = 0.2
    --Position = float (optional)
    --Size = float (optional)
})
```

## Creating tabs
```lua
local mainTab = Window:AddTab('Main')
```
#### CLICKABLES

## Creating Buttons
```lua
local MyButton = LeftGroupBox:AddButton({
    Text = 'Button',
    Func = function()
        print('You clicked a button!')
    end,
    DoubleClick = false,
    Tooltip = 'This is the main button' -- When you hover over the button this appears
})
```


## Creating a color picker
```lua
LeftGroupBox:AddLabel('Color'):AddColorPicker('ColorPicker', {
    Default = Color3.new(0, 1, 0), -- Bright green
    Title = 'Some color', -- Optional. Allows you to have a custom color picker title (when you open it)
    Transparency = 0, -- Optional. Enables transparency changing for this color picker (leave as nil to disable)

    Callback = function(Value)
        print('[cb] Color changed!', Value)
    end
})

Options.ColorPicker:OnChanged(function()
    print('Color changed!', Options.ColorPicker.Value)
    print('Transparency changed!', Options.ColorPicker.Transparency)
end)

Options.ColorPicker:SetValueRGB(Color3.fromRGB(0, 255, 140))
```

## Creating Toggles
```lua
LeftGroupBox:AddToggle('MyToggle', {
    Text = 'This is a toggle',
    Default = true, -- Default value (true / false)
    Tooltip = 'This is a tooltip', -- Information shown when you hover over the toggle

    Callback = function(Value)
        print('[cb] MyToggle changed to:', Value)
    end
})

MyToggle:OnChanged(function()
    -- here we get our toggle object & then get its value
    print('MyToggle changed to:', Toggles.MyToggle.Value)
end)
```


## Creating Sliders

```lua
LeftGroupBox:AddSlider('MySlider', {
    Text = 'This is my slider!',
    Default = 0,
    Min = 0,
    Max = 5,
    Rounding = 1,
    Compact = false,

    Callback = function(Value)
        print('[cb] MySlider was changed! New value:', Value)
    end
})

local Number = Options.MySlider.Value
MySlider:OnChanged(function()
    print('MySlider was changed! New value:', Options.MySlider.Value)
end)

MySlider:SetValue(3)
```
#### GROUPBOXES, LABELS, TABBOXES

## Creating GroupBoxes
```lua
local LeftGroupBox = Main:AddLeftGroupbox('Left Groupbox')
local RightGroupbox = Main:AddRightGroupbox('Right Groupbox');
```

## Creating TabBoxes
```lua
local RightTabBox = Main:AddRightTabbox()
local LeftTabBox = Main:AddLeftTabbox()
```

## Creating Labels
```lua
local Label = LeftGroupBox:AddLabel('This is a label')
--[[
Text = string
doesWrap = boolean (optional)
]]
```
