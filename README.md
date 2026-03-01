--[[
    SCRIPT TROLL: FAKE BAN UI
    Tác dụng: Hiện bảng thông báo bị khóa tài khoản y như thật.
]]

local player = game.Players.LocalPlayer
local gui = Instance.new("ScreenGui")
gui.Name = "RobloxSystemNotice"
gui.Parent = game.CoreGui
gui.DisplayOrder = 999999 -- Luôn hiện trên cùng

local main = Instance.new("Frame")
main.Size = UDim2.new(1, 0, 1, 0)
main.BackgroundColor3 = Color3.fromRGB(45, 45, 45) -- Màu xám đặc trưng của Roblox
main.Parent = gui

local box = Instance.new("Frame")
box.Size = UDim2.new(0, 400, 0, 250)
box.Position = UDim2.new(0.5, -200, 0.5, -125)
box.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
box.Parent = main
Instance.new("UICorner", box)

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 50)
title.Text = "Banned"
title.TextColor3 = Color3.fromRGB(255, 50, 50)
title.TextSize = 25
title.Font = Enum.Font.GothamBold
title.Parent = box

local msg = Instance.new("TextLabel")
msg.Size = UDim2.new(1, -40, 1, -100)
msg.Position = UDim2.new(0, 20, 0, 40)
msg.Text = "Tài khoản của bạn đã bị khóa vĩnh viễn do sử dụng phần mềm thứ ba (Script Gemini Hub V11).\n\nLý do: Exploit & Scamming.\nThời gian: Vĩnh viễn."
msg.TextColor3 = Color3.fromRGB(50, 50, 50)
msg.TextSize = 16
msg.TextWrapped = true
msg.Font = Enum.Font.Gotham
msg.Parent = box

local btn = Instance.new("TextButton")
btn.Size = UDim2.new(0, 150, 0, 40)
btn.Position = UDim2.new(0.5, -75, 0.8, 0)
btn.Text = "Thoát Game"
btn.BackgroundColor3 = Color3.fromRGB(0, 162, 255)
btn.TextColor3 = Color3.fromRGB(255, 255, 255)
btn.Font = Enum.Font.GothamBold
btn.Parent = box
Instance.new("UICorner", btn)

-- Hiệu ứng khóa màn hình: Không cho nhấn vào bất cứ đâu khác
btn.MouseButton1Click:Connect(function()
    player:Kick("Bạn đã bị khóa tài khoản vĩnh viễn!") -- Đá khỏi server thật luôn để tạo cảm giác sợ
end)

-- Hiệu ứng rung màn hình cho thêm phần kịch tính
task.spawn(function()
    while task.wait(0.05) do
        box.Position = UDim2.new(0.5, math.random(-202, -198), 0.5, math.random(-127, -123))
    end
end)
