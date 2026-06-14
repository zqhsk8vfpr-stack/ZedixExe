local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/sametexe001/sametlibs/refs/heads/main/lds13/Library.lua"))()

local Window = Library:Window({
    Name = "Zedix",
    SubTitle = "V1.0",
    Owner = "Luhzyrus"
})

-- Pages
local MainPage = Window:Page({ Name = "Main", Icon = "131145598162617", Columns = 2 })
local MiscPage = Window:Page({ Name = "Miscellaneous", Icon = "131145598162617", Columns = 2 })

local SettingsPage = Library:CreateSettingsPage(Window)

-- ========================= MAIN PAGE - LEFT COLUMN =========================
-- Camlock section
local CamlockSection = MainPage:Section({ Name = "Camlock", Side = 1 })

CamlockSection:Toggle({
    Name = "Enable Camlock",
    Flag = "CamlockToggle",
    Default = false
})

CamlockSection:Label("Aim key"):Keybind({
    Name = "Aim key",
    Flag = "AimKey",
    Default = Enum.KeyCode.E
})

CamlockSection:Dropdown({
    Name = "Aim mode",
    Flag = "AimMode",
    Default = "Camlock",
    Items = { "Camlock", "Mouselock" }
})

CamlockSection:Toggle({
    Name = "Smoothing",
    Flag = "SmoothingToggle",
    Default = false
})

CamlockSection:Label("Smoothing X")
CamlockSection:Textbox({
    Name = "Smoothing X",
    Flag = "SmoothingX",
    Default = "0.1",
    Numeric = true,
    Finished = true
})

CamlockSection:Label("Smoothing Y")
CamlockSection:Textbox({
    Name = "Smoothing Y",
    Flag = "SmoothingY",
    Default = "0.1",
    Numeric = true,
    Finished = true
})

CamlockSection:Toggle({
    Name = "Enable Sticky Aim",
    Flag = "StickyAimToggle",
    Default = false
})

CamlockSection:Label("Sticky Aim X")
CamlockSection:Textbox({
    Name = "Sticky Aim X",
    Flag = "StickyAimX",
    Default = "0.1",
    Numeric = true,
    Finished = true
})

CamlockSection:Label("Sticky Aim Y")
CamlockSection:Textbox({
    Name = "Sticky Aim Y",
    Flag = "StickyAimY",
    Default = "0.1",
    Numeric = true,
    Finished = true
})

CamlockSection:Toggle({
    Name = "Shake",
    Flag = "ShakeToggle",
    Default = false
})

CamlockSection:Label("Shake X")
CamlockSection:Textbox({
    Name = "Shake X",
    Flag = "ShakeX",
    Default = "0",
    Numeric = true,
    Finished = true
})

CamlockSection:Label("Shake Y")
CamlockSection:Textbox({
    Name = "Shake Y",
    Flag = "ShakeY",
    Default = "0",
    Numeric = true,
    Finished = true
})

CamlockSection:Label("Shake Z")
CamlockSection:Textbox({
    Name = "Shake Z",
    Flag = "ShakeZ",
    Default = "0",
    Numeric = true,
    Finished = true
})

CamlockSection:Label("Jump Offset")
CamlockSection:Textbox({
    Name = "Jump Offset",
    Flag = "JumpOffset",
    Default = "0",
    Numeric = true,
    Finished = true
})

CamlockSection:Label("Fall Offset")
CamlockSection:Textbox({
    Name = "Fall Offset",
    Flag = "FallOffset",
    Default = "0",
    Numeric = true,
    Finished = true
})

CamlockSection:Dropdown({
    Name = "Easing Style",
    Flag = "EasingStyle",
    Default = "Linear",
    Items = { "Linear", "Sine", "Quad", "Cubic", "Quart", "Expo", "Back", "Bounce", "Elastic" }
})

CamlockSection:Dropdown({
    Name = "Easing Direction",
    Flag = "EasingDirection",
    Default = "In",
    Items = { "In", "Out", "InOut" }
})

CamlockSection:Dropdown({
    Name = "AimPart",
    Flag = "AimPart",
    Default = "Head",
    Items = { "Head", "Humanoid", "UpperTorso", "LowerTorso", "RightLeg", "LeftLeg" }
})

CamlockSection:Dropdown({
    Name = "Air Aim Part",
    Flag = "AirAimPart",
    Default = "Head",
    Items = { "Head", "UpperTorso", "LowerTorso", "LeftLeg", "RightLeg" }
})

-- Prediction section (separate)
local CamlockPredictionSection = MainPage:Section({ Name = "Camlock Prediction", Side = 1 })

CamlockPredictionSection:Toggle({
    Name = "Enable Prediction",
    Flag = "EnablePrediction",
    Default = false
})

CamlockPredictionSection:Dropdown({
    Name = "Prediction Type",
    Flag = "PredictionType",
    Default = "Velocity",
    Items = { "Velocity", "Regular", "Linear", "Rot", "Angular", "Advanced" }
})

CamlockPredictionSection:Label("Prediction X")
CamlockPredictionSection:Textbox({
    Name = "Prediction X",
    Flag = "PredictionX",
    Default = "0",
    Numeric = true,      -- allows only numbers
    Finished = true,     -- saves value when you press Enter or click away
    Callback = function(v) print("PredictionX set to:", v) end
})

CamlockPredictionSection:Label("Prediction Y")
CamlockPredictionSection:Textbox({
    Name = "Prediction Y",
    Flag = "PredictionY",
    Default = "0",
    Numeric = true,
    Finished = true,
    Callback = function(v) print("PredictionY set to:", v) end
})

CamlockPredictionSection:Label("Prediction Z")
CamlockPredictionSection:Textbox({
    Name = "Prediction Z",
    Flag = "PredictionZ",
    Default = "0",
    Numeric = true,
    Finished = true,
    Callback = function(v) print("PredictionZ set to:", v) end
})

CamlockPredictionSection:Toggle({
    Name = "Auto Prediction",
    Flag = "AutoPrediction",
    Default = false
})

CamlockPredictionSection:Dropdown({
    Name = "Auto Pred Method",
    Flag = "AutoPredMethod",
    Default = "Default",
    Items = { "Default", "Advanced" }
})
-- Silent Aim section
local SilentAimSection = MainPage:Section({ Name = "Silent Aim", Side = 2 })

SilentAimSection:Toggle({
    Name = "Enable Silent Aim",
    Flag = "SilentAimToggle",
    Default = false
})

SilentAimSection:Label("Silent Aim Key"):Keybind({
    Name = "Silent Aim Key",
    Flag = "SilentAimKey",
    Default = Enum.KeyCode.Q
})

SilentAimSection:Dropdown({
    Name = "Target Mode",
    Flag = "TargetMode",
    Default = "FOV",
    Items = { "FOV", "Target" }
})

SilentAimSection:Slider({
    Name = "Hit Chance %",
    Flag = "HitChance",
    Default = 100,
    Min = 0,
    Max = 100,
    Decimals = 0,
    Suffix = "%"
})

SilentAimSection:Dropdown({
    Name = "Hit Type",
    Flag = "HitType",
    Default = "Aim Bone",
    Items = { "Aim Bone", "Nearest Point", "Closest Part" }
})

SilentAimSection:Dropdown({
    Name = "Aim Bone",
    Flag = "AimBone",
    Default = "Head",
    Items = { "Head", "Torso", "Left Arm", "Right Arm", "Left Leg", "Right Leg" }
})

SilentAimSection:Toggle({
    Name = "Anti Curve",
    Flag = "AntiCurve",
    Default = false
})

SilentAimSection:Slider({
    Name = "Max Angle",
    Flag = "MaxAngle",
    Default = 90,
    Min = 0,
    Max = 360,
    Decimals = 1,
    Suffix = "°"
})

-- Silent Aim Prediction section (separate)
local SilentAimPredictionSection = MainPage:Section({ Name = "Silent Aim Prediction", Side = 2 })

SilentAimPredictionSection:Toggle({
    Name = "Enable Prediction",
    Flag = "SilentEnablePrediction",
    Default = false
})

SilentAimPredictionSection:Dropdown({
    Name = "Prediction Type",
    Flag = "SilentPredictionType",
    Default = "Velocity",
    Items = { "Velocity", "Regular", "Linear", "Rot", "Angular", "Advanced" }
})

SilentAimPredictionSection:Label("Prediction X")
SilentAimPredictionSection:Textbox({
    Name = "Prediction X",
    Flag = "SilentPredictionX",
    Default = "0",
    Numeric = true,
    Finished = true
})

SilentAimPredictionSection:Label("Prediction Y")
SilentAimPredictionSection:Textbox({
    Name = "Prediction Y",
    Flag = "SilentPredictionY",
    Default = "0",
    Numeric = true,
    Finished = true
})

SilentAimPredictionSection:Label("Prediction Z")
SilentAimPredictionSection:Textbox({
    Name = "Prediction Z",
    Flag = "SilentPredictionZ",
    Default = "0",
    Numeric = true,
    Finished = true
})

SilentAimPredictionSection:Toggle({
    Name = "Auto Prediction",
    Flag = "SilentAutoPrediction",
    Default = false
})

SilentAimPredictionSection:Dropdown({
    Name = "Auto Pred Method",
    Flag = "SilentAutoPredMethod",
    Default = "Default",
    Items = { "Default", "Advanced" }
})

-- MISCELLANEOUS PAGE
local MiscLeft = MiscPage:Section({ Name = "Miscellaneous", Side = 1 })

MiscLeft:Toggle({
    Name = "Anti Aim Viewer",
    Flag = "AntiAimViewer",
    Default = false
})

MiscLeft:Toggle({
    Name = "No Jump Cooldown",
    Flag = "NoJumpCooldown",
    Default = false
})

MiscLeft:Toggle({
    Name = "No Slowdown",
    Flag = "NoSlowdown",
    Default = false
})

MiscLeft:Label("Whitelist (Username)")
MiscLeft:Textbox({
    Name = "Whitelist",
    Flag = "WhitelistUser",
    Default = "",
    Finished = true,
    Callback = function(v) print("Whitelist user:", v) end
})

MiscLeft:Toggle({
    Name = "Anti Mod",
    Flag = "AntiMod",
    Default = false
})

MiscLeft:Toggle({
    Name = "Check Mods On Load",
    Flag = "CheckModsOnLoad",
    Default = false
})

MiscLeft:Dropdown({
    Name = "Mod Action",
    Flag = "ModAction",
    Default = "Notify",
    Items = { "Notify", "Crash", "Server Hop", "Kick" }
})

MiscLeft:Toggle({
    Name = "Add Mod Group IDs",
    Flag = "AddModGroupIDs",
    Default = false
})

MiscLeft:Label("Mod Group IDs (comma separated)")
MiscLeft:Textbox({
    Name = "Mod Group IDs",
    Flag = "ModGroupIDs",
    Default = "",
    Finished = true,
    Callback = function(v) print("Mod group IDs:", v) end
})

-- ESP Section
local ESPSection = MiscPage:Section({ Name = "ESP Settings", Side = 2 })

ESPSection:Toggle({
    Name = "Names",
    Flag = "ESPNames",
    Default = false
})

ESPSection:Toggle({
    Name = "Box",
    Flag = "ESPBox",
    Default = false
})

ESPSection:Toggle({
    Name = "ESP Distances",
    Flag = "ESPDistances",
    Default = false
})

ESPSection:Toggle({
    Name = "Weapons",
    Flag = "ESPWeapons",
    Default = false
})

ESPSection:Toggle({
    Name = "Health Bar",
    Flag = "ESPHealthBar",
    Default = false
})

ESPSection:Toggle({
    Name = "Armor Bar",
    Flag = "ESPArmorBar",
    Default = false
})

-- Checks Section
local ChecksSection = MiscPage:Section({ Name = "Checks", Side = 2 })

ChecksSection:Toggle({
    Name = "Wall Check",
    Flag = "WallCheck",
    Default = false
})

ChecksSection:Toggle({
    Name = "Friend Check",
    Flag = "FriendCheck",
    Default = false
})

ChecksSection:Toggle({
    Name = "Knock Check",
    Flag = "KnockCheck",
    Default = false
})

ChecksSection:Toggle({
    Name = "Forcefield Check",
    Flag = "ForcefieldCheck",
    Default = false
})

ChecksSection:Toggle({
    Name = "Reload Check",
    Flag = "ReloadCheck",
    Default = false
})

ChecksSection:Toggle({
    Name = "Katana Check",
    Flag = "KatanaCheck",
    Default = false
})
