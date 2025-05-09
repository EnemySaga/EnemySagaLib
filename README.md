# EnemySagaLib

EnemySagaLib adalah UI library untuk Roblox yang dirancang untuk Create script hub dengan tampilan modern dan elegan.

## Fitur

- Sistem tab dengan ikon
- Berbagai elemen UI (tombol, toggle, dropdown, slider, input, dll)
- Indikator status dengan warna
- Tema yang dapat disesuaikan
- Animasi transisi yang halus
- Desain responsif

## How To use My Library

### Load Library

```lua
local EnemySagaLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/EnemySaga/EnemySagaLib/refs/heads/main/Library"))()
```

### Create Window

```lua
local Window = EnemySagaLib.new("Nama Hub", "Subtitle")
```

### Create Tab

```lua
local myTab = Window:CreateTab("Nama Tab", "rbxassetid://ICON_ID") -- Icon ID opsional
```

### Create Section

```lua
local mySection = Window:CreateSection(myTab, "Nama Section")
```

### Create Button

```lua
local myButton = Window:CreateButton(mySection, "Nama Button", function()
    print("Button diklik!")
end)
```

### Create Toggle

```lua
local myToggle = Window:CreateToggle(mySection, "Nama Toggle", false, function(enabled)
    print("Toggle:", enabled)
end)

myToggle:SetValue(true)
```

### Create Dropdown

```lua
local options = {"Option 1", "Option 2", "Option 3"}
local myDropdown = Window:CreateDropdown(mySection, "Nama Dropdown", options, "Option 1", function(selected)
    print("Selected:", selected)
end)

myDropdown:SetValue("Option 2")
```

### Create Slider

```lua
local mySlider = Window:CreateSlider(mySection, "Nama Slider", 0, 100, 50, "%", 0, function(value)
    print("Value:", value)
end)

mySlider:SetValue(75)
```

### Create Input

```lua
local myInput = Window:CreateInput(mySection, "Nama Input", "Placeholder text...", function(text)
    print("Input:", text)
end)

myInput:SetValue("Nilai baru")

local currentValue = myInput:GetValue()
```

### Create Status Indicator

```lua
local myStatus = Window:CreateStatusIndicator(mySection, "Nama Status", {
    spawn = false, -- true for "Spawn", false for "Not Spawn"
    text = "Custom Text", -- Opsional, text custom
    color = Color3.fromRGB(255, 0, 0) -- Opsional, color custom
})

-- change status
myStatus:SetSpawn(true) -- change ke "Spawn"
myStatus:SetStatus("Custom Status", Color3.fromRGB(0, 255, 0)) -- change text and color
```

## Costumize

Anda dapat mengubah tema UI dengan memodifikasi variabel `THEME` di awal file `library`:

```lua
local THEME = {
    Background = Color3.fromRGB(25, 25, 25),
    Accent = Color3.fromRGB(0, 255, 128),
    DarkAccent = Color3.fromRGB(0, 200, 100),
    LightText = Color3.fromRGB(240, 240, 240),
    DarkText = Color3.fromRGB(150, 150, 150),
    TabBackground = Color3.fromRGB(30, 30, 30),
    ElementBackground = Color3.fromRGB(40, 40, 40),
    ElementBackgroundHover = Color3.fromRGB(45, 45, 45),
    StatusRed = Color3.fromRGB(255, 75, 75),
    StatusGreen = Color3.fromRGB(75, 255, 75),
}
```

## Notes

- Beberapa fitur mungkin tidak berfungsi di semua game Roblox tergantung pada pengaturan keamanan game

## Credit

- Dibuat dengan EnemySagaLib
