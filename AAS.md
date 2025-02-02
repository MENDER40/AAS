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

Fluent:Notify({ Title = "Script executado com sucesso", Content = "VocÃª esta usando Mender_hub" })

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
        Content = "Add Fixed bugs /n Add Rank up"
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
