Пользовательский интерфейс redz Hub 

📌 Данный пользовательский интерфейс используется в скриптах redz Hub но он был переписан, и оптимизирован для общего пользования.

🔹 Почему стоит выбрать именно этот пользовательский интерфейс? 

- Красивый.

- Удобный в использовании.

- есть куча фишек и того, чего нет в других пользовательских интерфейсах.

🔹 Открытый исходный код, легкий и оптимизированный.

Далее я расскажу как использовать этот пользовательский интерфейс.

🚀 Начало работы

Чтобы загрузить UI есть 2 варианта: 1 через loadstring 2 локально

## 1 Способ через loadstring
```lua
local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/ABOBA412/Library/refs/heads/main/Source.lua"))()
```
# 2 Способ локальный
```lua
local success, redzlib = pcall(function()
-- Вставьте сюда содержимое пользовательского интерфейса.
end)
```

## Окно
```lua
local Window = redzlib:MakeWindow({
  Title = "redz Hub : Blox Fruits",
  SubTitle = "by redz9999",
  SaveFolder = "redz_hub" -- название Json файла с сохранениями Flag ов
})
```

## Кнопка для сворачивания
```lua
local Minimizer = Window:NewMinimizer({
  KeyCode = Enum.KeyCode.LeftControl
})
Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://71014873973869", BackgroundTransparency = 0 },
    Corner = { CornerRadius = UDim.new(35, 1) },
})
```

## Приглашение в Discord
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


## Таб
```lua
local Tab1 = Window:MakeTab({"Um", "cherry"})
```
## Стартовый таб
```lua
Window:SelectTab(Tab1) -- Стартовый таб.
```
## Секция
```lua
local Section = Tab1:AddSection({"Section"}) -- Секция.
```

## Параграф
```lua
Tab1:AddParagraph({"Paragraph", "This is a Paragraph\nSecond Line"})
```
## Диалог
```lua
  Window:Dialog({
    Title = "???",
    Text = "Ты любишь котиков?",
    Options = {
      {"Да", function()
        print("Да")
      end},
      {"Нет", function()
        print("Нет")
      end}
    }
  })
```
## Уведомление
```lua
Window:Notify({
  Title = "Notification",
  Content = "this is a Notification",
  Image = "rbxassetid://10734953451", -- Иконка.
  Duration = 5 -- Время, через которое пропадет уведомление.
})
```
## Кнопка 1 
```lua
Tab1:AddButton({"Print", function(Value)
print("Hello World!")
end})
```
## Toggle 1
```lua
local Toggle1 = Tab1:AddToggle({
  Name = "Auto Farm Level",
  Description = "Auto Farming Level", -- Описание.
  Flag = "Auto Farm Level" -- Отвечает за состояние toggle после перезапуска скрипта включено/выключено
  Default = false 
})
Toggle1:Callback(function(Value)
-- IsFarming = Value 
end)
```



## Toggle 2 ( Компактный с другим callback )
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



## Слайдер
```lua
Tab1:AddSlider({
  Name = "Tween Speed",
  Min = 1, -- Минимальное значение.
  Max = 100, -- Максимальное значение.
  Flag = "Tween Speed",
  Increase = 1,
  Default = 16,
  Callback = function(State)
  G.TweenSpeed = State
  end
})
```

## Dropdown 1 ( Обычный )
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
  MultiSelect = true, -- Позволяет выбирать несколько опций.
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
  PlaceholderText = "item only",
  Callback = function(Value)
    
  end
})
```
## Объяснение что для чего нужно
- 1 Секция просто заголовок.
- 2 Toggle переключатель для скрипта который например включает/выключает авто фарм.
- 3 Dropdown выберите опцию для скрипта например способ телепорта.
- 4 Кнопка при нажатии исполняет заданный код например телепортирует вас в нужную точку.
- 5 Слайдер Выберите значение для скрипта, например скорость спид хака.
- 6 TextBox запишите значение, например имя сервера на который надо телепортироваться.
- 7 Приглашение в Discord копируйте ссылку на дискорд сервер.
  
так же вы можете самостоятельно настраивать значения например в toggle то есть убрать Flag и Description использовать компактный callback и тд.
## Как создавать Toggle ы и тд в Табах?
Создайте таб, например Tab2

А потом создайте Tab2AddToggle({

Все просто!

## Остальное

Если вы хотите, сделать текст цветным, просто используйте это

## 
```txt
<font color='rgb(255, 255, 255)'>Тут текст, который надо сделать цветным</font>
```
rgb(255, 255, 255) Цвет текста, в данном случае тут стоит 255,255,255 что даст белый цвет.

