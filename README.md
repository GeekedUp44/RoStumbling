-- Gui to Lua
-- Version: 3.2

-- Instances:

local irostumbled = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local RPSTUMBLE = Instance.new("ImageLabel")
local Walkspeed = Instance.new("TextButton")
local value = Instance.new("TextBox")
local Gravity = Instance.new("TextButton")
local value2 = Instance.new("TextBox")
local NoClip = Instance.new("TextButton")
local Exit = Instance.new("TextButton")
local open = Instance.new("ImageButton")

--Properties:

irostumbled.Name = "irostumbled"
irostumbled.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
irostumbled.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
irostumbled.ResetOnSpawn = false

Frame.Parent = irostumbled
Frame.Active = true
Frame.BackgroundColor3 = Color3.fromRGB(38, 38, 38)
Frame.BorderColor3 = Color3.fromRGB(255, 21, 25)
Frame.Draggable = true
Frame.Position = UDim2.new(0.161337227, -9, 0.931456506, -13)
Frame.Selectable = true
Frame.Size = UDim2.new(0.675964773, 0, 0.068543449, 0)

RPSTUMBLE.Name = "RPSTUMBLE"
RPSTUMBLE.Parent = Frame
RPSTUMBLE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
RPSTUMBLE.BackgroundTransparency = 1.000
RPSTUMBLE.BorderSizePixel = 0
RPSTUMBLE.Position = UDim2.new(-0.000963151455, 0, -0.000821794849, 0)
RPSTUMBLE.Size = UDim2.new(0.22326088, 0, 1.00082338, 0)
RPSTUMBLE.Image = "http://www.roblox.com/asset/?id=11029327952"
RPSTUMBLE.ImageColor3 = Color3.fromRGB(255, 21, 25)

Walkspeed.Name = "Walkspeed"
Walkspeed.Parent = Frame
Walkspeed.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Walkspeed.BorderSizePixel = 0
Walkspeed.Position = UDim2.new(0.629064798, 0, 0.21698001, 0)
Walkspeed.Size = UDim2.new(0, 109, 0, 30)
Walkspeed.Text = "Walkspeed"
Walkspeed.TextColor3 = Color3.fromRGB(0, 0, 0)
Walkspeed.TextScaled = true
Walkspeed.TextSize = 14.000
Walkspeed.TextWrapped = true
Walkspeed.MouseButton1Click:Connect(function()
	game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = value.Text
end)

value.Name = "value"
value.Parent = Walkspeed
value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
value.BorderSizePixel = 0
value.Position = UDim2.new(0.992772102, 0, 0, 0)
value.Size = UDim2.new(0, 134, 0, 30)
value.Font = Enum.Font.SourceSans
value.PlaceholderText = "NumVal"
value.Text = ""
value.TextColor3 = Color3.fromRGB(0, 0, 0)
value.TextScaled = true
value.TextSize = 14.000
value.TextWrapped = true

Gravity.Name = "Gravity"
Gravity.Parent = Frame
Gravity.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Gravity.BorderSizePixel = 0
Gravity.Position = UDim2.new(0.236617774, 0, 0.218062624, 0)
Gravity.Size = UDim2.new(0, 109, 0, 30)
Gravity.Text = "Gravity"
Gravity.TextColor3 = Color3.fromRGB(0, 0, 0)
Gravity.TextScaled = true
Gravity.TextSize = 14.000
Gravity.TextWrapped = true
Gravity.MouseButton1Click:Connect(function()
	workspace.Gravity = value2.Text
end)


value2.Name = "value2"
value2.Parent = Gravity
value2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
value2.BorderSizePixel = 0
value2.Position = UDim2.new(0.992771745, 0, 0, 0)
value2.Size = UDim2.new(0, 109, 0, 30)
value2.Font = Enum.Font.SourceSans
value2.PlaceholderText = "NumVal"
value2.Text = ""
value2.TextColor3 = Color3.fromRGB(0, 0, 0)
value2.TextScaled = true
value2.TextSize = 14.000
value2.TextWrapped = true


NoClip.Name = "NoClip"
NoClip.Parent = Frame
NoClip.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
NoClip.BorderSizePixel = 0
NoClip.Position = UDim2.new(0.4891693, 0, 0.217590541, 0)
NoClip.Size = UDim2.new(0, 109, 0, 30)
NoClip.Text = "NoClip"
NoClip.TextColor3 = Color3.fromRGB(0, 0, 0)
NoClip.TextScaled = true
NoClip.TextSize = 14.000
NoClip.TextWrapped = true
NoClip.MouseButton1Click:Connect(function()
	local runservice = game:GetService("RunService")

	local player = game:GetService("Players").LocalPlayer
	runservice.Stepped:Connect(function()
		for i,v in pairs(player.Character:GetDescendants()) do
			if v:IsA("BasePart") then
				v.CanCollide = false
			end
		end
	end)
end)

Exit.Name = "Exit"
Exit.Parent = Frame
Exit.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Exit.BackgroundTransparency = 1.000
Exit.BorderSizePixel = 0
Exit.Position = UDim2.new(0.911614954, 0, -0.0572894067, 0)
Exit.Size = UDim2.new(0, 79, 0, 50)
Exit.Font = Enum.Font.SourceSansBold
Exit.Text = "X"
Exit.TextColor3 = Color3.fromRGB(255, 255, 255)
Exit.TextScaled = true
Exit.TextSize = 14.000
Exit.TextWrapped = true
Exit.MouseButton1Click:Connect(function()
	Frame.Visible=false
	open.Visible=true
end)

open.Name = "open"
open.Parent = irostumbled
open.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
open.BackgroundTransparency = 1.000
open.Position = UDim2.new(-0.00100000005, 0, 0.930999994, 0)
open.Size = UDim2.new(0.149000004, 0, 0.0649999976, 0)
open.Visible = false
open.Image = "http://www.roblox.com/asset/?id=11029327952"
open.ImageColor3 = Color3.fromRGB(255, 21, 25)
open.MouseButton1Click:Connect(function()
	Frame.Visible=true
	open.Visible=false
end)
