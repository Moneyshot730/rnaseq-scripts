-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local TextButton = Instance.new("TextButton")
local UICorner = Instance.new("UICorner")
local Test = Instance.new("Frame")
local label = Instance.new("TextLabel")
local Fly = Instance.new("TextButton")
local EToTp = Instance.new("TextButton")
local NoClip = Instance.new("TextButton")
local Teleport = Instance.new("TextButton")
local TeleportToPlayer = Instance.new("TextButton")
local Speed = Instance.new("TextButton")
local ESP = Instance.new("TextButton")
local Aimbot = Instance.new("TextButton")
local Infinitejump = Instance.new("TextButton")
local Close = Instance.new("TextButton")
local NextPage = Instance.new("TextButton")
local Testt = Instance.new("Frame")
local label_2 = Instance.new("TextLabel")
local Close_2 = Instance.new("TextButton")
local BloxFruitV2 = Instance.new("TextButton")
local MuderMy2 = Instance.new("TextButton")
local PetSim = Instance.new("TextButton")
local DaHood = Instance.new("TextButton")
local InvisFling = Instance.new("TextButton")
local InfiniteYield = Instance.new("TextButton")
local _5 = Instance.new("TextButton")
local _3 = Instance.new("TextButton")
local _4 = Instance.new("TextButton")
local _2 = Instance.new("TextButton")
local _1 = Instance.new("TextButton")
local _6 = Instance.new("TextButton")
local _10 = Instance.new("TextButton")
local _8 = Instance.new("TextButton")
local _9 = Instance.new("TextButton")
local _7 = Instance.new("TextButton")
local _14 = Instance.new("TextButton")
local _11 = Instance.new("TextButton")
local _12 = Instance.new("TextButton")
local _15 = Instance.new("TextButton")
local _13 = Instance.new("TextButton")
local _16 = Instance.new("TextButton")
local _18 = Instance.new("TextButton")
local _19 = Instance.new("TextButton")
local _17 = Instance.new("TextButton")
local _20 = Instance.new("TextButton")

--Properties:

ScreenGui.Parent = game.CoreGui

TextButton.Parent = ScreenGui
TextButton.BackgroundColor3 = Color3.fromRGB(90, 90, 90)
TextButton.Position = UDim2.new(0.00603968883, 0, 0.568807423, 0)
TextButton.Size = UDim2.new(0, 200, 0, 50)
TextButton.Font = Enum.Font.Cartoon
TextButton.Text = "Open"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextScaled = true
TextButton.TextSize = 14.000
TextButton.TextWrapped = true

UICorner.CornerRadius = UDim.new(0.200000003, 0)
UICorner.Parent = TextButton

Test.Name = "Test"
Test.Parent = ScreenGui
Test.BackgroundColor3 = Color3.fromRGB(93, 93, 93)
Test.BackgroundTransparency = 0.100
Test.Position = UDim2.new(0.268334746, 0, 0.228560418, 0)
Test.Size = UDim2.new(0, 579, 0, 390)
Test.Visible = false
Test.Active = true

label.Name = "label"
label.Parent = Test
label.BackgroundColor3 = Color3.fromRGB(76, 76, 76)
label.Size = UDim2.new(0, 579, 0, 50)
label.Font = Enum.Font.Cartoon
label.Text = "Trolling Gui"
label.TextColor3 = Color3.fromRGB(0, 0, 0)
label.TextScaled = true
label.TextSize = 14.000
label.TextWrapped = true

Fly.Name = "Fly"
Fly.Parent = Test
Fly.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Fly.Position = UDim2.new(0, 0, 0.169230774, 0)
Fly.Size = UDim2.new(0, 142, 0, 50)
Fly.Font = Enum.Font.SourceSans
Fly.Text = "Fly"
Fly.TextColor3 = Color3.fromRGB(0, 0, 0)
Fly.TextScaled = true
Fly.TextSize = 14.000
Fly.TextWrapped = true
Fly.MouseButton1Click:Connect(function()
	repeat wait() 
	until game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:findFirstChild("HumanoidRootPart") and game.Players.LocalPlayer.Character:findFirstChild("Humanoid") 
	local mouse = game.Players.LocalPlayer:GetMouse() 
	repeat wait() until mouse
	local plr = game.Players.LocalPlayer 
	local torso = plr.Character.HumanoidRootPart 
	local flying = true
	local deb = true 
	local ctrl = {f = 0, b = 0, l = 0, r = 0} 
	local lastctrl = {f = 0, b = 0, l = 0, r = 0} 
	local maxspeed = 50 
	local speed = 0 

	function Fly() 
		local bg = Instance.new("BodyGyro", torso) 
		bg.P = 9e4 
		bg.maxTorque = Vector3.new(9e9, 9e9, 9e9) 
		bg.cframe = torso.CFrame 
		local bv = Instance.new("BodyVelocity", torso) 
		bv.velocity = Vector3.new(0,0.1,0) 
		bv.maxForce = Vector3.new(9e9, 9e9, 9e9) 
		repeat wait() 
			plr.Character.Humanoid.PlatformStand = true 
			if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then 
				speed = speed+.5+(speed/maxspeed) 
				if speed > maxspeed then 
					speed = maxspeed 
				end 
			elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then 
				speed = speed-1 
				if speed < 0 then 
					speed = 0 
				end 
			end 
			if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then 
				bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
				lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r} 
			elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then 
				bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
			else 
				bv.velocity = Vector3.new(0,0.1,0) 
			end 
			bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0) 
		until not flying 
		ctrl = {f = 0, b = 0, l = 0, r = 0} 
		lastctrl = {f = 0, b = 0, l = 0, r = 0} 
		speed = 0 
		bg:Destroy() 
		bv:Destroy() 
		plr.Character.Humanoid.PlatformStand = false 
	end 
	mouse.KeyDown:connect(function(key) 
		if key:lower() == "e" then 
			if flying then flying = false 
			else 
				flying = true 
				Fly() 
			end 
		elseif key:lower() == "w" then 
			ctrl.f = 1 
		elseif key:lower() == "s" then 
			ctrl.b = -1 
		elseif key:lower() == "a" then 
			ctrl.l = -1 
		elseif key:lower() == "d" then 
			ctrl.r = 1 
		end 
	end) 
	mouse.KeyUp:connect(function(key) 
		if key:lower() == "w" then 
			ctrl.f = 0 
		elseif key:lower() == "s" then 
			ctrl.b = 0 
		elseif key:lower() == "a" then 
			ctrl.l = 0 
		elseif key:lower() == "d" then 
			ctrl.r = 0 
		end 
	end)
	Fly()	
end)

EToTp.Name = "E To Tp"
EToTp.Parent = Test
EToTp.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
EToTp.Position = UDim2.new(0, 0, 0.43589747, 0)
EToTp.Size = UDim2.new(0, 142, 0, 50)
EToTp.Font = Enum.Font.SourceSans
EToTp.Text = "E To Tp"
EToTp.TextColor3 = Color3.fromRGB(0, 0, 0)
EToTp.TextScaled = true
EToTp.TextSize = 14.000
EToTp.TextWrapped = true
EToTp.MouseButton1Click:Connect(function()
	mouse = game.Players.LocalPlayer:GetMouse()
	tool = Instance.new("Tool")
	tool.RequiresHandle = false
	tool.Name = "Click Teleport"
	tool.Activated:connect(function()
		local pos = mouse.Hit+Vector3.new(0,2.5,0)
		pos = CFrame.new(pos.X,pos.Y,pos.Z)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = pos
	end)
	tool.Parent = game.Players.LocalPlayer.Backpack
end)
NoClip.Name = "No Clip"
NoClip.Parent = Test
NoClip.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
NoClip.Position = UDim2.new(0, 0, 0.715384662, 0)
NoClip.Size = UDim2.new(0, 142, 0, 50)
NoClip.Font = Enum.Font.SourceSans
NoClip.Text = "No clip"
NoClip.TextColor3 = Color3.fromRGB(0, 0, 0)
NoClip.TextScaled = true
NoClip.TextSize = 14.000
NoClip.TextWrapped = true
NoClip.MouseButton1Click:Connect(function()
	noclip = false
	game:GetService('RunService').Stepped:connect(function()
		if noclip then
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
		end
	end)
	plr = game.Players.LocalPlayer
	mouse = plr:GetMouse()
	mouse.KeyDown:connect(function(key)
		if key == "m" then
			noclip = not noclip
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
		end
	end)
	game.StarterGui:SetCore("SendNotification", {
		Title = "Noclip";
		Text = "Loaded.";
		Duration = "10";
	})
	wait(1)
	game.StarterGui:SetCore("SendNotification", {
		Title = "Noclip";
		Text = "Press m To Noclip";
		Duration = "10";
	})
end)
Teleport.Name = "Teleport"
Teleport.Parent = Test
Teleport.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Teleport.Position = UDim2.new(0.34887737, 0, 0.715384662, 0)
Teleport.Size = UDim2.new(0, 142, 0, 50)
Teleport.Font = Enum.Font.SourceSans
Teleport.Text = "Click To Delete"
Teleport.TextColor3 = Color3.fromRGB(0, 0, 0)
Teleport.TextScaled = true
Teleport.TextSize = 14.000
Teleport.TextWrapped = true
Teleport.MouseButton1Click:Connect(function()
	local Player = game:GetService("Players").LocalPlayer
	local Mouse = Player:GetMouse()

	Mouse.Button1Down:connect(function()
		if not game:GetService("UserInputService"):IsKeyDown(Enum.KeyCode.LeftAlt) and not game:GetService("UserInputService"):IsKeyDown(Enum.KeyCode.RightAlt)then return end
		if not Mouse.Target then return end
		Mouse.Target:Destroy()
	end)
end)
TeleportToPlayer.Name = "Teleport To Player"
TeleportToPlayer.Parent = Test
TeleportToPlayer.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TeleportToPlayer.Position = UDim2.new(0.34887737, 0, 0.43589747, 0)
TeleportToPlayer.Size = UDim2.new(0, 142, 0, 50)
TeleportToPlayer.Font = Enum.Font.SourceSans
TeleportToPlayer.Text = "Teleport To player"
TeleportToPlayer.TextColor3 = Color3.fromRGB(0, 0, 0)
TeleportToPlayer.TextScaled = true
TeleportToPlayer.TextSize = 14.000
TeleportToPlayer.TextWrapped = true
TeleportToPlayer.MouseButton1Click:Connect(function()
	-- Gui to Lua
	-- Version: 3.2

	-- Instances:

	local Tutorial = Instance.new("ScreenGui")
	local OpenFrame = Instance.new("Frame")
	local Open = Instance.new("TextButton")
	local Main = Instance.new("Frame")
	local TextLabel = Instance.new("TextLabel")
	local TextLabel_2 = Instance.new("TextLabel")
	local Close = Instance.new("TextButton")
	local ImageLabel = Instance.new("ImageLabel")
	local Teleport = Instance.new("TextButton")
	local TextLabel_3 = Instance.new("TextLabel")
	local TextBox = Instance.new("TextBox")

	--Properties:

	Tutorial.Name = "Tutorial"
	Tutorial.Parent = game.CoreGui

	OpenFrame.Name = "OpenFrame"
	OpenFrame.Parent = Tutorial
	OpenFrame.Active = true
	OpenFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	OpenFrame.BackgroundTransparency = 0.500
	OpenFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
	OpenFrame.Position = UDim2.new(0.891908348, 0, 0.654420495, 0)
	OpenFrame.Size = UDim2.new(0, 100, 0, 50)

	Open.Name = "Open"
	Open.Parent = OpenFrame
	Open.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	Open.BackgroundTransparency = 0.500
	Open.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Open.Position = UDim2.new(-0.000202026364, 0, -0.00305725099, 0)
	Open.Size = UDim2.new(0, 100, 0, 50)
	Open.Font = Enum.Font.Sarpanch
	Open.Text = "Open"
	Open.TextColor3 = Color3.fromRGB(255, 255, 255)
	Open.TextScaled = true
	Open.TextSize = 14.000
	Open.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
	Open.TextWrapped = true
	Open.MouseButton1Down:connect(function()
		Main.Visible = true
		OpenFrame.Visible = false
	end)

	Main.Name = "Main"
	Main.Parent = Tutorial
	Main.Active = true
	Main.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	Main.BackgroundTransparency = 0.500
	Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Main.Position = UDim2.new(0.206340134, 0, 0.291599989, 0)
	Main.Size = UDim2.new(0, 583, 0, 332)
	Main.Visible = false
	Main.Draggable = true

	TextLabel.Parent = Main
	TextLabel.Active = true
	TextLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel.BackgroundTransparency = 0.500
	TextLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel.Position = UDim2.new(0, 0, -0.00052341976, 0)
	TextLabel.Size = UDim2.new(0, 583, 0, 50)
	TextLabel.Font = Enum.Font.SourceSansItalic
	TextLabel.Text = "Teleport Player GUI"
	TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel.TextScaled = true
	TextLabel.TextSize = 14.000
	TextLabel.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel.TextWrapped = true

	TextLabel_2.Parent = Main
	TextLabel_2.Active = true
	TextLabel_2.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel_2.BackgroundTransparency = 0.500
	TextLabel_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel_2.Position = UDim2.new(0, 0, 0.850090206, 0)
	TextLabel_2.Size = UDim2.new(0, 583, 0, 50)
	TextLabel_2.Font = Enum.Font.SourceSansItalic
	TextLabel_2.Text = "GUI Maker : Ahmed_Prowy"
	TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_2.TextScaled = true
	TextLabel_2.TextSize = 14.000
	TextLabel_2.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_2.TextWrapped = true

	Close.Name = "Close"
	Close.Parent = Main
	Close.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	Close.BackgroundTransparency = 0.500
	Close.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Close.Position = UDim2.new(0.914032459, 0, -0.000113993883, 0)
	Close.Size = UDim2.new(0, 50, 0, 50)
	Close.Font = Enum.Font.SourceSansSemibold
	Close.Text = "X"
	Close.TextColor3 = Color3.fromRGB(255, 255, 255)
	Close.TextSize = 50.000
	Close.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
	Close.MouseButton1Down:connect(function()
		OpenFrame.Visible = true
		Main.Visible = false
	end)

	ImageLabel.Parent = Main
	ImageLabel.Active = true
	ImageLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	ImageLabel.BackgroundTransparency = 1.000
	ImageLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
	ImageLabel.Position = UDim2.new(-5.47013187e-05, 0, -0.00138611393, 0)
	ImageLabel.Size = UDim2.new(0, 75, 0, 50)
	ImageLabel.Image = "http://www.roblox.com/asset/?id=6830485913"

	Teleport.Name = "Teleport"
	Teleport.Parent = Main
	Teleport.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	Teleport.BackgroundTransparency = 0.500
	Teleport.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Teleport.Position = UDim2.new(0.217702299, 0, 0.640216887, 0)
	Teleport.Size = UDim2.new(0, 328, 0, 49)
	Teleport.Font = Enum.Font.Roboto
	Teleport.Text = "Teleport"
	Teleport.TextColor3 = Color3.fromRGB(255, 255, 255)
	Teleport.TextSize = 40.000
	Teleport.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
	Teleport.TextWrapped = true
	Teleport.MouseButton1Click:connect(function()
		local tp_namedplayer = TextBox.Text
		local tp_player = game:GetService("Players")[tp_namedplayer]
		local PLR = game:GetService("Players").LocalPlayer
		local p = TextBox.Text

		if tp_player then
			for i = 1,1 do
				wait(.08)
				PLR.Character.HumanoidRootPart.CFrame = tp_player.Character.HumanoidRootPart.CFrame + Vector3.new(0, 0, -1)
			end
		end
	end)

	TextLabel_3.Parent = Main
	TextLabel_3.Active = true
	TextLabel_3.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel_3.BackgroundTransparency = 1.000
	TextLabel_3.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel_3.Position = UDim2.new(0.106525294, 0, 0.148282975, 0)
	TextLabel_3.Size = UDim2.new(0, 458, 0, 79)
	TextLabel_3.Font = Enum.Font.Roboto
	TextLabel_3.Text = "Enter The Players Name Here"
	TextLabel_3.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_3.TextScaled = true
	TextLabel_3.TextSize = 40.000
	TextLabel_3.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_3.TextWrapped = true

	TextBox.Parent = Main
	TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextBox.BackgroundTransparency = 0.700
	TextBox.Position = UDim2.new(0.217702314, 0, 0.423602074, 0)
	TextBox.Size = UDim2.new(0, 329, 0, 50)
	TextBox.Font = Enum.Font.Roboto
	TextBox.Text = "Player"
	TextBox.TextColor3 = Color3.fromRGB(0, 0, 0)
	TextBox.TextSize = 40.000
end)
Speed.Name = "Speed "
Speed.Parent = Test
Speed.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Speed.Position = UDim2.new(0.34887737, 0, 0.169230789, 0)
Speed.Size = UDim2.new(0, 142, 0, 50)
Speed.Font = Enum.Font.SourceSans
Speed.Text = "Speed"
Speed.TextColor3 = Color3.fromRGB(0, 0, 0)
Speed.TextScaled = true
Speed.TextSize = 14.000
Speed.TextWrapped = true
Speed.MouseButton1Click:Connect(function()
	local Hacks = Instance.new("ScreenGui")
	local Background = Instance.new("Frame")
	local Walkspeedlb = Instance.new("TextLabel")
	local jumppowerlb = Instance.new("TextLabel")
	local speed = Instance.new("TextLabel")
	local jump = Instance.new("TextLabel")
	local WalkBox = Instance.new("TextBox")
	local JumpBox = Instance.new("TextBox")
	local WalkSumbit = Instance.new("TextButton")
	local JumpSumbit = Instance.new("TextButton")
	local TextLabel = Instance.new("TextLabel")
	local Open = Instance.new("TextButton")
	--Properties:
	Hacks.Name = "Hacks"
	Hacks.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
	Hacks.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	Background.Name = "Background"
	Background.Parent = Hacks
	Background.BackgroundColor3 = Color3.new(0, 0, 0)
	Background.BackgroundTransparency = 0.40000000596046
	Background.Position = UDim2.new(0.109510086, 0, 0.381112367, 0)
	Background.Size = UDim2.new(0.222958699, 0, 0.476163864, 0)
	Background.Visible = false

	Walkspeedlb.Name = "Walkspeedlb"
	Walkspeedlb.Parent = Background
	Walkspeedlb.BackgroundColor3 = Color3.new(1, 1, 1)
	Walkspeedlb.BackgroundTransparency = 1
	Walkspeedlb.Position = UDim2.new(0, 0, 0.122436516, 0)
	Walkspeedlb.Size = UDim2.new(0.999999762, 0, 0.100000001, 0)
	Walkspeedlb.Visible = false
	Walkspeedlb.Font = Enum.Font.SourceSans
	Walkspeedlb.Text = "WalkSpeed:"
	Walkspeedlb.TextColor3 = Color3.new(1, 1, 1)
	Walkspeedlb.TextScaled = true
	Walkspeedlb.TextSize = 14
	Walkspeedlb.TextWrapped = true
	Walkspeedlb.TextXAlignment = Enum.TextXAlignment.Left

	jumppowerlb.Name = "jumppowerlb"
	jumppowerlb.Parent = Background
	jumppowerlb.BackgroundColor3 = Color3.new(1, 1, 1)
	jumppowerlb.BackgroundTransparency = 1
	jumppowerlb.Position = UDim2.new(0, 0, 0.2203857, 0)
	jumppowerlb.Size = UDim2.new(0.999999762, 0, 0.100000001, 0)
	jumppowerlb.Visible = false
	jumppowerlb.Font = Enum.Font.SourceSans
	jumppowerlb.Text = "Jump Power:"
	jumppowerlb.TextColor3 = Color3.new(1, 1, 1)
	jumppowerlb.TextScaled = true
	jumppowerlb.TextSize = 14
	jumppowerlb.TextWrapped = true
	jumppowerlb.TextXAlignment = Enum.TextXAlignment.Left

	speed.Name = "speed"
	speed.Parent = Background
	speed.BackgroundColor3 = Color3.new(1, 1, 1)
	speed.BackgroundTransparency = 1
	speed.Position = UDim2.new(0.577337444, 0, 0.122436516, 0)
	speed.Size = UDim2.new(0.422662586, 0, 0.100000001, 0)
	speed.Visible = false
	speed.Font = Enum.Font.SourceSans
	speed.Text = "Default"
	speed.TextColor3 = Color3.new(1, 1, 1)
	speed.TextScaled = true
	speed.TextSize = 14
	speed.TextWrapped = true

	jump.Name = "jump"
	jump.Parent = Background
	jump.BackgroundColor3 = Color3.new(1, 1, 1)
	jump.BackgroundTransparency = 1
	jump.Position = UDim2.new(0.659198582, 0, 0.22038573, 0)
	jump.Size = UDim2.new(0.340801179, 0, 0.100000001, 0)
	jump.Visible = false
	jump.Font = Enum.Font.SourceSans
	jump.Text = "Default"
	jump.TextColor3 = Color3.new(1, 1, 1)
	jump.TextScaled = true
	jump.TextSize = 14
	jump.TextWrapped = true

	WalkBox.Name = "WalkBox"
	WalkBox.Parent = Background
	WalkBox.BackgroundColor3 = Color3.new(0.333333, 0.333333, 0.333333)
	WalkBox.BackgroundTransparency = 0.5
	WalkBox.BorderSizePixel = 0
	WalkBox.Position = UDim2.new(0, 0, 0.174571082, 0)
	WalkBox.Size = UDim2.new(0.999999881, 0, 0.187969327, 0)
	WalkBox.Font = Enum.Font.SourceSans
	WalkBox.PlaceholderColor3 = Color3.new(1, 1, 1)
	WalkBox.PlaceholderText = "Insert a number for walk speed"
	WalkBox.Text = ""
	WalkBox.TextColor3 = Color3.new(1, 1, 1)
	WalkBox.TextScaled = true
	WalkBox.TextSize = 14
	WalkBox.TextWrapped = true

	JumpBox.Name = "JumpBox"
	JumpBox.Parent = Background
	JumpBox.BackgroundColor3 = Color3.new(0.333333, 0.333333, 0.333333)
	JumpBox.BackgroundTransparency = 0.5
	JumpBox.BorderSizePixel = 0
	JumpBox.Position = UDim2.new(0.00430848775, 0, 0.6280002, 0)
	JumpBox.Size = UDim2.new(0.999999881, 0, 0.190235019, 0)
	JumpBox.Font = Enum.Font.SourceSans
	JumpBox.PlaceholderColor3 = Color3.new(1, 1, 1)
	JumpBox.PlaceholderText = "Insert a number for jump power"
	JumpBox.Text = ""
	JumpBox.TextColor3 = Color3.new(1, 1, 1)
	JumpBox.TextScaled = true
	JumpBox.TextSize = 14
	JumpBox.TextWrapped = true

	WalkSumbit.Name = "WalkSumbit"
	WalkSumbit.Parent = Background
	WalkSumbit.BackgroundColor3 = Color3.new(0.0980392, 1, 0)
	WalkSumbit.Position = UDim2.new(0.00430848775, 0, 0.402936816, 0)
	WalkSumbit.Size = UDim2.new(0.995691121, 0, 0.155913889, 0)
	WalkSumbit.Font = Enum.Font.SourceSans
	WalkSumbit.Text = "Sumbit"
	WalkSumbit.TextColor3 = Color3.new(0, 0, 0)
	WalkSumbit.TextScaled = true
	WalkSumbit.TextSize = 14
	WalkSumbit.TextWrapped = true

	JumpSumbit.Name = "JumpSumbit"
	JumpSumbit.Parent = Background
	JumpSumbit.BackgroundColor3 = Color3.new(0.0980392, 1, 0)
	JumpSumbit.Position = UDim2.new(0, 0, 0.84706986, 0)
	JumpSumbit.Size = UDim2.new(0.995691121, 0, 0.151039571, 0)
	JumpSumbit.Font = Enum.Font.SourceSans
	JumpSumbit.Text = "Sumbit"
	JumpSumbit.TextColor3 = Color3.new(0, 0, 0)
	JumpSumbit.TextScaled = true
	JumpSumbit.TextSize = 14
	JumpSumbit.TextWrapped = true

	TextLabel.Parent = Background
	TextLabel.BackgroundColor3 = Color3.new(1, 1, 1)
	TextLabel.BackgroundTransparency = 1
	TextLabel.Size = UDim2.new(0.995690882, 0, 0.135462731, 0)
	TextLabel.Font = Enum.Font.SourceSans
	TextLabel.Text = "Created By DariuZzZ"
	TextLabel.TextColor3 = Color3.new(1, 1, 1)
	TextLabel.TextScaled = true
	TextLabel.TextSize = 14
	TextLabel.TextWrapped = true

	Open.Name = "Open"
	Open.Parent = Hacks
	Open.BackgroundColor3 = Color3.new(0, 0, 0)
	Open.BackgroundTransparency = 0.44999998807907
	Open.Position = UDim2.new(0, 0, 0.756052136, 0)
	Open.Size = UDim2.new(0.100000001, 0, 0.0553072728, 0)
	Open.Font = Enum.Font.SourceSans
	Open.Text = "Open"
	Open.TextColor3 = Color3.new(1, 1, 1)
	Open.TextScaled = true
	Open.TextSize = 14
	Open.TextWrapped = true
	-- Scripts:

	local playername = game.Players.LocalPlayer.Name
	local player = game.Players.LocalPlayer
	local character = game.Workspace[playername]
	local Background = player.PlayerGui.Hacks.Background

	Open.MouseButton1Click:Connect(function()
		if game.Players.LocalPlayer.PlayerGui.Hacks.Background.Visible == true then
			game.Players.LocalPlayer.PlayerGui.Hacks.Open.Text = "Open"
			game.Players.LocalPlayer.PlayerGui.Hacks.Background.Visible = false
		else
			game.Players.LocalPlayer.PlayerGui.Hacks.Open.Text = "Close"
			game.Players.LocalPlayer.PlayerGui.Hacks.Background.Visible = true
		end
	end)

	WalkSumbit.MouseButton1Click:connect(function()
		character.Humanoid.WalkSpeed = tostring(Background.WalkBox.Text)
	end)

	JumpSumbit.MouseButton1Click:connect(function()
		character.Humanoid.JumpPower = tostring(Background.JumpBox.Text)
	end)
	Print("Cheats Got Executed")
end)
ESP.Name = "ESP"
ESP.Parent = Test
ESP.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ESP.Position = UDim2.new(0.675302207, 0, 0.169230789, 0)
ESP.Size = UDim2.new(0, 142, 0, 50)
ESP.Font = Enum.Font.SourceSans
ESP.Text = "ESP"
ESP.TextColor3 = Color3.fromRGB(0, 0, 0)
ESP.TextScaled = true
ESP.TextSize = 14.000
ESP.TextWrapped = true
ESP.MouseButton1Click:Connect(function()
	local custom_theme = {} --soon

	local function CreateInstance(cls,props)
		local inst = Instance.new(cls)
		for i,v in pairs(props) do
			inst[i] = v
		end
		return inst
	end

	local age1 = CreateInstance('ScreenGui',{DisplayOrder=0,Enabled=true,ResetOnSpawn=true,Name='age1', Parent=game.CoreGui})
	local p_visuals = CreateInstance('Frame',{Style=Enum.FrameStyle.Custom,Active=true,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=2,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 50, 0, 60),Rotation=0,Selectable=false,Size=UDim2.new(0, 200, 0, 254),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name = 'p_visuals',Parent = age1})
	local UIListLayout = CreateInstance('UIListLayout', {Padding = UDim.new(0, 1), FillDirection = Enum.FillDirection.Vertical, HorizontalAlignment = Enum.HorizontalAlignment.Left, SortOrder = Enum.SortOrder.LayoutOrder, VerticalAlignment = Enum.VerticalAlignment.Top, Name = 'UIListLayout', Parent = p_visuals })
	local title1 = CreateInstance('TextLabel',{Font=Enum.Font.GothamBlack,FontSize=Enum.FontSize.Size18,Text='Player visuals',TextColor3=Color3.new(1, 1, 1),TextScaled=false,TextSize=18,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, 0, 0, 24),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='title1',Parent = p_visuals})
	local b_b = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Bounding box',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_b',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_b})
	local b_f = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Fill alpha',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_f',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_f})
	local b_rt = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Render team',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_rt',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_rt})
	local b_tc = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Use TeamColor',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_tc',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_tc})
	local b_sn = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Show name',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_sn',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_sn})
	local b_sd = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Show distance',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_sd',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_sd})
	local b_sh = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Show health',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_sh',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='OFF',TextColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_sh})
	local b_ht = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Health type',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_ht',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Text',TextColor3=Color3.new(0, 1, 1),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_ht})
	local b_f_t = CreateInstance('TextButton',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Fill transparency',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,AutoButtonColor=true,Modal=false,Selected=false,Style=Enum.ButtonStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_f_t',Parent = p_visuals})
	local v = CreateInstance('TextLabel',{Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,Text='1',TextColor3=Color3.new(0, 1, 1),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Right,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, 0, 0, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 18, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='v',Parent = b_f_t})
	local title1_2 = CreateInstance('TextLabel',{Font=Enum.Font.SourceSansBold,FontSize=Enum.FontSize.Size18,Text='ESP',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=18,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, 0, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='title1_2',Parent = p_visuals})
	local b_ct = CreateInstance('TextLabel',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Team color',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_ct',Parent = p_visuals})
	local ct_b = CreateInstance('TextBox',{ClearTextOnFocus=true,Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,MultiLine=false,Text='',TextColor3=Color3.new(0, 0, 1), PlaceholderText='', PlaceholderColor3=Color3.new(0, 0, 1),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, -2, 0, 2),Rotation=0,Selectable=true,Size=UDim2.new(0, 27, 0, 14),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='ct_b',Parent = b_ct})
	local ct_g = CreateInstance('TextBox',{ClearTextOnFocus=true,Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,MultiLine=false,Text='',TextColor3=Color3.new(0, 1, 0), PlaceholderText='', PlaceholderColor3=Color3.new(0, 1, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, -29, 0, 2),Rotation=0,Selectable=true,Size=UDim2.new(0, 27, 0, 14),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='ct_g',Parent = b_ct})
	local ct_r = CreateInstance('TextBox',{ClearTextOnFocus=true,Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,MultiLine=false,Text='',TextColor3=Color3.new(1, 0, 0), PlaceholderText='', PlaceholderColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, -56, 0, 2),Rotation=0,Selectable=true,Size=UDim2.new(0, 27, 0, 14),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='ct_r',Parent = b_ct})
	local b_ce = CreateInstance('TextLabel',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size18,Text='Enemy color',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=16,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 0, 0.498039),BackgroundTransparency=1,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=0,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 0, 0, 0),Rotation=0,Selectable=true,Size=UDim2.new(1, -2, 0, 18),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='b_ce',Parent = p_visuals})
	local ce_b = CreateInstance('TextBox',{ClearTextOnFocus=true,Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,MultiLine=false,Text='',TextColor3=Color3.new(0, 0, 1), PlaceholderText='', PlaceholderColor3=Color3.new(0, 0, 1),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, -2, 0, 2),Rotation=0,Selectable=true,Size=UDim2.new(0, 27, 0, 14),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='ce_b',Parent = b_ce})
	local ce_g = CreateInstance('TextBox',{ClearTextOnFocus=true,Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,MultiLine=false,Text='',TextColor3=Color3.new(0, 1, 0), PlaceholderText='', PlaceholderColor3=Color3.new(0, 1, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, -29, 0, 2),Rotation=0,Selectable=true,Size=UDim2.new(0, 27, 0, 14),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='ce_g',Parent = b_ce})
	local ce_r = CreateInstance('TextBox',{ClearTextOnFocus=true,Font=Enum.Font.Gotham,FontSize=Enum.FontSize.Size14,MultiLine=false,Text='',TextColor3=Color3.new(1, 0, 0), PlaceholderText='', PlaceholderColor3=Color3.new(1, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=true,AnchorPoint=Vector2.new(1, 0),BackgroundColor3=Color3.new(0.121569, 0.12549, 0.172549),BackgroundTransparency=0,BorderColor3=Color3.new(1, 0, 0.498039),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(1, -56, 0, 2),Rotation=0,Selectable=true,Size=UDim2.new(0, 27, 0, 14),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='ce_r',Parent = b_ce})
	local watermark = CreateInstance('TextLabel',{Font=Enum.Font.Code,FontSize=Enum.FontSize.Size14,Text='lamehaxx v0.01',TextColor3=Color3.new(0, 0, 0),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Top,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, 2, 0, -34),Rotation=0,Selectable=false,Size=UDim2.new(0, 200, 0, 20),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=20,Name='watermark',Parent = age1})
	local watermark1 = CreateInstance('TextLabel',{Font=Enum.Font.Code,FontSize=Enum.FontSize.Size14,Text='lamehaxx v0.01',TextColor3=Color3.new(1, 0, 0.498039),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=0,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Left,TextYAlignment=Enum.TextYAlignment.Top,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(1, 1, 1),BackgroundTransparency=1,BorderColor3=Color3.new(0.105882, 0.164706, 0.207843),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0, -2, 0, -2),Rotation=0,Selectable=false,Size=UDim2.new(0, 200, 0, 20),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=20,Name='watermark1',Parent = watermark})
	p_visuals.Draggable = true

	title1.LayoutOrder = 0 title1_2.LayoutOrder = 1
	b_b.LayoutOrder = 1 b_f.LayoutOrder = 2 b_f_t.LayoutOrder = 3 b_sd.LayoutOrder = 4 b_sn.LayoutOrder = 5 b_sh.LayoutOrder = 6 b_ht.LayoutOrder = 7 b_rt.LayoutOrder = 8 b_tc.LayoutOrder = 9 b_ct.LayoutOrder = 10 b_ce.LayoutOrder = 11

	local localplayer = game:GetService"Players".LocalPlayer
	local uis = game:GetService"UserInputService"

	local cheats = {
		b_b = false;
		b_f = false;
		b_f_t = 1;
		b_sd = false;
		b_sn = false;
		b_sh = false;
		b_ht = "Text";
		b_rt = false;
		b_tc = false;
	}

	local cheatsf = Instance.new("Folder", game.CoreGui) cheatsf.Name = "cheats"
	local espf = Instance.new("Folder", cheatsf) espf.Name = "esp"

	function addEsp(player)
		local bbg = Instance.new("BillboardGui", espf)
		bbg.Name = player.Name
		bbg.AlwaysOnTop = true
		bbg.Size = UDim2.new(4,0,5.4,0)
		bbg.ClipsDescendants = false

		local outlines = Instance.new("Frame", bbg)
		outlines.Size = UDim2.new(1,0,1,0)
		outlines.BorderSizePixel = 0
		outlines.BackgroundTransparency = 1
		local left = Instance.new("Frame", outlines)
		left.BorderSizePixel = 0
		left.Size = UDim2.new(0,1,1,0)
		local right = left:Clone()
		right.Parent = outlines
		right.Size = UDim2.new(0,-1,1,0)
		right.Position = UDim2.new(1,0,0,0)
		local up = left:Clone()
		up.Parent = outlines
		up.Size = UDim2.new(1,0,0,1)
		local down = left:Clone()
		down.Parent = outlines
		down.Size = UDim2.new(1,0,0,-1)
		down.Position = UDim2.new(0,0,1,0)

		local info = Instance.new("BillboardGui", bbg)
		info.Name = "info"
		info.Size = UDim2.new(3,0,0,54)
		info.StudsOffset = Vector3.new(3.6,-3,0)
		info.AlwaysOnTop = true
		info.ClipsDescendants = false
		local namelabel = Instance.new("TextLabel", info)
		namelabel.Name = "namelabel"
		namelabel.BackgroundTransparency = 1
		namelabel.TextStrokeTransparency = 0
		namelabel.TextXAlignment = Enum.TextXAlignment.Left
		namelabel.Size = UDim2.new(0,100,0,18)
		namelabel.Position = UDim2.new(0,0,0,0)
		namelabel.Text = player.Name
		local distancel = Instance.new("TextLabel", info)
		distancel.Name = "distancelabel"
		distancel.BackgroundTransparency = 1
		distancel.TextStrokeTransparency = 0
		distancel.TextXAlignment = Enum.TextXAlignment.Left
		distancel.Size = UDim2.new(0,100,0,18)
		distancel.Position = UDim2.new(0,0,0,18)
		local healthl = Instance.new("TextLabel", info)
		healthl.Name = "healthlabel"
		healthl.BackgroundTransparency = 1
		healthl.TextStrokeTransparency = 0
		healthl.TextXAlignment = Enum.TextXAlignment.Left
		healthl.Size = UDim2.new(0,100,0,18)
		healthl.Position = UDim2.new(0,0,0,36)

		local uill = Instance.new("UIListLayout", info)

		local forhealth = Instance.new("BillboardGui", bbg)
		forhealth.Name = "forhealth"
		forhealth.Size = UDim2.new(5,0,6,0)
		forhealth.AlwaysOnTop = true
		forhealth.ClipsDescendants = false

		local healthbar = Instance.new("Frame", forhealth)
		healthbar.Name = "healthbar"
		healthbar.BackgroundColor3 = Color3.fromRGB(40,40,40)
		healthbar.BorderColor3 = Color3.fromRGB(0,0,0)
		healthbar.Size = UDim2.new(0.04,0,0.9,0)
		healthbar.Position = UDim2.new(0,0,0.05,0)
		local bar = Instance.new("Frame", healthbar)
		bar.Name = "bar"
		bar.BorderSizePixel = 0
		bar.BackgroundColor3 = Color3.fromRGB(94,255,69)
		bar.AnchorPoint = Vector2.new(0,1)
		bar.Position = UDim2.new(0,0,1,0)
		bar.Size = UDim2.new(1,0,1,0)

		local co = coroutine.create(function()
			while wait(0.1) do
				if (player.Character and player.Character:FindFirstChild"HumanoidRootPart") then
					bbg.Adornee = player.Character.HumanoidRootPart
					info.Adornee = player.Character.HumanoidRootPart
					forhealth.Adornee = player.Character.HumanoidRootPart

					if (player.Team ~= localplayer.Team) then
						bbg.Enabled = true
						info.Enabled = true
						forhealth.Enabled = true
					end
					if player.Character:FindFirstChild("ForceField") then
						outlines.BackgroundTransparency = 0.4
						left.BackgroundTransparency = 0.4
						right.BackgroundTransparency = 0.4
						up.BackgroundTransparency = 0.4
						down.BackgroundTransparency = 0.4
						healthl.TextTransparency = 0.4
						healthl.TextStrokeTransparency = 0.8
						distancel.TextTransparency = 0.4
						distancel.TextStrokeTransparency = 0.8
						namelabel.TextTransparency = 0.4
						namelabel.TextStrokeTransparency = 0.8
						bar.BackgroundTransparency = 0.4
						healthbar.BackgroundTransparency = 0.8
					else
						outlines.BackgroundTransparency = 0
						left.BackgroundTransparency = 0
						right.BackgroundTransparency = 0
						up.BackgroundTransparency = 0
						down.BackgroundTransparency = 0
						healthl.TextTransparency = 0
						healthl.TextStrokeTransparency = 0
						distancel.TextTransparency = 0
						distancel.TextStrokeTransparency = 0
						namelabel.TextTransparency = 0
						namelabel.TextStrokeTransparency = 0
						bar.BackgroundTransparency = 0
						healthbar.BackgroundTransparency = 0
					end
					if cheats.b_b == true then
						outlines.Visible = true
					else
						outlines.Visible = false
					end
					if cheats.b_f == true then
						if player.Character:FindFirstChild("ForceField") then
							outlines.BackgroundTransparency = 0.9
						else
							outlines.BackgroundTransparency = cheats.b_f_t
						end
					else
						outlines.BackgroundTransparency = 1
					end
					if cheats.b_sh == true then
						if (player.Character:FindFirstChild"Humanoid") then
							healthl.Text = "Health: "..math.floor(player.Character:FindFirstChild"Humanoid".Health)
							healthbar.bar.Size = UDim2.new(1,0,player.Character:FindFirstChild"Humanoid".Health/player.Character:FindFirstChild"Humanoid".MaxHealth,0)
						end
						if cheats.b_ht == "Text" then
							healthbar.Visible = false
							healthl.Visible = true
						end
						if cheats.b_ht == "Bar" then
							healthl.Visible = false
							healthbar.Visible = true
						end
						if cheats.b_ht == "Both" then
							healthl.Visible = true
							healthbar.Visible = true
						end
					else
						healthl.Visible = false
						healthbar.Visible = false
					end
					if cheats.b_sn then
						namelabel.Visible = true
					else
						namelabel.Visible = false
					end
					if cheats.b_sd == true then
						distancel.Visible = true
						if (localplayer.Character and localplayer.Character:FindFirstChild"HumanoidRootPart") then
							distancel.Text = "Distance: "..math.floor(0.5+(localplayer.Character:FindFirstChild"HumanoidRootPart".Position - player.Character:FindFirstChild"HumanoidRootPart".Position).magnitude)
						end
					else
						distancel.Visible = false
					end
					if cheats.b_rt == true then
						if (player.Team == localplayer.Team) then
							bbg.Enabled = true
							info.Enabled = true
							forhealth.Enabled = true
						end
					else
						if (player.Team == localplayer.Team) then
							bbg.Enabled = false
							info.Enabled = false
							forhealth.Enabled = false
						end
					end
					if cheats.b_tc == true then
						outlines.BackgroundColor3 = player.TeamColor.Color
						left.BackgroundColor3 = player.TeamColor.Color
						right.BackgroundColor3 = player.TeamColor.Color
						up.BackgroundColor3 = player.TeamColor.Color
						down.BackgroundColor3 = player.TeamColor.Color
						healthl.TextColor3 = player.TeamColor.Color
						distancel.TextColor3 = player.TeamColor.Color
						namelabel.TextColor3 = player.TeamColor.Color
					else
						if (player.Team == localplayer.Team) then
							outlines.BackgroundColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							left.BackgroundColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							right.BackgroundColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							up.BackgroundColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							down.BackgroundColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							healthl.TextColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							distancel.TextColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
							namelabel.TextColor3 = Color3.fromRGB(ct_r.Text, ct_g.Text, ct_b.Text)
						else
							outlines.BackgroundColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							left.BackgroundColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							right.BackgroundColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							up.BackgroundColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							down.BackgroundColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							healthl.TextColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							distancel.TextColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
							namelabel.TextColor3 = Color3.fromRGB(ce_r.Text, ce_g.Text, ce_b.Text)
						end
					end
				end
				if not (game:GetService"Players":FindFirstChild(player.Name)) then
					print(player.Name.." has left. Clearing esp.")
					espf:FindFirstChild(player.Name):Destroy()
					coroutine.yield()
				end
			end
		end)
		coroutine.resume(co)
	end

	--main
	do
		wait(2)
		--menu buttons
		for _,button in pairs(age1:GetDescendants()) do
			if button:IsA"TextButton" then
				button.MouseButton1Click:connect(function()
					if button.Name == "b_f_t" then
						if cheats.b_f_t >= 0 then
							cheats.b_f_t = cheats.b_f_t+0.1
							if cheats.b_f_t > 1 then
								cheats.b_f_t = 0
							end
						end
						button.v.Text = cheats.b_f_t
					elseif button.Name == "b_ht" then
						if cheats.b_ht == "Text" then
							cheats.b_ht = "Bar"
						elseif cheats.b_ht == "Bar" then
							cheats.b_ht = "Both"
						else
							cheats.b_ht = "Text"
						end
						button.v.Text = cheats.b_ht
					else
						if cheats[button.Name] == true then
							cheats[button.Name] = false
							button.v.Text = "OFF"
							button.v.TextColor3 = Color3.fromRGB(255,0,0)
						else
							cheats[button.Name] = true
							button.v.Text = "ON"
							button.v.TextColor3 = Color3.fromRGB(0,255,0)
						end
					end	
				end)
			end
		end

		--initial player addition
		for _,v in pairs(game:GetService("Players"):GetChildren()) do
			if not (v.Name == localplayer.Name) then
				if not (espf:FindFirstChild(v.Name)) then
					addEsp(v)
				end
			end
		end

		--open/close gui
		game:GetService("UserInputService").InputBegan:connect(function(input, gameProcessed)
			if input.KeyCode == Enum.KeyCode.KeypadOne then
				if not gameProcessed then
					age1.Enabled = not age1.Enabled
				end
			end
		end)

		--auto-update
		while wait(10) do
			for _,v in pairs(game:GetService("Players"):GetChildren()) do
				if not (v.Name == localplayer.Name) then
					if not (espf:FindFirstChild(v.Name)) then
						addEsp(v)
					end
				end
			end
		end
	end
end)
Aimbot.Name = "Aimbot"
Aimbot.Parent = Test
Aimbot.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Aimbot.Position = UDim2.new(0.675302207, 0, 0.43589747, 0)
Aimbot.Size = UDim2.new(0, 142, 0, 50)
Aimbot.Font = Enum.Font.SourceSans
Aimbot.Text = "Aimbot"
Aimbot.TextColor3 = Color3.fromRGB(0, 0, 0)
Aimbot.TextScaled = true
Aimbot.TextSize = 14.000
Aimbot.TextWrapped = true
Aimbot.MouseButton1Click:Connect(function()
	--Not made by me
	local espcolor = Color3.fromRGB(140, 69, 102)
	local wallhack_esp_transparency = .4
	local gui_hide_button = {Enum.KeyCode.LeftControl, "h"}
	local plrs = game:GetService("Players")
	local lplr = game:GetService("Players").LocalPlayer
	local TeamBased = true ; local teambasedswitch = "o"
	local presskeytoaim = true; local aimkey = "e"
	aimbothider = false; aimbothiderspeed = .5
	local Aim_Assist = false ; Aim_Assist_Key = {Enum.KeyCode.LeftControl, "z"}
	local espupdatetime = 5; autoesp = false
	local abs = math.abs
	local mouselock = false
	local canaimat = true
	local lockaim = true; local lockangle = 5
	local ver = "2"
	local cam = game.Workspace.CurrentCamera
	local BetterDeathCount = true


	local mouse = lplr:GetMouse()
	local switch = false
	local key = "k"
	local aimatpart = nil

	local CCAimbot = Instance.new("ScreenGui")
	local AimbotFrame = Instance.new("Frame")
	local MainAimbotFrame = Instance.new("Frame")
	local N2 = Instance.new("Frame")
	local CheatType = Instance.new("TextLabel")
	local N2_2 = Instance.new("Frame")
	local CheatType_2 = Instance.new("TextLabel")
	local N1 = Instance.new("Frame")
	local CheatType_3 = Instance.new("TextLabel")
	local C5 = Instance.new("Frame")
	local Letters = Instance.new("TextLabel")
	local CheatType_4 = Instance.new("TextLabel")
	local C4 = Instance.new("Frame")
	local Letters_2 = Instance.new("TextLabel")
	local CheatType_5 = Instance.new("TextLabel")
	local C3 = Instance.new("Frame")
	local Letters_3 = Instance.new("TextLabel")
	local CheatType_6 = Instance.new("TextLabel")
	local C2 = Instance.new("Frame")
	local Letters_4 = Instance.new("TextLabel")
	local CheatType_7 = Instance.new("TextLabel")
	local C1 = Instance.new("Frame")
	local Letters_5 = Instance.new("TextLabel")
	local CheatType_8 = Instance.new("TextLabel")
	local TabFrame = Instance.new("Frame")
	local Title = Instance.new("TextLabel")
	local Exit = Instance.new("TextButton")
	local Hide = Instance.new("TextButton")

	--Properties:

	CCAimbot.Name = "CCAimbot"
	CCAimbot.Parent = game.CoreGui

	AimbotFrame.Name = "AimbotFrame"
	AimbotFrame.Parent = CCAimbot
	AimbotFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	AimbotFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	AimbotFrame.BackgroundTransparency = 1.000
	AimbotFrame.BorderSizePixel = 0
	AimbotFrame.ClipsDescendants = true
	AimbotFrame.Position = UDim2.new(0.5, 0, 0.479495257, 0)
	AimbotFrame.Size = UDim2.new(0, 195, 0, 259)

	MainAimbotFrame.Name = "MainAimbotFrame"
	MainAimbotFrame.Parent = AimbotFrame
	MainAimbotFrame.BackgroundColor3 = Color3.fromRGB(23, 24, 28)
	MainAimbotFrame.BorderSizePixel = 0
	MainAimbotFrame.ClipsDescendants = true
	MainAimbotFrame.Position = UDim2.new(-0.00256413221, 0, 0.0464286208, 0)
	MainAimbotFrame.Size = UDim2.new(0, 195, 0, 245)

	N2.Name = "N2"
	N2.Parent = MainAimbotFrame
	N2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	N2.BackgroundTransparency = 1.000
	N2.BorderSizePixel = 0
	N2.Position = UDim2.new(0, 0, 0.562231719, 0)
	N2.Size = UDim2.new(1, 0, 0.100000001, 0)

	CheatType.Name = "CheatType"
	CheatType.Parent = N2
	CheatType.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType.BackgroundTransparency = 1.000
	CheatType.BorderSizePixel = 0
	CheatType.Position = UDim2.new(0, 0, 2.03163123, 0)
	CheatType.Size = UDim2.new(1, 0, 1.05753362, 0)
	CheatType.Font = Enum.Font.GothamBlack
	CheatType.Text = "ESP Loop : False"
	CheatType.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType.TextSize = 15.000
	CheatType.TextWrapped = true

	N2_2.Name = "N2"
	N2_2.Parent = MainAimbotFrame
	N2_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	N2_2.BackgroundTransparency = 1.000
	N2_2.BorderSizePixel = 0
	N2_2.Position = UDim2.new(0, 0, 0.935622334, 0)
	N2_2.Size = UDim2.new(1, 0, 0.0613734461, 0)

	CheatType_2.Name = "CheatType"
	CheatType_2.Parent = N2_2
	CheatType_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_2.BackgroundTransparency = 1.000
	CheatType_2.BorderSizePixel = 0
	CheatType_2.Size = UDim2.new(1, 0, 1, 0)
	CheatType_2.Font = Enum.Font.Gotham
	CheatType_2.Text = "Letters Corrospond with Keybinds"
	CheatType_2.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_2.TextScaled = true
	CheatType_2.TextSize = 15.000
	CheatType_2.TextWrapped = true

	N1.Name = "N1"
	N1.Parent = MainAimbotFrame
	N1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	N1.BackgroundTransparency = 1.000
	N1.BorderSizePixel = 0
	N1.Position = UDim2.new(0, 0, 0.562231719, 0)
	N1.Size = UDim2.new(1, 0, 0.100000001, 0)

	CheatType_3.Name = "CheatType"
	CheatType_3.Parent = N1
	CheatType_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_3.BackgroundTransparency = 1.000
	CheatType_3.BorderSizePixel = 0
	CheatType_3.Position = UDim2.new(0, 0, 0.987714529, 0)
	CheatType_3.Size = UDim2.new(1, 0, 1.05753362, 0)
	CheatType_3.Font = Enum.Font.GothamBlack
	CheatType_3.Text = "Team Based : True"
	CheatType_3.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_3.TextSize = 15.000
	CheatType_3.TextWrapped = true

	C5.Name = "C5"
	C5.Parent = MainAimbotFrame
	C5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	C5.BackgroundTransparency = 1.000
	C5.BorderSizePixel = 0
	C5.Position = UDim2.new(-0.00512820529, 0, 0.459227443, 0)
	C5.Size = UDim2.new(1, 0, 0.100000001, 0)

	Letters.Name = "Letters"
	Letters.Parent = C5
	Letters.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Letters.BackgroundTransparency = 1.000
	Letters.BorderSizePixel = 0
	Letters.Position = UDim2.new(0.730999887, 0, 0.973926187, 0)
	Letters.Size = UDim2.new(0.263999999, 0, 1.05753362, 0)
	Letters.Font = Enum.Font.GothamBold
	Letters.Text = "O"
	Letters.TextColor3 = Color3.fromRGB(255, 255, 255)
	Letters.TextSize = 15.000
	Letters.TextWrapped = true

	CheatType_4.Name = "CheatType"
	CheatType_4.Parent = C5
	CheatType_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_4.BackgroundTransparency = 1.000
	CheatType_4.BorderSizePixel = 0
	CheatType_4.Position = UDim2.new(0.0307692308, 0, 0.97837925, 0)
	CheatType_4.Size = UDim2.new(0.699999988, 0, 1.05753362, 0)
	CheatType_4.Font = Enum.Font.GothamBold
	CheatType_4.Text = "Team Based"
	CheatType_4.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_4.TextSize = 15.000
	CheatType_4.TextWrapped = true
	CheatType_4.TextXAlignment = Enum.TextXAlignment.Left

	C4.Name = "C4"
	C4.Parent = MainAimbotFrame
	C4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	C4.BackgroundTransparency = 1.000
	C4.BorderSizePixel = 0
	C4.Position = UDim2.new(0, 0, 0.356223166, 0)
	C4.Size = UDim2.new(1, 0, 0.100000001, 0)

	Letters_2.Name = "Letters"
	Letters_2.Parent = C4
	Letters_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Letters_2.BackgroundTransparency = 1.000
	Letters_2.BorderSizePixel = 0
	Letters_2.Position = UDim2.new(0.730999887, 0, 0.914663553, 0)
	Letters_2.Size = UDim2.new(0.263999999, 0, 1.05753362, 0)
	Letters_2.Font = Enum.Font.GothamBold
	Letters_2.Text = "Y"
	Letters_2.TextColor3 = Color3.fromRGB(255, 255, 255)
	Letters_2.TextSize = 15.000
	Letters_2.TextWrapped = true

	CheatType_5.Name = "CheatType"
	CheatType_5.Parent = C4
	CheatType_5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_5.BackgroundTransparency = 1.000
	CheatType_5.BorderSizePixel = 0
	CheatType_5.Position = UDim2.new(0.0307692308, 0, 0.919116616, 0)
	CheatType_5.Size = UDim2.new(0.699999988, 0, 1.05753362, 0)
	CheatType_5.Font = Enum.Font.GothamBold
	CheatType_5.Text = "Aimbot Hider"
	CheatType_5.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_5.TextSize = 15.000
	CheatType_5.TextWrapped = true
	CheatType_5.TextXAlignment = Enum.TextXAlignment.Left

	C3.Name = "C3"
	C3.Parent = MainAimbotFrame
	C3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	C3.BackgroundTransparency = 1.000
	C3.BorderSizePixel = 0
	C3.Position = UDim2.new(0, 0, 0.253218889, 0)
	C3.Size = UDim2.new(1, 0, 0.100000001, 0)

	Letters_3.Name = "Letters"
	Letters_3.Parent = C3
	Letters_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Letters_3.BackgroundTransparency = 1.000
	Letters_3.BorderSizePixel = 0
	Letters_3.Position = UDim2.new(0.730999887, 0, 0.855401516, 0)
	Letters_3.Size = UDim2.new(0.263999999, 0, 1.05753362, 0)
	Letters_3.Font = Enum.Font.GothamBold
	Letters_3.Text = "L"
	Letters_3.TextColor3 = Color3.fromRGB(255, 255, 255)
	Letters_3.TextSize = 15.000
	Letters_3.TextWrapped = true

	CheatType_6.Name = "CheatType"
	CheatType_6.Parent = C3
	CheatType_6.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_6.BackgroundTransparency = 1.000
	CheatType_6.BorderSizePixel = 0
	CheatType_6.Position = UDim2.new(0.0307692308, 0, 0.859854579, 0)
	CheatType_6.Size = UDim2.new(0.699999988, 0, 1.05753362, 0)
	CheatType_6.Font = Enum.Font.GothamBold
	CheatType_6.Text = "ESP Loop"
	CheatType_6.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_6.TextSize = 15.000
	CheatType_6.TextWrapped = true
	CheatType_6.TextXAlignment = Enum.TextXAlignment.Left

	C2.Name = "C2"
	C2.Parent = MainAimbotFrame
	C2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	C2.BackgroundTransparency = 1.000
	C2.BorderSizePixel = 0
	C2.Position = UDim2.new(0, 0, 0.150214598, 0)
	C2.Size = UDim2.new(1, 0, 0.100000001, 0)

	Letters_4.Name = "Letters"
	Letters_4.Parent = C2
	Letters_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Letters_4.BackgroundTransparency = 1.000
	Letters_4.BorderSizePixel = 0
	Letters_4.Position = UDim2.new(0.730999887, 0, 0.796139479, 0)
	Letters_4.Size = UDim2.new(0.263999999, 0, 1.05753362, 0)
	Letters_4.Font = Enum.Font.GothamBold
	Letters_4.Text = "T"
	Letters_4.TextColor3 = Color3.fromRGB(255, 255, 255)
	Letters_4.TextSize = 15.000
	Letters_4.TextWrapped = true

	CheatType_7.Name = "CheatType"
	CheatType_7.Parent = C2
	CheatType_7.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_7.BackgroundTransparency = 1.000
	CheatType_7.BorderSizePixel = 0
	CheatType_7.Position = UDim2.new(0.0307692308, 0, 0.800592542, 0)
	CheatType_7.Size = UDim2.new(0.699999988, 0, 1.05753362, 0)
	CheatType_7.Font = Enum.Font.GothamBold
	CheatType_7.Text = "ESP"
	CheatType_7.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_7.TextSize = 15.000
	CheatType_7.TextWrapped = true
	CheatType_7.TextXAlignment = Enum.TextXAlignment.Left

	C1.Name = "C1"
	C1.Parent = MainAimbotFrame
	C1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	C1.BackgroundTransparency = 1.000
	C1.BorderSizePixel = 0
	C1.Position = UDim2.new(0, 0, 0.0472103022, 0)
	C1.Size = UDim2.new(1, 0, 0.100000001, 0)

	Letters_5.Name = "Letters"
	Letters_5.Parent = C1
	Letters_5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Letters_5.BackgroundTransparency = 1.000
	Letters_5.BorderSizePixel = 0
	Letters_5.Position = UDim2.new(0.730999887, 0, 0.736877441, 0)
	Letters_5.Size = UDim2.new(0.263999999, 0, 1.05753362, 0)
	Letters_5.Font = Enum.Font.GothamBold
	Letters_5.Text = "E"
	Letters_5.TextColor3 = Color3.fromRGB(255, 255, 255)
	Letters_5.TextSize = 15.000
	Letters_5.TextWrapped = true

	CheatType_8.Name = "CheatType"
	CheatType_8.Parent = C1
	CheatType_8.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_8.BackgroundTransparency = 1.000
	CheatType_8.BorderSizePixel = 0
	CheatType_8.Position = UDim2.new(0.0307692308, 0, 0.741330564, 0)
	CheatType_8.Size = UDim2.new(0.699999988, 0, 1.05753362, 0)
	CheatType_8.Font = Enum.Font.GothamBold
	CheatType_8.Text = "Lock-in Person"
	CheatType_8.TextColor3 = Color3.fromRGB(255, 255, 255)
	CheatType_8.TextSize = 15.000
	CheatType_8.TextWrapped = true
	CheatType_8.TextXAlignment = Enum.TextXAlignment.Left

	TabFrame.Name = "TabFrame"
	TabFrame.Parent = AimbotFrame
	TabFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	TabFrame.BackgroundColor3 = Color3.fromRGB(0, 237, 206)
	TabFrame.BorderSizePixel = 0
	TabFrame.ClipsDescendants = true
	TabFrame.Position = UDim2.new(0.497435898, 0, 0.0926640928, 0)
	TabFrame.Size = UDim2.new(1, 0, 0.100000001, 0)

	Title.Name = "Title"
	Title.Parent = TabFrame
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.BackgroundTransparency = 1.000
	Title.BorderSizePixel = 0
	Title.Position = UDim2.new(0.0307692308, 0, 0, 0)
	Title.Size = UDim2.new(0.41538462, 0, 1, 0)
	Title.Font = Enum.Font.GothamBold
	Title.Text = "CC AIMBOT"
	Title.TextColor3 = Color3.fromRGB(255, 255, 255)
	Title.TextSize = 14.000
	Title.TextXAlignment = Enum.TextXAlignment.Left

	Exit.Name = "Exit"
	Exit.Parent = TabFrame
	Exit.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Exit.BackgroundTransparency = 1.000
	Exit.BorderSizePixel = 0
	Exit.Position = UDim2.new(0.899999976, 0, 0, 0)
	Exit.Size = UDim2.new(0.100000001, 0, 1, 0)
	Exit.Font = Enum.Font.GothamBold
	Exit.Text = "X"
	Exit.TextColor3 = Color3.fromRGB(255, 255, 255)
	Exit.TextScaled = true
	Exit.TextSize = 14.000
	Exit.TextWrapped = true

	Hide.Name = "Hide"
	Hide.Parent = TabFrame
	Hide.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Hide.BackgroundTransparency = 1.000
	Hide.BorderSizePixel = 0
	Hide.Position = UDim2.new(0.79743588, 0, 0, 0)
	Hide.Size = UDim2.new(0.100000001, 0, 1, 0)
	Hide.Font = Enum.Font.GothamBold
	Hide.Text = "-"
	Hide.TextColor3 = Color3.fromRGB(255, 255, 255)
	Hide.TextScaled = true
	Hide.TextSize = 14.000
	Hide.TextWrapped = true

	-- Scripts:

	local function JLYIY_fake_script() -- Exit.LocalScript 
		local script = Instance.new('LocalScript', Exit)

		local b = script.Parent

		b.MouseButton1Down:connect(function()
			b.Parent.Parent.AnchorPoint = Vector2.new(0.5, 0.5)
			b.Parent.Parent:TweenSize(UDim2.new(0, 0, 0, 0), "In", 2, 0.5)
		end)
	end
	coroutine.wrap(JLYIY_fake_script)()
	local function CXSQXNO_fake_script() -- Hide.LocalScript 
		local script = Instance.new('LocalScript', Hide)

		local b = script.Parent
		local closed = false

		b.MouseButton1Down:connect(function()
			if closed == false then
				b.Parent.Parent.MainAimbotFrame:TweenSize(UDim2.new(0, 195, 0, 25), "Out", 1.5, 0.5)
				closed = true

			elseif closed == true then
				b.Parent.Parent.MainAimbotFrame:TweenSize(UDim2.new(0, 195, 0, 245), "Out", 1.5, 0.5)
				closed = false
			end

		end)
	end
	coroutine.wrap(CXSQXNO_fake_script)()

	f = {}
	local espforlder
	local partconverter = Instance.new("Part")

	f.addesp = function()
		pcall(function()
			--print("ESP ran")
			if espforlder then
				espforlder:Destroy()
				espforlder = Instance.new("Folder")
				espforlder.Parent = game.Workspace.CurrentCamera
			else
				espforlder = Instance.new("Folder")
				espforlder.Parent = game.Workspace.CurrentCamera
			end
			for i, v in pairs(espforlder:GetChildren()) do
				v:Destroy()
			end
			for _, plr in pairs(plrs:GetChildren()) do
				if plr.Character and plr.Character.Humanoid.Health > 0 and plr.Name ~= lplr.Name then
					if TeamBased == true then
						if plr.Team.Name ~= plrs.LocalPlayer.Team.Name  then
							local e = espforlder:FindFirstChild(plr.Name)
							if not e then
								local fold = Instance.new("Folder", espforlder)
								fold.Name = plr.Name

								--partconverter.BrickColor = plr.Team.Color
								--local teamc = partconverter.Color
								for i, p in pairs(plr.Character:GetChildren()) do
									if p:IsA("BasePart") and p.Name ~= "HumanoidRootPart" then
										local urmom = Instance.new("BoxHandleAdornment")
										urmom.ZIndex = 10
										urmom.AlwaysOnTop = true
										urmom.Color3 = espcolor
										urmom.Size = p.Size
										urmom.Adornee = p
										urmom.Name = tick().." Ur mom has big gay"
										urmom.Transparency = wallhack_esp_transparency
										urmom.Parent = fold

									end
								end
								plr.Character.Humanoid.Died:Connect(function()
									fold:Destroy()
								end)
							end
						end
					else
						local e = espforlder:FindFirstChild(plr.Name)
						if not e then
							local fold = Instance.new("Folder", espforlder)
							fold.Name = plr.Name

							--partconverter.BrickColor = plr.Team.Color
							--local teamc = Move.BackgroundColor3
							for i, p in pairs(plr.Character:GetChildren()) do
								if p:IsA("BasePart") and p.Name ~= "HumanoidRootPart" then
									local urmom = Instance.new("BoxHandleAdornment")
									urmom.ZIndex = 10
									urmom.AlwaysOnTop = true
									urmom.Color3 = espcolor
									urmom.Size = p.Size
									urmom.Adornee = p
									urmom.Name = tick().." Ur mom has big gay"
									urmom.Transparency = wallhack_esp_transparency
									urmom.Parent = fold
								end
							end
							plr.Character.Humanoid.Died:Connect(function()
								fold:Destroy()
							end)
						end
					end


				end
			end
		end)
	end
	local uis = game:GetService("UserInputService")
	local bringall = false
	local hided2 = false
	mouse.KeyDown:Connect(function(a)
		if a == "t" then
			--print("worked1")
			f.addesp()
		elseif a == gui_hide_button[2] and uis:IsKeyDown(gui_hide_button[1]) then
			if hided2 == false then
				hided2 = true
				autoesp =false
				if espforlder then
					espforlder:Destroy()
				end
				CCAimbot.Enabled = false
			else
				CCAimbot.Enabled = true
				hided2 = false
			end
		elseif a == "u" then
			if mouselock == false then
				mouselock = true
			else
				mouselock = false
			end
		elseif a == "y" then
			if aimbothider == false then
				aimbothider = true
				if aimbothider == true then
					return
				end
			end
		elseif a == "l" then
			if autoesp == false then
				autoesp = true
			else
				autoesp = false
			end
		elseif a == Aim_Assist_Key[2] and uis:IsKeyDown(Aim_Assist_Key[1]) then
			if Aim_Assist == true then
				Aim_Assist = false
				--print("disabled")
			else
				Aim_Assist = true
			end
		end
		if a == "j" then
			if mouse.Target then
				mouse.Target:Destroy()
			end
		end
		if a == key then
			if switch == false then
				switch = true
			else
				switch = false
				if aimatpart ~= nil then
					aimatpart = nil
				end
			end
		elseif a == teambasedswitch then
			if TeamBased == true then
				TeamBased = false
				CheatType_3.Text = "Team Based : "..tostring(TeamBased)
			else
				TeamBased = true
				CheatType_3.Text = "Team Based : "..tostring(TeamBased)
			end
		elseif a == aimkey then
			if not aimatpart then
				local maxangle = math.rad(20)
				for i, plr in pairs(plrs:GetChildren()) do
					if plr.Name ~= lplr.Name and plr.Character and plr.Character.Head and plr.Character.Humanoid and plr.Character.Humanoid.Health > 1 then
						if TeamBased == true then
							if plr.Team.Name ~= lplr.Team.Name then
								local an = checkfov(plr.Character.Head)
								if an < maxangle then
									maxangle = an
									aimatpart = plr.Character.Head
								end
							end
						else
							local an = checkfov(plr.Character.Head)
							if an < maxangle then
								maxangle = an
								aimatpart = plr.Character.Head
							end
							--print(plr)
						end
						local old = aimatpart
						plr.Character.Humanoid.Died:Connect(function()
							--print("died")
							if aimatpart and aimatpart == old then
								aimatpart = nil
							end
						end)

					end
				end
			else
				aimatpart = nil
				canaimat = false
				delay(1.1, function()
					canaimat = true
				end)
			end
		end
	end)

	function getfovxyz (p0, p1, deg)
		local x1, y1, z1 = p0:ToOrientation()
		local cf = CFrame.new(p0.p, p1.p)
		local x2, y2, z2 = cf:ToOrientation()
		local d = math.deg
		if deg then
			return Vector3.new(d(x1-x2), d(y1-y2), d(z1-z2))
		else
			return Vector3.new((x1-x2), (y1-y2), (z1-z2))
		end
	end


	function aimat(part)
		if part then
			if aimbothider == true or Aim_Assist == true then
				cam.CFrame = cam.CFrame:Lerp(CFrame.new(cam.CFrame.p, part.CFrame.p), aimbothiderspeed)
			else

				cam.CFrame = CFrame.new(cam.CFrame.p, part.CFrame.p)
			end
		end
	end
	function checkfov (part)
		local fov = getfovxyz(game.Workspace.CurrentCamera.CFrame, part.CFrame)
		local angle = math.abs(fov.X) + math.abs(fov.Y)
		return angle
	end
	pcall(function()
		delay(0, function()
			while wait(.4) do
				if Aim_Assist and not aimatpart and canaimat and lplr.Character and lplr.Character.Humanoid and lplr.Character.Humanoid.Health > 0 then
					for i, plr in pairs(plrs:GetChildren()) do


						local minangle = math.rad(5.5)
						local lastpart = nil
						local function gg(plr)
							pcall(function()
								if plr.Name ~= lplr.Name and plr.Character and plr.Character.Humanoid and plr.Character.Humanoid.Health > 0 and plr.Character.Head then
									local raycasted = false
									local cf1 = CFrame.new(cam.CFrame.p, plr.Character.Head.CFrame.p) * CFrame.new(0, 0, -4)
									local r1 = Ray.new(cf1.p, cf1.LookVector * 9000)
									local obj, pos = game.Workspace:FindPartOnRayWithIgnoreList(r1,  {lplr.Character.Head})
									local dist = (plr.Character.Head.CFrame.p- pos).magnitude
									if dist < 4 then
										raycasted = true
									end
									if raycasted == true then
										local an1 = getfovxyz(cam.CFrame, plr.Character.Head.CFrame)
										local an = abs(an1.X) + abs(an1.Y)
										if an < minangle then
											minangle = an
											lastpart = plr.Character.Head
										end
									end
								end
							end)
						end
						if TeamBased then
							if plr.Team.Name ~= lplr.Team.Name then
								gg(plr)
							end
						else
							gg(plr)
						end
						--print(math.deg(minangle))
						if lastpart then
							aimatpart = lastpart
							aimatpart.Parent.Humanoid.Died:Connect(function()
								if aimatpart == lastpart then
									aimatpart = nil
								end
							end)

						end
					end
				end
			end
		end)
	end)
	local oldheadpos
	local lastaimapart
	game:GetService("RunService").RenderStepped:Connect(function()
		CheatType.Text = "Esp loop : "..tostring(autoesp)
		if aimatpart and lplr.Character and lplr.Character.Head then
			if BetterDeathCount and lastaimapart and lastaimapart == aimatpart then
				local dist = (oldheadpos - aimatpart.CFrame.p).magnitude
				if dist > 40 then
					aimatpart = nil
				end
			end
			lastaimapart = aimatpart
			oldheadpos = lastaimapart.CFrame.p
			do
				if aimatpart.Parent == plrs.LocalPlayer.Character then
					aimatpart = nil
				end
				aimat(aimatpart)
				pcall(function()
					if Aim_Assist == true then
						local cf1 = CFrame.new(cam.CFrame.p, aimatpart.CFrame.p) * CFrame.new(0, 0, -4)
						local r1 = Ray.new(cf1.p, cf1.LookVector * 1000)
						local obj, pos = game.Workspace:FindPartOnRayWithIgnoreList(r1,  {lplr.Character.Head})
						local dist = (aimatpart.CFrame.p- pos).magnitude
						if obj then
							--print(obj:GetFullName())
						end
						if not obj or dist > 6 then
							aimatpart = nil
							--print("ooof")
						end
						canaimat = false
						delay(.5, function()
							canaimat = true
						end)
					end
				end)
			end



		end
	end)
	delay(0, function()
		while wait(espupdatetime) do
			if autoesp == true then
				pcall(function()
					f.addesp()
				end)
			end
		end
	end)
	--warn("loaded")
	function dragify(Frame)
		dragToggle = nil
		dragSpeed = .25 -- You can edit this.
		dragInput = nil
		dragStart = nil
		dragPos = nil

		function updateInput(input)
			Delta = input.Position - dragStart
			Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
			game:GetService("TweenService"):Create(Frame, TweenInfo.new(.25), {Position = Position}):Play()
		end

		Frame.InputBegan:Connect(function(input)
			if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then
				dragToggle = true
				dragStart = input.Position
				startPos = Frame.Position
				input.Changed:Connect(function()
					if (input.UserInputState == Enum.UserInputState.End) then
						dragToggle = false
					end
				end)
			end
		end)

		Frame.InputChanged:Connect(function(input)
			if (input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch) then
				dragInput = input
			end
		end)

		game:GetService("UserInputService").InputChanged:Connect(function(input)
			if (input == dragInput and dragToggle) then
				updateInput(input)
			end
		end)
	end
	dragify(AimbotFrame)

	local Player = game:GetService'Players'.LocalPlayer;
	local UIS = game:GetService'UserInputService';

	_G.JumpHeight = 50;

	function Action(Object, Function) if Object ~= nil then Function(Object); end end

	UIS.InputBegan:connect(function(UserInput)
		if UserInput.UserInputType == Enum.UserInputType.Keyboard and UserInput.KeyCode == Enum.KeyCode.Space then
			Action(Player.Character.Humanoid, function(self)
				if self:GetState() == Enum.HumanoidStateType.Jumping or self:GetState() == Enum.HumanoidStateType.Freefall then
					Action(self.Parent.HumanoidRootPart, function(self)
						self.Velocity = Vector3.new(0, _G.JumpHeight, 0);
					end)
				end
			end)
		end
	end)
end)
Infinitejump.Name = "Infinite jump"
Infinitejump.Parent = Test
Infinitejump.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Infinitejump.Position = UDim2.new(0.675302207, 0, 0.715384662, 0)
Infinitejump.Size = UDim2.new(0, 142, 0, 50)
Infinitejump.Font = Enum.Font.SourceSans
Infinitejump.Text = "Infinite Jump"
Infinitejump.TextColor3 = Color3.fromRGB(0, 0, 0)
Infinitejump.TextScaled = true
Infinitejump.TextSize = 14.000
Infinitejump.TextWrapped = true
Infinitejump.MouseButton1Click:Connect(function()
	-- by isaraw8912
	-- Press [R] to turn off and to turn on

	_G.infinjump = true

	local Player = game:GetService("Players").LocalPlayer
	local Mouse = Player:GetMouse()
	Mouse.KeyDown:connect(function(k)
		if _G.infinjump then
			if k:byte() == 32 then
				Humanoid = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
				Humanoid:ChangeState("Jumping")
				wait(0.1)
				Humanoid:ChangeState("Seated")
			end
		end
	end)

	local Player = game:GetService("Players").LocalPlayer
	local Mouse = Player:GetMouse()
	Mouse.KeyDown:connect(function(k)
		k = k:lower()
		if k == "r" then
			if _G.infinjump == true then
				_G.infinjump = false
			else
				_G.infinjump = true
			end
		end
	end)
end)
Close.Name = "Close"
Close.Parent = Test
Close.BackgroundColor3 = Color3.fromRGB(255, 40, 12)
Close.Position = UDim2.new(0.939550936, 0, 0, 0)
Close.Size = UDim2.new(0, 35, 0, 43)
Close.Font = Enum.Font.SourceSans
Close.Text = "X"
Close.TextColor3 = Color3.fromRGB(0, 0, 0)
Close.TextScaled = true
Close.TextSize = 14.000
Close.TextWrapped = true


NextPage.Name = "NextPage"
NextPage.Parent = Test
NextPage.BackgroundColor3 = Color3.fromRGB(74, 74, 74)
NextPage.Position = UDim2.new(0.820379972, 0, 0.871794879, 0)
NextPage.Size = UDim2.new(0, 96, 0, 42)
NextPage.Font = Enum.Font.SourceSans
NextPage.Text = "Next Page"
NextPage.TextColor3 = Color3.fromRGB(0, 0, 0)
NextPage.TextScaled = true
NextPage.TextSize = 14.000
NextPage.TextWrapped = true

Testt.Name = "Testt"
Testt.Parent = ScreenGui
Testt.BackgroundColor3 = Color3.fromRGB(93, 93, 93)
Testt.BackgroundTransparency = 0.100
Testt.Position = UDim2.new(0.307000011, 0, 0.261999995, 0)
Testt.Size = UDim2.new(0, 579, 0, 390)
Testt.Visible = false

label_2.Name = "label"
label_2.Parent = Testt
label_2.BackgroundColor3 = Color3.fromRGB(76, 76, 76)
label_2.Size = UDim2.new(0, 579, 0, 50)
label_2.Font = Enum.Font.Cartoon
label_2.Text = "Trolling Gui"
label_2.TextColor3 = Color3.fromRGB(0, 0, 0)
label_2.TextScaled = true
label_2.TextSize = 14.000
label_2.TextWrapped = true

Close_2.Name = "Close"
Close_2.Parent = Testt
Close_2.BackgroundColor3 = Color3.fromRGB(255, 40, 12)
Close_2.Position = UDim2.new(0.939550936, 0, 0, 0)
Close_2.Size = UDim2.new(0, 35, 0, 43)
Close_2.Font = Enum.Font.SourceSans
Close_2.Text = "X"
Close_2.TextColor3 = Color3.fromRGB(0, 0, 0)
Close_2.TextScaled = true
Close_2.TextSize = 14.000
Close_2.TextWrapped = true

BloxFruitV2.Name = "Blox Fruit V2"
BloxFruitV2.Parent = Testt
BloxFruitV2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
BloxFruitV2.Position = UDim2.new(0.0138169257, 0, 0.171794876, 0)
BloxFruitV2.Size = UDim2.new(0, 97, 0, 50)
BloxFruitV2.Font = Enum.Font.SourceSans
BloxFruitV2.Text = "Blox Fruit V2"
BloxFruitV2.TextColor3 = Color3.fromRGB(0, 0, 0)
BloxFruitV2.TextScaled = true
BloxFruitV2.TextSize = 14.000
BloxFruitV2.TextWrapped = true
BloxFruitV2.MouseButton1Click:Connect(function()
	loadstring(game:HttpGet"https://raw.githubusercontent.com/xDepressionx/Free-Script/main/AllScript.lua")()	
end)

MuderMy2.Name = "MuderMy2"
MuderMy2.Parent = Testt
MuderMy2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
MuderMy2.Position = UDim2.new(0.227979273, 0, 0.171794876, 0)
MuderMy2.Size = UDim2.new(0, 97, 0, 50)
MuderMy2.Font = Enum.Font.SourceSans
MuderMy2.Text = "InvisFling Press Z"
MuderMy2.TextColor3 = Color3.fromRGB(0, 0, 0)
MuderMy2.TextScaled = true
MuderMy2.TextSize = 14.000
MuderMy2.TextWrapped = true
MuderMy2.MouseButton1Click:Connect(function()
	game.StarterGui:SetCore("SendNotification", {
		Title = "FE Invisible Fling";
		Text = "hehe boi get load'd";
		Duration = 3;
	})

	spawn(function()
		local message = Instance.new("Message",workspace)
		message.Text = "Press z to execute or X to respawn."
		wait(0.5)
		message:Destroy()
	end)


	local mouse = game.Players.LocalPlayer:GetMouse()

	local groot = nil

	mouse.KeyDown:connect(function(k)

		if k == "z" then



			spawn(function()
				local message = Instance.new("Message",workspace)
				message.Text = "Fe Invisible Fling By Diemiers#4209 Loaded (wait 11 seconds to load)"
				wait(11)
				message:Destroy()
			end)


			local ch = game.Players.LocalPlayer.Character
			local prt=Instance.new("Model", workspace)
			local z1 =  Instance.new("Part", prt)
			z1.Name="Torso"
			z1.CanCollide = false
			z1.Anchored = true
			local z2  =Instance.new("Part", prt)
			z2.Name="Head"
			z2.Anchored = true
			z2.CanCollide = false
			local z3 =Instance.new("Humanoid", prt)
			z3.Name="Humanoid"
			z1.Position = Vector3.new(0,9999,0)
			z2.Position = Vector3.new(0,9991,0)
			game.Players.LocalPlayer.Character=prt
			wait(5)
			game.Players.LocalPlayer.Character=ch
			wait(6)


			local plr = game.Players.LocalPlayer
			mouse = plr:GetMouse()

			local Hum = Instance.new("Humanoid")
			Hum.Parent = game.Players.LocalPlayer.Character


			local root =  game.Players.LocalPlayer.Character.HumanoidRootPart


			for i,v in pairs(plr.Character:GetChildren()) do

				if v ~= root and  v.Name ~= "Humanoid" then

					v:Destroy()

				end


			end

			workspace.CurrentCamera.CameraSubject = root

			local se = Instance.new("SelectionBox",root)
			se.Adornee = root


			game:GetService('RunService').Stepped:connect(function()
				game.Players.LocalPlayer.Character.HumanoidRootPart.CanCollide = false
			end)
			game:GetService('RunService').RenderStepped:connect(function()
				game.Players.LocalPlayer.Character.HumanoidRootPart.CanCollide = false
			end)


			power = 999999 -- change this to make it more or less powerful

			power = power*10

			---
			wait(.1)
			local bambam = Instance.new("BodyThrust")
			bambam.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
			bambam.Force = Vector3.new(power,0,power)
			bambam.Location = game.Players.LocalPlayer.Character.HumanoidRootPart.Position 





			local plr = game.Players.LocalPlayer
			local torso = root
			local flying = true
			local deb = true
			local ctrl = {f = 0, b = 0, l = 0, r = 0}
			local lastctrl = {f = 0, b = 0, l = 0, r = 0}
			local maxspeed = 120
			local speed = 15


			---local bambam = Instance.new("BodyThrust")
			---bambam.Parent = torso
			--bambam.Force = Vector3.new(9999999,0,9999999)
			--bambam.Location = torso.Position


			---
			groot = root

			function Fly()
				local bg = Instance.new("BodyGyro", torso)
				bg.P = 9e4
				bg.maxTorque = Vector3.new(0, 0, 0)
				bg.cframe = torso.CFrame
				local bv = Instance.new("BodyVelocity", torso)
				bv.velocity = Vector3.new(0,0,0)
				bv.maxForce = Vector3.new(9e9, 9e9, 9e9)
				repeat wait()

					if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then
						speed = speed+.2
						if speed > maxspeed then
							speed = maxspeed
						end
					elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then
						speed = speed-1
						if speed < 0 then
							speed = 0
						end
					end
					if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then
						bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed
						lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r}
					elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then
						bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed
					else
						bv.velocity = Vector3.new(0,0.1,0)
					end

				until not flying
				ctrl = {f = 0, b = 0, l = 0, r = 0}
				lastctrl = {f = 0, b = 0, l = 0, r = 0}
				speed = 0
				bg:Destroy()
				bv:Destroy()

			end
			mouse.KeyDown:connect(function(key)
				if key:lower() == "e" then
					if flying then flying = false
					else
						flying = true
						Fly()
					end
				elseif key:lower() == "w" then
					ctrl.f = 1
				elseif key:lower() == "s" then
					ctrl.b = -1
				elseif key:lower() == "a" then
					ctrl.l = -1
				elseif key:lower() == "d" then
					ctrl.r = 1
				end
			end)
			mouse.KeyUp:connect(function(key)
				if key:lower() == "w" then
					ctrl.f = 0
				elseif key:lower() == "s" then
					ctrl.b = 0
				elseif key:lower() == "a" then
					ctrl.l = 0
				elseif key:lower() == "d" then
					ctrl.r = 0
				elseif key:lower() == "r" then

				end
			end)
			Fly()



		elseif k == "x" then


			spawn(function()
				local message = Instance.new("Message",workspace)
				message.Text = "Respawning dont spam"
				wait(1)
				message:Destroy()
			end)

			local saved = groot.Position

			local ch = game.Players.LocalPlayer.Character
			local prt=Instance.new("Model", workspace)
			local z1 =  Instance.new("Part", prt)
			z1.Name="Torso"
			z1.CanCollide = false
			z1.Anchored = true
			local z2  =Instance.new("Part", prt)
			z2.Name="Head"
			z2.Anchored = true
			z2.CanCollide = false
			local z3 =Instance.new("Humanoid", prt)
			z3.Name="Humanoid"
			z1.Position = Vector3.new(0,9999,0)
			z2.Position = Vector3.new(0,9991,0)
			game.Players.LocalPlayer.Character=prt
			wait(5)
			game.Players.LocalPlayer.Character=ch
			local poop = nil
			repeat wait() poop = game.Players.LocalPlayer.Character:FindFirstChild("Head") until poop ~= nil
			wait(1)
			game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(saved)

		end


	end)
end)

PetSim.Name = "PetSim"
PetSim.Parent = Testt
PetSim.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
PetSim.Position = UDim2.new(0.431778908, 0, 0.171794876, 0)
PetSim.Size = UDim2.new(0, 97, 0, 50)
PetSim.Text = "PetSim"
PetSim.Font = Enum.Font.SourceSans
PetSim.TextColor3 = Color3.fromRGB(0, 0, 0)
PetSim.TextScaled = true
PetSim.TextSize = 14.000
PetSim.TextWrapped = true
PetSim.MouseButton1Click:Connect(function()
--Name: "Pet Simulator X | Auto Farm Coins, Diamonds, Auto OPEN EGGS & MORE!"

loadstring(game:HttpGet("https://raw.githubusercontent.com/TurfuGoldy/GoldenScripts/main/EzPets.lua"))()


end)

DaHood.Name = "Da Hood"
DaHood.Parent = Testt
DaHood.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
DaHood.Position = UDim2.new(0.626942992, 0, 0.171794876, 0)
DaHood.Size = UDim2.new(0, 97, 0, 50)
DaHood.Text = "DaHood"
DaHood.Font = Enum.Font.SourceSans
DaHood.TextColor3 = Color3.fromRGB(0, 0, 0)
DaHood.TextScaled = true
DaHood.TextSize = 14.000
DaHood.TextWrapped = true
DaHood.MouseButton1Click:Connect(function()

end)

InvisFling.Name = "Invis Fling"
InvisFling.Parent = Testt
InvisFling.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
InvisFling.Position = UDim2.new(0.818652868, 0, 0.171794876, 0)
InvisFling.Size = UDim2.new(0, 97, 0, 50)
InvisFling.Text = "InvisFling"
InvisFling.Font = Enum.Font.SourceSans
InvisFling.TextColor3 = Color3.fromRGB(0, 0, 0)
InvisFling.TextScaled = true
InvisFling.TextSize = 14.000
InvisFling.TextWrapped = true
InvisFling.MouseButton1Click:Connect(function()

end)

InfiniteYield.Name = "Infinite Yield"
InfiniteYield.Parent = Testt
InfiniteYield.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
InfiniteYield.Position = UDim2.new(0.818652868, 0, 0.171794876, 0)
InfiniteYield.Size = UDim2.new(0, 97, 0, 50)
InfiniteYield.Text = "InfiniteYield"
InfiniteYield.Font = Enum.Font.SourceSans
InfiniteYield.TextColor3 = Color3.fromRGB(0, 0, 0)
InfiniteYield.TextScaled = true
InfiniteYield.TextSize = 14.000
InfiniteYield.TextWrapped = true
InfiniteYield.MouseButton1Click:Connect(function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'),true))()
end)

_5.Name = "5"
_5.Parent = Testt
_5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_5.Position = UDim2.new(0.818652868, 0, 0.335897446, 0)
_5.Size = UDim2.new(0, 97, 0, 50)
_5.Text = "Blox Fruit V2"
_5.Font = Enum.Font.SourceSans
_5.TextColor3 = Color3.fromRGB(0, 0, 0)
_5.TextScaled = true
_5.TextSize = 14.000
_5.TextWrapped = true
_5.MouseButton1Click:Connect(function()

end)

_3.Name = "3"
_3.Parent = Testt
_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_3.Position = UDim2.new(0.626942992, 0, 0.335897446, 0)
_3.Size = UDim2.new(0, 97, 0, 50)
_3.Text = "Blox Fruit V2"
_3.Font = Enum.Font.SourceSans
_3.TextColor3 = Color3.fromRGB(0, 0, 0)
_3.TextScaled = true
_3.TextSize = 14.000
_3.TextWrapped = true
_3.MouseButton1Click:Connect(function()

end)

_4.Name = "4"
_4.Parent = Testt
_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_4.Position = UDim2.new(0.431778908, 0, 0.335897446, 0)
_4.Size = UDim2.new(0, 97, 0, 50)
_4.Text = "Blox Fruit V2"
_4.Font = Enum.Font.SourceSans
_4.TextColor3 = Color3.fromRGB(0, 0, 0)
_4.TextScaled = true
_4.TextSize = 14.000
_4.TextWrapped = true
_4.MouseButton1Click:Connect(function()

end)

_2.Name = "2"
_2.Parent = Testt
_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_2.Position = UDim2.new(0.227979273, 0, 0.335897446, 0)
_2.Size = UDim2.new(0, 97, 0, 50)
_2.Text = "Blox Fruit V2"
_2.Font = Enum.Font.SourceSans
_2.TextColor3 = Color3.fromRGB(0, 0, 0)
_2.TextScaled = true
_2.TextSize = 14.000
_2.TextWrapped = true
_2.MouseButton1Click:Connect(function()

end)

_1.Name = "1"
_1.Parent = Testt
_1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_1.Position = UDim2.new(0.0138169257, 0, 0.335897446, 0)
_1.Size = UDim2.new(0, 97, 0, 50)
_1.Text = "Blox Fruit V2"
_1.Font = Enum.Font.SourceSans
_1.TextColor3 = Color3.fromRGB(0, 0, 0)
_1.TextScaled = true
_1.TextSize = 14.000
_1.TextWrapped = true
_1.MouseButton1Click:Connect(function()

end)

_6.Name = "6"
_6.Parent = Testt
_6.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_6.Position = UDim2.new(0.818652868, 0, 0.5, 0)
_6.Size = UDim2.new(0, 97, 0, 50)
_6.Text = "Blox Fruit V2"
_6.Font = Enum.Font.SourceSans
_6.TextColor3 = Color3.fromRGB(0, 0, 0)
_6.TextScaled = true
_6.TextSize = 14.000
_6.TextWrapped = true
_6.MouseButton1Click:Connect(function()

end)

_10.Name = "10"
_10.Parent = Testt
_10.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_10.Position = UDim2.new(0.626942992, 0, 0.5, 0)
_10.Size = UDim2.new(0, 97, 0, 50)
_10.Text = "Blox Fruit V2"
_10.Font = Enum.Font.SourceSans
_10.TextColor3 = Color3.fromRGB(0, 0, 0)
_10.TextScaled = true
_10.TextSize = 14.000
_10.TextWrapped = true
_10.MouseButton1Click:Connect(function()

end)

_8.Name = "8"
_8.Parent = Testt
_8.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_8.Position = UDim2.new(0.431778908, 0, 0.5, 0)
_8.Size = UDim2.new(0, 97, 0, 50)
_8.Text = "Blox Fruit V2"
_8.Font = Enum.Font.SourceSans
_8.TextColor3 = Color3.fromRGB(0, 0, 0)
_8.TextScaled = true
_8.TextSize = 14.000
_8.TextWrapped = true
_8.MouseButton1Click:Connect(function()

end)

_9.Name = "9"
_9.Parent = Testt
_9.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_9.Position = UDim2.new(0.227979273, 0, 0.5, 0)
_9.Size = UDim2.new(0, 97, 0, 50)
_9.Text = "Blox Fruit V2"
_9.Font = Enum.Font.SourceSans
_9.TextColor3 = Color3.fromRGB(0, 0, 0)
_9.TextScaled = true
_9.TextSize = 14.000
_9.TextWrapped = true
_9.MouseButton1Click:Connect(function()

end)

_7.Name = "7"
_7.Parent = Testt
_7.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_7.Position = UDim2.new(0.0138169257, 0, 0.5, 0)
_7.Size = UDim2.new(0, 97, 0, 50)
_7.Text = "Blox Fruit V2"
_7.Font = Enum.Font.SourceSans
_7.TextColor3 = Color3.fromRGB(0, 0, 0)
_7.TextScaled = true
_7.TextSize = 14.000
_7.TextWrapped = true
_7.MouseButton1Click:Connect(function()

end)

_14.Name = "14"
_14.Parent = Testt
_14.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_14.Position = UDim2.new(0.818652868, 0, 0.661538482, 0)
_14.Size = UDim2.new(0, 97, 0, 50)
_14.Text = "Blox Fruit V2"
_14.Font = Enum.Font.SourceSans
_14.TextColor3 = Color3.fromRGB(0, 0, 0)
_14.TextScaled = true
_14.TextSize = 14.000
_14.TextWrapped = true
_14.MouseButton1Click:Connect(function()

end)

_11.Name = "11"
_11.Parent = Testt
_11.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_11.Position = UDim2.new(0.626942992, 0, 0.661538482, 0)
_11.Size = UDim2.new(0, 97, 0, 50)
_11.Text = "Blox Fruit V2"
_11.Font = Enum.Font.SourceSans
_11.TextColor3 = Color3.fromRGB(0, 0, 0)
_11.TextScaled = true
_11.TextSize = 14.000
_11.TextWrapped = true
_11.MouseButton1Click:Connect(function()

end)

_12.Name = "12"
_12.Parent = Testt
_12.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_12.Position = UDim2.new(0.431778908, 0, 0.661538482, 0)
_12.Size = UDim2.new(0, 97, 0, 50)
_12.Text = "Blox Fruit V2"
_12.Font = Enum.Font.SourceSans
_12.TextColor3 = Color3.fromRGB(0, 0, 0)
_12.TextScaled = true
_12.TextSize = 14.000
_12.TextWrapped = true
_12.MouseButton1Click:Connect(function()

end)

_15.Name = "15"
_15.Parent = Testt
_15.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_15.Position = UDim2.new(0.227979273, 0, 0.661538482, 0)
_15.Size = UDim2.new(0, 97, 0, 50)
_15.Text = "Blox Fruit V2"
_15.Font = Enum.Font.SourceSans
_15.TextColor3 = Color3.fromRGB(0, 0, 0)
_15.TextScaled = true
_15.TextSize = 14.000
_15.TextWrapped = true
_15.MouseButton1Click:Connect(function()

end)

_13.Name = "13"
_13.Parent = Testt
_13.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_13.Position = UDim2.new(0.0138169257, 0, 0.661538482, 0)
_13.Size = UDim2.new(0, 97, 0, 50)
_13.Text = "Blox Fruit V2"
_13.Font = Enum.Font.SourceSans
_13.TextColor3 = Color3.fromRGB(0, 0, 0)
_13.TextScaled = true
_13.TextSize = 14.000
_13.TextWrapped = true
_13.MouseButton1Click:Connect(function()

end)

_16.Name = "16"
_16.Parent = Testt
_16.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_16.Position = UDim2.new(0.818652868, 0, 0.807692349, 0)
_16.Size = UDim2.new(0, 97, 0, 50)
_16.Text = "Blox Fruit V2"
_16.Font = Enum.Font.SourceSans
_16.TextColor3 = Color3.fromRGB(0, 0, 0)
_16.TextScaled = true
_16.TextSize = 14.000
_16.TextWrapped = true
_16.MouseButton1Click:Connect(function()

end)

_18.Name = "18"
_18.Parent = Testt
_18.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_18.Position = UDim2.new(0.626942992, 0, 0.807692349, 0)
_18.Size = UDim2.new(0, 97, 0, 50)
_18.Text = "Blox Fruit V2"
_18.Font = Enum.Font.SourceSans
_18.TextColor3 = Color3.fromRGB(0, 0, 0)
_18.TextScaled = true
_18.TextSize = 14.000
_18.TextWrapped = true
_18.MouseButton1Click:Connect(function()

end)
_19.Name = "19"
_19.Parent = Testt
_19.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_19.Position = UDim2.new(0.431778908, 0, 0.807692349, 0)
_19.Size = UDim2.new(0, 97, 0, 50)
_19.Text = "Blox Fruit V2"
_19.Font = Enum.Font.SourceSans
_19.TextColor3 = Color3.fromRGB(0, 0, 0)
_19.TextScaled = true
_19.TextSize = 14.000
_19.TextWrapped = true
_19.MouseButton1Click:Connect(function()

end)

_17.Name = "17"
_17.Parent = Testt
_17.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_17.Position = UDim2.new(0.227979273, 0, 0.807692349, 0)
_17.Size = UDim2.new(0, 97, 0, 50)
_17.Text = "Blox Fruit V2"
_17.Font = Enum.Font.SourceSans
_17.TextColor3 = Color3.fromRGB(0, 0, 0)
_17.TextScaled = true
_17.TextSize = 14.000
_17.TextWrapped = true
_17.MouseButton1Click:Connect(function()

end)

_20.Name = "20"
_20.Parent = Testt
_20.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
_20.Position = UDim2.new(0.0138169257, 0, 0.807692349, 0)
_20.Size = UDim2.new(0, 97, 0, 50)
_20.Text = "Blox Fruit V2"
_20.Font = Enum.Font.SourceSans
_20.TextColor3 = Color3.fromRGB(0, 0, 0)
_20.TextScaled = true
_20.TextSize = 14.000
_20.TextWrapped = true
_20.MouseButton1Click:Connect(function()

end)

-- Scripts:

local function NLVLBO_fake_script() -- TextButton.LocalScript 
	local script = Instance.new('LocalScript', TextButton)

	local frame = script.Parent.Parent.Test
	
	local open = false
	
	script.Parent.MouseButton1Click:Connect(function()
		if frame.Visible == false then
			frame.Visible = true
		
		end
	end)
end
coroutine.wrap(NLVLBO_fake_script)()
local function OIGW_fake_script() -- Close.LocalScript 
	local script = Instance.new('LocalScript', Close)

	script.Parent.MouseButton1Click:Connect(function()
		script.Parent.Parent.Visible = false
	end)
end
coroutine.wrap(OIGW_fake_script)()
local function XFDHH_fake_script() -- Test.DraggableGUI 
	local script = Instance.new('LocalScript', Test)

	local UserInputService = game:GetService("UserInputService")
	
	local gui = script.Parent
	
	local dragging
	local dragInput
	local dragStart
	local startPos
	
	local function update(input)
		local delta = input.Position - dragStart
		gui.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	end
	
	gui.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			dragging = true
			dragStart = input.Position
			startPos = gui.Position
			
			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragging = false
				end
			end)
		end
	end)
	
	gui.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			dragInput = input
		end
	end)
	
	UserInputService.InputChanged:Connect(function(input)
		if input == dragInput and dragging then
			if gui.Visible then
				update(input)
			end
		end
	end)
end
coroutine.wrap(XFDHH_fake_script)()
local function TLTSK_fake_script() -- NextPage.LocalScript 
	local script = Instance.new('LocalScript', NextPage)

	local frame = script.Parent.Parent.Parent.Test
	local framee = script.Parent.Parent.Parent.Testt
	local open = false
	
	  function OnClicked()
		if frame.Visible == true then
			frame.Visible = false
			framee.Visible = true
		end
		end 
	
	
	script.Parent.MouseButton1Click:Connect(OnClicked)
end
coroutine.wrap(TLTSK_fake_script)()
local function PHKLJ_fake_script() -- Testt.DraggableGUI 
	local script = Instance.new('LocalScript', Testt)

	local UserInputService = game:GetService("UserInputService")
	
	local gui = script.Parent
	
	local dragging
	local dragInput
	local dragStart
	local startPos
	
	local function update(input)
		local delta = input.Position - dragStart
		gui.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	end
	
	gui.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			dragging = true
			dragStart = input.Position
			startPos = gui.Position
			
			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragging = false
				end
			end)
		end
	end)
	
	gui.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			dragInput = input
		end
	end)
	
	UserInputService.InputChanged:Connect(function(input)
		if input == dragInput and dragging then
			if gui.Visible then
				update(input)
			end
		end
	end)
end
coroutine.wrap(PHKLJ_fake_script)()
local function DBYORA_fake_script() -- Close_2.LocalScript 
	local script = Instance.new('LocalScript', Close_2)

	script.Parent.MouseButton1Click:Connect(function()
		script.Parent.Parent.Visible = false
	end)
end
coroutine.wrap(DBYORA_fake_script)()
