local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local UserInputService = game:GetService("UserInputService")
local Workspace = game:GetService("Workspace")
local CoreGui = game:GetService("CoreGui")
local Players = game:GetService("Players")
local WalkHack = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local Toggle = Instance.new("TextButton")
local Status = Instance.new("TextLabel")
local StatusWork = Instance.new("TextLabel")
local Credit = Instance.new("TextLabel")
local Cross = Instance.new("ImageButton")
local SpeedOn = false

local config = {
    --Ставить кнопки
    BaseSpeed = Enum.KeyCode.Z,
    MediumSpeed = Enum.KeyCode.X,
    BigSpeed = Enum.KeyCode.C,
    Fly = Enum.KeyCode.V,
    Noclip = Enum.KeyCode.G,

    --Скорость среднего бега
    MediumConfig = 40
}

print("WalkHack has been Activated")

WalkHack.Name = "WalkHack"
WalkHack.Parent = game.CoreGui
--WalkHack.Parent = game.StarterGui

Frame.Name = "Frame"
Frame.Parent = WalkHack
Frame.BackgroundColor3 = Color3.new(0.0980392, 0.0980392, 0.0980392)
Frame.BorderColor3 = Color3.new(0.0588235, 0.0588235, 0.0588235)
Frame.BorderSizePixel = 2
Frame.Position = UDim2.new(0.149479166, 0, 0.82087779, 0)
Frame.Size = UDim2.new(0, 210, 0, 127)
Frame.Active = true
Frame.Draggable = true

Title.Name = "Title"
Title.Parent = Frame
Title.BackgroundColor3 = Color3.new(0.333333, 1, 0.498039)
Title.BorderColor3 = Color3.new(0.180392, 0, 0.431373)
Title.BorderSizePixel = 2
Title.Size = UDim2.new(0, 210, 0, 33)
Title.Font = Enum.Font.Highway
Title.Text = "WalkSpeed"
Title.TextColor3 = Color3.new(1, 1, 1)
Title.FontSize = Enum.FontSize.Size32
Title.TextSize = 30
Title.TextStrokeColor3 = Color3.new(0.180392, 0, 0.431373)
Title.TextStrokeTransparency = 0

Toggle.Parent = Frame
Toggle.BackgroundColor3 = Color3.new(0.333333, 1, 0.498039) --0.266667, 0.00392157, 0.627451
Toggle.BorderColor3 = Color3.new(0.180392, 0, 0.431373)
Toggle.BorderSizePixel = 2
Toggle.Position = UDim2.new(0.152380958, 0, 0.374192119, 0)
Toggle.Size = UDim2.new(0, 146, 0, 36)
Toggle.Font = Enum.Font.Highway
Toggle.FontSize = Enum.FontSize.Size28
Toggle.Text = "Toggle"
Toggle.TextColor3 = Color3.new(1, 1, 1)
Toggle.TextSize = 25
Toggle.TextStrokeColor3 = Color3.new(0.180392, 0, 0.431373)
Toggle.TextStrokeTransparency = 0

Status.Name = "Status"
Status.Parent = Frame
Status.BackgroundColor3 = Color3.new(1, 1, 1)
Status.BackgroundTransparency = 1
Status.Position = UDim2.new(0.314285725, 0, 0.708661377, 0)
Status.Size = UDim2.new(0, 56, 0, 20)
Status.Font = Enum.Font.Highway
Status.FontSize = Enum.FontSize.Size24
Status.Text = "Status:"
Status.TextColor3 = Color3.new(1, 1, 1)
Status.TextSize = 20
Status.TextStrokeColor3 = Color3.new(0.333333, 0.333333, 0.333333)
Status.TextStrokeTransparency = 0
Status.TextWrapped = true

StatusWork.Name = "StatusWork"
StatusWork.Parent = Frame
StatusWork.BackgroundColor3 = Color3.new(1, 1, 1)
StatusWork.BackgroundTransparency = 1
StatusWork.Position = UDim2.new(0.580952346, 0, 0.708661377, 0)
StatusWork.Size = UDim2.new(0, 56, 0, 20)
StatusWork.Font = Enum.Font.Highway
StatusWork.FontSize = Enum.FontSize.Size14
StatusWork.Text = "off"
StatusWork.TextColor3 = Color3.new(0.666667, 0, 0)
StatusWork.TextScaled = true
StatusWork.TextSize = 14
StatusWork.TextStrokeColor3 = Color3.new(0.180392, 0, 0.431373)
StatusWork.TextWrapped = true
StatusWork.TextXAlignment = Enum.TextXAlignment.Left

Credit.Name = "Credit"
Credit.Parent = Frame
Credit.BackgroundColor3 = Color3.new(1, 1, 1)
Credit.BackgroundTransparency = 1
Credit.Position = UDim2.new(0.1, 0,0.866, 0)
Credit.Size = UDim2.new(0, 169,0, 17)
Credit.Font = Enum.Font.SourceSans
Credit.FontSize = Enum.FontSize.Size18
Credit.Text = "Created by den41k4982"
Credit.TextColor3 = Color3.new(1, 1, 1)
Credit.TextSize = 16
Credit.TextStrokeColor3 = Color3.new(0.196078, 0.196078, 0.196078)
Credit.TextStrokeTransparency = 0
Credit.TextWrapped = true

Cross.Name = "Cross"
Cross.Parent = Frame
Cross.Position = UDim2.new(0, 0,0, 0)
Cross.Size = UDim2.new(0, 33,0, 33)
Cross.ImageColor3 = Color3.new(0.333333, 0.666667, 0.498039)

local debounce = false
local flyDebounce = false
local Fly = false
local Noclip = false
local NoclipDebounce = false

UserInputService.InputBegan:Connect(function(input, isTyping)
    if isTyping then return end
    if input.KeyCode == config.BigSpeed and SpeedOn == true then
        player.Character.Humanoid.WalkSpeed = 200
    end
    if input.KeyCode == config.MediumSpeed and SpeedOn == true then
        player.Character.Humanoid.WalkSpeed = config.MediumConfig
    end
    if input.KeyCode == config.BaseSpeed and SpeedOn == true then
        player.Character.Humanoid.WalkSpeed = 16
    end
    if input.KeyCode == config.Fly and SpeedOn == true and flyDebounce == false then
        flyDebounce = true
        Fly = true
        print("Полёт включен")
    elseif input.KeyCode == config.Fly and SpeedOn == true and flyDebounce == true then
        flyDebounce = false
        Fly = false
        print("Полёт выключен")
    end
    if input.KeyCode == config.Noclip and SpeedOn == true and NoclipDebounce == false then
        NoclipDebounce = true
        Noclip = true
        if Noclip then
            player.Character.UpperTorso.CanCollide = false
            player.Character.LowerTorso.CanCollide = false
            player.Character.HumanoidRootPart.CanCollide = false
        else
            player.Character.UpperTorso.CanCollide = true
            player.Character.LowerTorso.CanCollide = true
            player.Character.HumanoidRootPart.CanCollide = true
        end
        print("Noclip включен")
    elseif input.KeyCode == config.Noclip and SpeedOn == true and NoclipDebounce == true then
        NoclipDebounce = false
        Noclip = false
        if Noclip then
            player.Character.UpperTorso.CanCollide = false
            player.Character.LowerTorso.CanCollide = false
            player.Character.HumanoidRootPart.CanCollide = false
        else
            player.Character.UpperTorso.CanCollide = true
            player.Character.LowerTorso.CanCollide = true
            player.Character.HumanoidRootPart.CanCollide = true
        end
        print("Noclip выключен")
    end
end)

UserInputService.JumpRequest:Connect(function()  
    if Fly == true then
        player.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
    end
end)

Toggle.MouseButton1Click:Connect(function()  
    if StatusWork.Text == "off" then
        SpeedOn = true
        StatusWork.Text = "on"
        StatusWork.TextColor3 = Color3.new(0, 0.70, 0)
    else
        Fly = false
        SpeedOn = false
        StatusWork.Text = "off"
        StatusWork.TextColor3 = Color3.new(0.50, 0, 0)
        player.Character.Humanoid.WalkSpeed = 16
    end
end)

Cross.MouseButton1Click:Connect(function()
    Noclip = false
    Fly = false
    SpeedOn = false
    WalkHack:Destroy()
    print("WalkHack has been closed")
end)
