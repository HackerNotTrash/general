local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))()
local venyx = library.new("Switch Hub", 5013109572)

players = {}

for i,v in pairs(game:GetService("Players"):GetChildren()) do
     table.insert(players,v.Name)
        end

local page = venyx:addPage("Players", 5012544693)
local section1 = page:addSection("Teleport")
local section2 = page:addSection("Select Player")

section2:addDropdown("Select Player",players, function(kuy)
   Choose = kuy
       end)

local section2 = page:addSection("Ability")
section2:addButton("Ctrl+Click = tp", function()
local Plr = game:GetService("Players").LocalPlayer
local Mouse = Plr:GetMouse()

Mouse.Button1Down:connect(function()
if not game:GetService("UserInputService"):IsKeyDown(Enum.KeyCode.LeftControl) then return end
if not Mouse.Target then return end
Plr.Character:MoveTo(Mouse.Hit.p)
end)
end)

section2:addToggle("Anchored", nil, function(value)
game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = value
end)

local section2 = page:addSection("Hide")


section1:addButton("Teleport", function()
    Point1 = game.Players.LocalPlayer.Character.HumanoidRootPart
Point2 = game.Players[Choose].Character.HumanoidRootPart.CFrame --Choose = ค่าที่เราตั้ง
Time = 2 -- Seccond
TypeStyle = Enum.EasingStyle.Linear
tweenService = game:GetService("TweenService")

tweenInfo = TweenInfo.new(Time, TypeStyle)
tween = tweenService:Create(Point1, tweenInfo, {CFrame = Point2})
tween:Play()
end)

section1:addButton("Refresh", function()
    table.clear(players)
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
      end
end)

section2:addKeybind("Toggle Keybind", Enum.KeyCode.RightControl, function()
print("Activated Keybind")
venyx:toggle()
end)
