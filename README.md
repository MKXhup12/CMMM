local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("ZX Hub", "DarkTheme")

local Tab = Window:NewTab("Main")

local Section = Tab:NewSection("Auto Equip")

local Weaponlist = {}

local Weapon = nil

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do

    table.insert(Weaponlist,v.Name)

end

Section:NewDropdown("select weapon", " ", Weaponlist, function(currentOption)

    Weapon = currentOption

end)

Section:NewToggle("Auto Equip", " ", function(a)

AutoEquiped = a

end)

spawn(function()

while wait() do

if AutoEquiped then

pcall(function()

game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))

end)

end

end

end)

local Tab = Window:NewTab("ไก่ตันละมั้ง")

local noSection = Tab:NewSection("เริ่ม")

Section:NewButton("ButtonText", "ButtonInfo", function()

    loadstring(game:HttpGet("https://raw.githubusercontent.com/GooD1020/Exon_x_hub_kaitan/main/README.md"))()

end)

Section:NewButton("ButtonText", "ButtonInfo", function()

    loadstring(game:HttpGet("https://raw.githubusercontent.com/GooD1020/Exon_x_hub_kaitan/main/README.md"))()

end)

Section:NewButton("ตัน1วิ", "ButtonInfo", function()

   

local plr = game:GetService("Players").LocalPlayer

local Notification = require(game:GetService("ReplicatedStorage").Notification)

local Data = plr:WaitForChild("Data")

local EXPFunction = require(game.ReplicatedStorage:WaitForChild("EXPFunction"))

local LevelUp = require(game:GetService("ReplicatedStorage").Effect.Container.LevelUp)

local Sound = require(game:GetService("ReplicatedStorage").Util.Sound)

local LevelUpSound = game:GetService("ReplicatedStorage").Util.Sound.Storage.Other:FindFirstChild("LevelUp_Proxy") or game:GetService("ReplicatedStorage").Util.Sound.Storage.Other:FindFirstChild("LevelUp")

function v129(p15)

local v130 = p15;

while true do

local v131, v132 = string.gsub(v130, "^(-?%d+)(%d%d%d)", "%1,%2");

v130 = v131;

if v132 == 0 then

break;

end;

end;

return v130;

end;

Notification.new("<Color=Yellow>QUEST COMPLETED!<Color=/>"):Display()

Notification.new("Earned <Color=Yellow>1,000,000,000,000 Exp.<Color=/> (+ None)"):Display()

Notification.new("Earned <Color=Green>$25,000<Color=/>"):Display()

plr.Data.Exp.Value = 999999999999

plr.Data.Beli.Value = plr.Data.Beli.Value + 25000

delay = 0

count = 0

while plr.Data.Exp.Value - EXPFunction(Data.Level.Value) > 0 do

plr.Data.Exp.Value = plr.Data.Exp.Value - EXPFunction(Data.Level.Value)

plr.Data.Level.Value = plr.Data.Level.Value + 1

plr.Data.Points.Value = plr.Data.Points.Value + 3

LevelUp({ plr })

Sound.Play(Sound, LevelUpSound.Value)

Notification.new("<Color=Green>LEVEL UP!<Color=/> (" .. plr.Data.Level.Value .. ")"):Display()

count = count + 1

if count >= 5 then

delay = tick()

count = 0

wait()

end

end

end)

