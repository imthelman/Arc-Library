# Arc Library
This documentation is for the Arc Library.  Arc Library is currently in beta.  Some fetures wont be avalible

## Installing the Library
```lua
local ArcLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/imthelman/Arc-Library/main/source')))()
```



## Creating a Window
```lua
local Window = ArcLib:MakeWindow({
    Title = 'Title of the UI',
    SubTitle = 'Subtitle of the UI',
    IntroEnabled = true
    IntroText = 'Arc Library'
})

--[[
Name = <string> - The name of the UI.
IntroEnabled = <bool> - Whether or not to show the intro animation.
IntroText = <string> - Text to show in the intro animation.
]]
```

### Updating a Window
```lua
Window:Update({
    Title = 'New Title',
    SubTitle = 'New SubTitle'
})
```

## Creating a Tab 
```lua
local Tab = Window:MakeTab({
	Name = "Tab 1"
})

--[[
Name = <string> - The name of the tab.
]]
```

### Updating a Tab
```lua
Tab:Update({Name = 'New Tab Name'})
```

## Notifying the user

Not avalible right now
```lua
ArcLib:Notification({
	Name = "Title!",
	Content = "Notification content... what will it say??",
	Time = 5
})

--[[
Title = <string> - The title of the notification.
Content = <string> - The content of the notification.
Time = <number> - The duration of the notfication.
]]
```



### Creating a Button
```lua
Tab:CreateButton({
	Name = "Button!",
	Callback = function()
      	    -- Your function
  	end    
})

--[[
Name = <string> - The name of the button.
Callback = <function> - The function of the button.
]]
```

### Updating an existing Button
```lua
Button:Update({
	Name = "New Button name",
	Callback = function()
	    -- Your function
	end    
})
```
You must set the button as a variable for this to work


## Creating a Toggle
```lua
Tab:CreateToggle({
	Name = "This is a toggle!",
	Default = false,
	Callback = function(Value)
	    -- Your function
	end    
})

--[[
Name = <string> - The name of the toggle.
Default = <bool> - The default value of the toggle.
Callback = <function> - The function of the toggle.
]]
```

### Updating an existing Toggle
```lua
Toggle:Update({
	Name = "This is a toggle!",
	Value = false,
	Callback = function(Value)
	    -- Your function
	end    
})
```
You must set the toggle as a variable for this to work


## Creating a Color Picker

Not avalible right now
```lua
Tab:CreateColorpicker({
	Name = "Colorpicker",
	Default = Color3.fromRGB(255, 0, 0),
	Callback = function(Value)
	    -- Your function
	end	  
})

--[[
Name = <string> - The name of the colorpicker.
Default = <color3> - The default value of the colorpicker.
Callback = <function> - The function of the colorpicker.
]]
```

### Updating an existing color picker
```lua
ColorPicker:Update({
    Name = 'New Color Picker Name',
    Color = Color3.fromRGB(255,255,255)
    Callback = function(Value)
        -- Your function
    end
})
```
You must set the button as a variable for this to work

## Creating a Slider
```lua
Tab:CreateSlider({
	Name = "Slider",
	Min = 0,
	Max = 20,
	Default = 5,
	Color = Color3.fromRGB(255,255,255),
	Increment = 1,
	Callback = function(Value)
	    -- Your function
	end    
})

--[[
Name = <string> - The name of the slider.
Min = <number> - The minimal value of the slider.
Max = <number> - The maxium value of the slider.
Increment = <number> - How much the slider will change value when dragging.
Default = <number> - The default value of the slider.
Callback = <function> - The function of the slider.
]]
```

### Updating an existing Slider
```lua
Slider:Update({
    Name = "New Slider name",
    Min = 0
    Max = 10
    Increment = 1
    Value = 5
    CallBack = function(Value)
	-- Your function
    end    
})
```
You must set the slider as a variable for this to work


## Creating a Label
```lua
Tab:CreateLabel({Name = 'Label'})
```

### Updating an existing label
```lua
Label:Update({Name = 'New Label Name'})
```
You must set the label as a variable for this to work

## Creating a Paragraph
```lua
Tab:CreateParagraph({
    Name = "Paragraph",
    Text = "Paragraph Content"
})
```

### Updating an existing Paragraph
```lua
Paragraph:Update({
    Name = "Paragraph New!",
    Text = "New Paragraph Content!"
})
```
You must set the paragraph as a variable for this to work

## Creating an Adaptive Input
```lua
Tab:CreateInput({
	Name = "Textbox",
	PlaceHolderText = "place holder text",
	RemoveTextAfterFocusLost = false,
	Callback = function(Value)
	    -- Your function
	end	  
})

--[[
Name = <string> - The name of the textbox.
PlaceHolderText = <string> - The placeholder text of the textbox.
RemoveTextAfterFocusLost = <bool> - Makes the text disappear in the textbox after losing focus.
Callback = <function> - The function of the textbox.
]]
```


## Creating a Keybind
```lua
Window:CreateKeybind({
	Key = 'E',
	Callback = function()
	    -- Your function
	end    
})

--[[
Key = <keycode> - The default value of the bind.
Callback = <function> - The function of the bind.
]]
```

### Updating an excisting Keybind
```lua
Keybind:Update({
    Key = 'Q',
    Callback = function()
        -- Your function
    end
})
```

## Creating a Dropdown menu
```lua
Tab:AddDropdown({
	Name = "Dropdown",
	Default = "1",
	Options = {"1", "2"},
	Callback = function(Value)
	    -- Your function
	end    
})

--[[
Name = <string> - The name of the dropdown.
Default = <string> - The default value of the dropdown.
Options = <table> - The options in the dropdown.
Callback = <function> - The function of the dropdown.
]]
```

### Adding a set of new Dropdown buttons to an existing menu
```lua
Dropdown:Update({
    Name = 'New Dropdown Name',
    Options = {'Option A', 'Option B'},
    Callback = function(v)
        -- Your function
    end
})
```

### Clearing a dropdown menu
```lua
Dropdown:Clear()
```


### How :Update() work.
It updates any part of the UI.
Note that you dont need to change every element of the part. 
Below in an example of using update.
```lua
Dropdown:Update({
    --[[Notice how I didn't have Name = ''.  Thats OK]]
    Options = {'Your', 'New', 'Options'}
})

```

### Destroying elements
All you have to do is type
```lua
Element:Destroy()
```
