local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/thanhdat4461/OrionMoblie/main/source')))()
repeat wait() until game:IsLoaded()
game:GetService("Players").LocalPlayer.Idled:connect(function()
game:GetService("VirtualUser"):ClickButton2(Vector2.new())
end)
local Window = OrionLib:MakeWindow({
		Name = "Rock Fruit",
		HidePremium = false,
		SaveConfig = true,
		ConfigFolder = "OrionTest",
        IntroText = "BY Script|Dev"       
}) 

local Tab = Window:MakeTab({
	Name = "FarmLv",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local EnermyFarm
local TweenService = game:GetService("TweenService")
Tab:AddLabel("AutoFarm Select ! Mobs")
Tab:AddDropdown({
	Name = "Select :> [Mobs]",
	Default = "1",
	Options = {"Bacon Real"},
	Callback = function(mob)
		EnermyFarm = mob
	end    
})
Tab:AddToggle({
Name = "Auto Farm [Selected]",
Default = false,
Callback = function(value)
pcall(function()
for i,v in pairs(workspace:GetDescendants()) do
if v.Name == PlayerTP1 then
if v.Humanoid.Health > 0 then
repeat
local toolName = "Combat" -- Replace "YourToolNameHere" with the name of your tool

local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
if v:IsA('Tool') and v.Name == toolName then
v.Parent = LocalPlayer.Character
break -- Stop the loop after picking up the tool
end
end
game:GetService("Players").LocalPlayer.Character.Yoru.Combo.C0:FireServer()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,5)
wait()  -- Wait a short time before checking again
until not _G.Hit or v.Humanoid.Health <= 0
end
end
end
end)
local Player = game.Players.LocalPlayer
local function onCharacterAdded(character)
character.Archivable = false
character:WaitForChild("HumanoidRootPart").Anchored = false
if Player.Character then
onCharacterAdded(Player.Character)
end
end
Player.CharacterAdded:Connect(onCharacterAdded)
end    
})
local Tab = Window:MakeTab({
	Name = "Stats",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
Tab:AddLabel(" -- UpStat -- ")
Tab:AddToggle({
Name = "Auto [Melee]",
Default = false,
Callback = function(Value)
_G.Melee = Value
while _G.Melee do wait(0.1)
    game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer("Melee", 10)
    end
end    
})
Tab:AddToggle({
Name = "Auto [Health]",
Default = false,
Callback = function(Value)
_G.Defend = Value
while _G.Defend do wait(0.1)
    game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer("maxHealth", 10)
    end
end    
})
Tab:AddToggle({
Name = "Auto [Devil-Fruit]",
Default = false,
Callback = function(Value)
_G.Sword = Value
while _G.Sword do wait(0.1)
    game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer("DevilFruit", 10)
    end
end    
})
Tab:AddToggle({
Name = "Auto [Sword]",
Default = false,
Callback = function(Value)
_G.Sword = Value
while _G.Sword do wait(0.1)
    game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer("Sword", 10)
    end
end    
})
local Tab = Window:MakeTab({
	Name = "Cave-Miner",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
Tab:AddLabel("Farm +Coin+")
Tab:AddButton({
Name = "Tp Get - [Pickaxe]",
Callback = function(Value)
        wait(1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1190.27563, 12.8834286, 428.714508, -0.988498807, 0, -0.15123108, 0, 1, 0, 0.15123108, 0, -0.988498807)
        wait(1)
        for _,v in next, workspace[" island cave"]["NPC Miner"]:GetDescendants() do
            if v.ClassName == "ProximityPrompt"  then
            fireproximityprompt(v, 1, true)
            end
        end
  	end    
})
Tab:AddToggle({
    Name = "AutoFarm [Coin]",
    Default = false,
    Callback = function(Value)
    _G.Coin = Value
    while _G.Coin do wait(0.1)
        local toolName = "Pickaxe" -- Replace "YourToolNameHere" with the name of your tool

        local LocalPlayer = game:GetService("Players").LocalPlayer
        for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
            if v:IsA('Tool') and v.Name == toolName then
                v.Parent = LocalPlayer.Character
                break -- Stop the loop after picking up the tool
            end
        end
        wait(1)
        for i,v in pairs(workspace[" island cave"]:GetDescendants()) do
            if v.Name == "Rock" then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
            end
        end
        wait(1)
        for _,v in next, workspace[" island cave"]:GetDescendants() do
            if v.ClassName == "ProximityPrompt"  then
            fireproximityprompt(v, 1, true)
            end
        end
        end
    end    
})
Tab:AddToggle({
    Name = "Auto [Sell]",
    Default = false,
    Callback = function(Value)
    _G.Sell = Value
    while _G.Sell do wait(1)
        for _,v in pairs(workspace[" island cave"].ShopSell.Pad.Give:GetDescendants()) do
            if v:IsA("TouchTransmitter") then
            firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
            firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
            end
            end
        end
    end    
})
local Tab = Window:MakeTab({
	Name = "Fishing",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
Tab:AddLabel("Click Get NPC Fishing-Rod")
Tab:AddButton({
Name = "Tp Get - [Fishing Rod]",
Callback = function(Value)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(21.0466843, 18.3833904, 324.096863, 0.360527158, -0, -0.932748854, 0, 1, -0, 0.932748854, 0, 0.360527158)
end    
})
Tab:AddToggle({
Name = "AutoFarm [Fish]",
Default = false,
Callback = function(Value)
_G.Fish = Value
while _G.Fish do wait(0.1)
local toolName = "FishingRod" -- Replace "YourToolNameHere" with the name of your tool

local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
    if v:IsA('Tool') and v.Name == toolName then
        v.Parent = LocalPlayer.Character
        break -- Stop the loop after picking up the tool
    end
end
wait(0.1)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(8, 17, 327)
wait(0.1)
local args = {
    [1] = "bind",
    [2] = Vector3.new(-5.0644378662109375, 1.149999976158142, 347.26373291015625)
}

game:GetService("Players").LocalPlayer.Character.FishingRod.LocalScript.RemoteFunction:InvokeServer(unpack(args))
        end
    end    
})
Tab:AddToggle({
Name = "Auto [Sell/Fish]",
Default = false,
Callback = function(Value)
_G.sell = Value
while _G.sell do wait(0.1)
    local toolName = "Fish" -- Replace "YourToolNameHere" with the name of your tool
    
    local LocalPlayer = game:GetService("Players").LocalPlayer
for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
    if v:IsA('Tool') and v.Name == toolName then
        v.Parent = LocalPlayer.Character
        break -- Stop the loop after picking up the tool
    end
end
	for _,v in pairs(workspace.ShopSell.Pad:GetDescendants()) do
	if v:IsA("TouchTransmitter") then
	firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
	firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
end
end
    end
end    
})
local Tab = Window:MakeTab({
	Name = "Raid",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
Tab:AddButton({
Name = "Tp Raid ! Zone",
Callback = function(Value)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(111,17,124)
    end    
})
Tab:AddToggle({
Name = "Auto [Raid]",
Default = false,
Callback = function(Value)
    _G.raid = Value
while _G.raid do wait(0.5)
local TweenService = game:GetService("TweenService")
local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(0, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(76,3,-79)}):Play()
sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", 112412400000)
sethiddenproperty(game.Players.LocalPlayer, "MaxSimulationRadius", 112412400000)
for i,d in pairs(game.Workspace:GetDescendants()) do
if d.ClassName == 'Humanoid' and d.Parent.Name ~= game.Players.LocalPlayer.Name then
d.Health = 0
end
end
end
end    
})
