
-- Yellow Hub | Arsenal - Menu Profissional

local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/UiLibProject/Orion/main/OrionLib.lua"))()

local window = library:MakeWindow({
    Name = "Yellow Hub | Arsenal",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "YellowHubArsenal"
})

-- Tabs
local visualTab = window:MakeTab({ Name = "Visual", Icon = "👁️", PremiumOnly = false })
local espTab = window:MakeTab({ Name = "ESP", Icon = "📦", PremiumOnly = false })
local aimbotTab = window:MakeTab({ Name = "Aimbot", Icon = "🎯", PremiumOnly = false })
local settingsTab = window:MakeTab({ Name = "Settings", Icon = "⚙️", PremiumOnly = false })

-- Visual Options
visualTab:AddToggle({
    Name = "Enable Visuals",
    Default = true,
    Callback = function(Value) _G.VisualsEnabled = Value end
})

-- ESP Options
espTab:AddToggle({ Name = "ESP Enabled", Default = true, Callback = function(v) _G.ESPEnabled = v end })
espTab:AddToggle({ Name = "Box", Default = true, Callback = function(v) _G.BoxESP = v end })
espTab:AddToggle({ Name = "Name", Default = true, Callback = function(v) _G.NameESP = v end })
espTab:AddToggle({ Name = "Tracer", Default = false, Callback = function(v) _G.TracerESP = v end })
espTab:AddToggle({ Name = "Skeleton", Default = false, Callback = function(v) _G.SkeletonESP = v end })
espTab:AddToggle({ Name = "Distance", Default = false, Callback = function(v) _G.DistanceESP = v end })
espTab:AddToggle({ Name = "Team Check", Default = true, Callback = function(v) _G.TeamCheck = v end })

-- Aimbot Options
aimbotTab:AddToggle({ Name = "Enable Aimbot", Default = true, Callback = function(v) _G.AimbotEnabled = v end })
aimbotTab:AddSlider({
    Name = "Aimbot FOV",
    Min = 10,
    Max = 300,
    Default = 120,
    Color = Color3.fromRGB(255, 255, 0),
    Increment = 1,
    ValueName = "px",
    Callback = function(Value) _G.AimbotFOV = Value end
})
aimbotTab:AddToggle({ Name = "Draw FOV Circle", Default = true, Callback = function(v) _G.DrawFOV = v end })

-- Settings Tab
settingsTab:AddBind({
    Name = "Toggle Menu",
    Default = Enum.KeyCode.RightShift,
    Hold = false,
    Callback = function()
        library:Toggle()
    end,
})

-- Finaliza
library:Init()
