-- Icon personalizado
local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

-- Propriedades
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton.Parent = ScreenGui
ImageButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageButton.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageButton.BorderSizePixel = 0
ImageButton.Position = UDim2.new(0.005, 0, 0.010, 0)
ImageButton.Size = UDim2.new(0, 45, 0, 45)
ImageButton.Image = "rbxassetid://139166819013498" -- Id da icon aqui

UICorner.Parent = ImageButton

-- FunÃ§Ã£o para tornar o botÃ£o arrastÃ¡vel
local UIS = game:GetService("UserInputService")
local dragging, dragInput, startPos, startMousePos
local hasMoved = false

ImageButton.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragging = true
        hasMoved = false
        startPos = ImageButton.Position
        startMousePos = UIS:GetMouseLocation()

        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

ImageButton.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement then
        dragInput = input
    end
end)

UIS.InputChanged:Connect(function(input)
    if input == dragInput and dragging then
        local delta = UIS:GetMouseLocation() - startMousePos
        if math.abs(delta.X) > 5 or math.abs(delta.Y) > 5 then 
            hasMoved = true
        end
        ImageButton.Position = UDim2.new(
            startPos.X.Scale, startPos.X.Offset + delta.X,
            startPos.Y.Scale, startPos.Y.Offset + delta.Y
        )
    end
end)

ImageButton.MouseButton1Down:Connect(function()
    task.wait(0.1) -- Isso serve pro icone nao abrir quando a pessoa for arrastar ele, mexe aqui nÃ£o
    if not hasMoved then
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.LeftControl, false, game)
    end
end)

local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local MarketplaceService = game:GetService("MarketplaceService")
local PlaceId = game.PlaceId
local ProductInfo = MarketplaceService:GetProductInfo(PlaceId)
local GameName = ProductInfo.Name

Fluent:Notify({ Title = "Script executado com sucesso", Content = "Você esta usando Mender_hub",
Duration= 4 
})

local Window = Fluent:CreateWindow({
    Title = "Mender_hub",
    SubTitle = "-- " .. GameName,
    TabWidth = 102,
    Size = UDim2.fromOffset(450, 320),
    Acrylic = false,
    Theme = "Amethyst",
    MinimizeKey = Enum.KeyCode.LeftControl
})
local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "" })    
}
Tabs.Main:AddParagraph({
        Title = "Atualizado 22:45",
        Content = "Add Fixed bugs \n Add Rank up \n Add Magnetc Game pass"    
    })

local Tabs = {
    farm= Window:AddTab({ Title = "| Farm", Icon = "rbxassetid://18831424669" }),
     }
     
local AutoClick= Tabs.farm:AddToggle("Auto energy", {Title = "Auto energy", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
    --remote
    
game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Combat"):WaitForChild("Events"):WaitForChild("Attack"):InvokeServer()
            wait(0)
           end
        end)

local Tabs = {
    Main= Window:AddTab({ Title = "| Hath", Icon = "rbxassetid://18831424669" })
}
local AutoClick= Tabs.Main:AddToggle("Clover", {Title = "Black clover", Default = false})

AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Clover Field",
    [2] = 1
}

game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Gacha"):WaitForChild("Events"):WaitForChild("Open"):InvokeServer(unpack(args))
        wait(0)
    end
end)


local AutoClick= Tabs.Main:AddToggle("Ninja village", {Title = "ninja village", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Ninja Village",
    [2] = 1
}

game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Gacha"):WaitForChild("Events"):WaitForChild("Open"):InvokeServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("SWORD", {Title = "SWORD ART ONLINE", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Online World",
    [2] = 1
}

game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Gacha"):WaitForChild("Events"):WaitForChild("Open"):InvokeServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Demon Town", {Title = "Demon town", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Demon Town",
    [2] = 1
}

game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Gacha"):WaitForChild("Events"):WaitForChild("Open"):InvokeServer(unpack(args))
        wait(0)
    end
end)

local Tabs = { 
   Settings = Window:AddTab({ Title = "MISC", Icon = "settings" })
}

local AutoClick= Tabs.Settings:AddToggle("RankUp", {Title = "Auto Rank Up", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("RankUp"):WaitForChild("Events"):WaitForChild("Redeem"):InvokeServer()
        wait(0)
    end
end)

local Dropdown = Tabs.farm:AddDropdown("autofarm", {
    Title = "Wolrd 1",
    Values = {
        "Selecione a Ilha", -- Opcao inicial para evitar teleportes automÃ¡ticos
        "Finraio", 
        "Magna", 
        "noelly", 
        "vanessa", 
        "yuno", 
        "asta", 
    },
    Multi = false,
    Default = "Selecione O Mob", -- Agora o dropdown comeÃ§a sem teleportar ninguÃ©m
})

Dropdown:OnChanged(function(Value)
    local locations = {
        ["Finraio"] = _G.auto = true

while _G.auto do
local args = {
    [1] = "e46ec797-c047-4a03-9b1d-d7bfcfc15d02"
}

game:GetService("ReplicatedStorage").Packages.Network.Services.Combat.Events.Attack:InvokeServer(unpack(args))


wait()
end,
        ["Magna"] = CFrame.new(823.648682, 17.4093723, 8962.78223),
        ["noelly"] = CFrame.new(-6692.25293, 23.5935249, 1327.20728),
        ["vanessa"] = CFrame.new(4408.04736, 29.4047318, -2371.62598),
        ["yuno"] = CFrame.new(-3961.60254, 80.3750458, 9812.37793),
        ["asta"] = CFrame.new(-727.004517, 16.7731647, 1173.44324),
        ["Jojo"] = CFrame.new(49050.8633, 117.753181, 1175.1842),
        ["One Punch Man"] = CFrame.new(-23614.3711, -40.7557831, 460.156738)
    }

    if locations[Value] then
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = locations[Value]
        end
    end
end)-- Icon personalizado
local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

-- Propriedades
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

le AutoClick.Value do
--remote
local args = {
    [1] = "Online World",
    [2] = 1
}

game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Gacha"):WaitForChild("Events"):WaitForChild("Open"):InvokeServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Demon Town", {Title = "Demon town", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Demon Town",
    [2] = 1
}

game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("Gacha"):WaitForChild("Events"):WaitForChild("Open"):InvokeServer(unpack(args))
        wait(0)
    end
end)

local Tabs = { 
   Settings = Window:AddTab({ Title = "MISC", Icon = "settings" })
}

local AutoClick= Tabs.Settings:AddToggle("RankUp", {Title = "Auto Rank Up", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Network"):WaitForChild("Services"):WaitForChild("RankUp"):WaitForChild("Events"):WaitForChild("Redeem"):InvokeServer()
        wait(0)
    end
end)


local Toggle = Tabs.Settings:AddToggle("MagnetToggle", {Title = "Magnet", Default = false})

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local hrp = character:WaitForChild("HumanoidRootPart") -- Pega a posição do jogador

local function activateMagnet()
    while wait(0.1) do -- Repete a cada 0.1 segundos
        if Toggle.Value then -- Só ativa o magnet se o toggle estiver ligado
            for _, drop in pairs(workspace["Visual Effects"]:GetChildren()) do
                if drop:IsA("BasePart") or drop:IsA("Model") then -- Se for um objeto físico
                    drop.CFrame = hrp.CFrame -- Move o drop para o jogador
                end
            end
        end
    end
end

Toggle:OnChanged(function()
    if Toggle.Value then
        print("Magnet ativado!")
        activateMagnet()
    else
        print("Magnet desativado!")
    end
end)


local TeleportTab = Window:AddTab({ Title = "Teleports", Icon = "sword" })
TeleportTab:AddButton({
    Title = "nome da ilha",
    Callback = function()
        --codigo aqui
        local targetCFrame = CFrame.new(-74.0038071, 12.1121235, 2641.51855, -0.947319448, 1.04120423e-09, 0.320290238, 6.57698174e-10, 1, -1.30554711e-09, -0.320290238, -1.02611586e-09, -0.947319448)
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local HRT = character:WaitForChild("HumanoidRootPart")
        HRT.CFrame = targetCFrame
        print("Teleportado para ONE HERO")
    end
})


