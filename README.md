# Black-Guy-Transformation-Script-Roblox
in this script you equip a tool and when it is equipped you can click and it will change ur skintone to BLACK! and removes ur accessories and clothes, its mostly for trolling (DONT HATE PLEASE CUZ IM NEW)

THE SCRIPT IS:




local tool = Instance.new("Tool")
tool.Name = "KFC lover Transform"
tool.RequiresHandle = false

local normalColor = BrickColor.new("Black")
local isBrown = false

local function onToolActivated()
    local player = game.Players.LocalPlayer
    local character = player.Character
    if character then
        local humanoid = character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            if isBrown then
                for _, part in pairs(character:GetChildren()) do
                    if part:IsA("BasePart") then
                        part.BrickColor = normalColor
                    end
                end
            else
                for _, part in pairs(character:GetChildren()) do
                    if part:IsA("BasePart") then
                        part.BrickColor = BrickColor.new("Brown")
                    end
                end

                for _, accessory in pairs(character:GetChildren()) do
                    if accessory:IsA("Accessory") then
                        accessory:Destroy()
                    end
                end

                for _, item in pairs(character:GetChildren()) do
                    if item:IsA("Shirt") or item:IsA("Pants") or item:IsA("ShirtGraphic") then
                        item:Destroy()
                    end
                end
            end
            isBrown = not isBrown
        end
    end
end

tool.Equipped:Connect(function(mouse)
    mouse.Button1Down:Connect(onToolActivated)
end)

tool.Parent = game.Players.LocalPlayer.Backpack
