UI redz Hub 

redz Library V7

📌 This user interface is used in redz Hub scripts, but it has been rewritten and optimized.

🔹 why choose this UI?? 

- Beautiful.

- Easy to use.

- There are a lot of features that other UI don't have.

🔹 Open Source Easy and optimize.

Next, I'll tell you how to use this UI..

🚀 Start work

There are 2 options to load the UI: 1 via loadstring and 2 locally.

## 1 Option loadstring
```lua
local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/ABOBA412/Library/refs/heads/main/Source.lua"))()
```
# 2 Option locally
```lua
local success, redzlib = pcall(function()
-- Вставьте сюда содержимое пользовательского интерфейса.
end)
```

## Window
```lua
local Window = redzlib:MakeWindow({
  Title = "redz Hub : Blox Fruits",
  SubTitle = "by redz9999",
  SaveFolder = "redz_hub", -- название Json файла с сохранениями Flag ов
  Introduction = true,
  IntroductionTitle = "redz Hub",
  IntroductionDescription = "the best script",
  IntroductionImage = "rbxassetid://18751483361" 
})
```

## Minimize Button & Minimizer
```lua
local Minimizer = Window:NewMinimizer({
  KeyCode = Enum.KeyCode.LeftControl
})
Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://71014873973869", BackgroundTransparency = 0 },
    Corner = { CornerRadius = UDim.new(35, 1) },
})
```

## Tab
```lua
local Tab1 = Window:MakeTab({"Um", "cherry"})
```
## Start Tab
```lua
Window:SelectTab(Tab1) -- Стартовый таб.
```
## Section
```lua
local Section = Tab1:AddSection({"Section"})
```

## Paragraph
```lua
Tab1:AddParagraph({"Paragraph", "This is a Paragraph\nSecond Line"})
```
## Dialog
```lua
  Window:Dialog({
    Title = "???",
    Text = "Do you like cats?",
    Options = {
      {"Yes", function()
        print("Yes")
      end},
      {"No", function()
        print("No")
      end}
    }
  })
```
## Notify
```lua
Window:Notify({
  Title = "Notification",
  Content = "this is a Notification",
  Image = "rbxassetid://10734953451", -- Image.
  Duration = 5 
})
```
## Discord Invite
```lua
Tab1:AddDiscordInvite({
	Title = "Name Hub",
	Description = "Join server",
	Banner = "rbxassetid://18751483361", -- You can put an RGB Color: Color3.fromRGB(0, 0, 0)
	Logo = "rbxassetid://18751483361",
	Invite = "Link discord invite",
	Members = 200000, -- Optional
	Online = 20000, -- Optional
})
```
## ColorPicker
```lua
Tab1:AddColorPicker({
    Title = "My Color",
    Description = "Select the Color",
    Default = Color3.fromRGB(0, 0, 0),
	Flag = "MyColor",
    Callback = function(v)
        
    end
})
```
## Button 1 
```lua
Tab1:AddButton({"Print", function(Value)
print("Hello World!")
end})
```
## Toggle 1
```lua
local Toggle1 = Tab1:AddToggle({
  Name = "Auto Farm Level",
  Description = "Auto Farming Level", -- Desc
  Flag = "Auto Farm Level" -- Responsible for the toggle status after restarting the script on/off
  Default = false 
})
Toggle1:Callback(function(Value)
-- IsFarming = Value 
end)
```
## Toggle 2 ( Compact another callback )
```lua
Tab1:AddToggle({
    Name = "Auto Farm Nearest",
    Default = false,
    Flag = "Auto Farm Nearest",
    Callback = function(v)
    IsFarming = v
    end
})
```
## slider
```lua
Tab1:AddSlider({
  Name = "Tween Speed",
  Min = 1, -- Min meaning.
  Max = 100, -- Max meaning.
  Flag = "Tween Speed",
  Increase = 1,
  Default = 16,
  Callback = function(State)
  _G.TweenSpeed = State
  end
})
```
## Dropdown 1 ( Defaukt )
```lua
Tab1:AddDropdown({
  Name = "Players List",
  Description = "Select the <font color='rgb(88, 101, 242)'>Number</font>",
  Options = {"one", "two", "three"},
  Default = "two",
  Flag = "Player List",
  Callback = function(Value)
    
  end
})
```
# Dropdown 2 ( MultiSelect )
```lua
Tab1:AddDropdown({
  Name = "Dropdown",
  MultiSelect = true, -- Allows to select multiple options.
  Options = {"one", "two", "three", "four", "five"},
  Default = {"one", "four"},
  Callback = function(Value)
    
  end
})
```
## Textbox
```lua
Tab1:AddTextBox({
  Name = "Name item",
  Description = "1 Item on 1 Server",
  Flag = "Name item",
  PlaceholderText = "item only",
  Callback = function(Value)
    
  end
})
```
