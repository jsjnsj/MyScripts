local WindUI = loadstring(game:HttpGet("https://github.com/Footagesus/WindUI/releases/latest/download/main.lua"))()

local Window = WindUI:CreateWindow({
    Title = "xhk缝合脚本",
    Icon = "door-open",
    Author = "作者:不想玩墨水",
    Folder = "CloudHub",
    Size = UDim2.fromOffset(560, 360),
    Transparent = true,
    Theme = "Dark",
    User = {
        Enabled = true,
        Callback = function() 
            print("???") 
        end,
        Anonymous = true
    },
})

Window:EditOpenButton({
    Title = "打开xhk缝合脚本",
    Icon = "monitor",
    CornerRadius = UDim.new(0,16),
    StrokeThickness = 2,
    Color = ColorSequence.new(
        Color3.fromHex("FF0F7B"),
        Color3.fromHex("F89B29")
    ),
    Draggable = true,
})

-- 便捷函数定义
function Tab(a, icon)
    return Window:Tab({Title = a, Icon = icon or "eye"})
end

function Button(a, b, c)
    return a:Button({Title = b, Callback = c})
end

function Toggle(a, b, c, d)
    return a:Toggle({Title = b, Value = c, Callback = d})
end

function Slider(a, b, c, d, e, f)
    return a:Slider({Title = b, Step = 1, Value = {Min = c, Max = d, Default = e}, Callback = f})
end

function Dropdown(a, b, c, d, e)
    return a:Dropdown({Title = b, Values = c, Value = d, Callback = e})
end

local YioapTab = Tab("公告", "door-open")
local PlayerTab = Tab("通用", "user")
local IuoTab = Tab("旋转", "star")
local UiowpTab = Tab("其他脚本", "bird")

-- 公告页按钮
Button(YioapTab, "赞助人:无", function()
    print("赞助人:无")
end)

Button(YioapTab, "目前还是测试版", function()
    print("目前还是测试版")
end)

Button(YioapTab, "2创的我操你妈，你妈没了", function()
    print("2创的我操你妈，你妈没了")
end)

-- 玩家设置标签
Slider(PlayerTab, "移动速度", 16, 200, 16, function(value)
    local player = game.Players.LocalPlayer
    if player.Character then
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid.WalkSpeed = value
        end
    end
    print("移动速度设置为: " .. value)
end)

Slider(PlayerTab, "跳跃高度", 50, 200, 50, function(value)
    local player = game.Players.LocalPlayer
    if player.Character then
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid.JumpPower = value
        end
    end
    print("跳跃高度设置为: " .. value)
end)

Button(PlayerTab, "Yi指令台", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()
    print("Infinite Yield 已加载！")
end)

-- ========== 旋转功能 - 死亡后自动恢复 ==========
local angular = nil        -- BodyAngularVelocity 实例
local LAST_SPEED = 0       -- 记住速度
local lp = game:GetService("Players").LocalPlayer

-- 创建/更新旋转
local function setSpin(speed)
    local char = lp.Character or lp.CharacterAdded:Wait()
    local root = char:WaitForChild("HumanoidRootPart", 2)
    if not root then return end

    if speed == 0 then
        if angular then angular:Destroy(); angular = nil end
        return
    end

    if not angular or angular.Parent ~= root then
        if angular then angular:Destroy() end
        angular = Instance.new("BodyAngularVelocity")
        angular.Name = "NetSpin"
        angular.MaxTorque = Vector3.new(0, 400000, 0)
        angular.P = 50000
        angular.Parent = root
    end
    angular.AngularVelocity = Vector3.new(0, speed * 0.8, 0)
    LAST_SPEED = speed
end

-- 滑条控制
Slider(IuoTab, "旋转速度", 0, 200, 0, setSpin)

-- 重生自动恢复
lp.CharacterAdded:Connect(function(char)
    task.wait(0.5)
    if LAST_SPEED ~= 0 then setSpin(LAST_SPEED) end
end)

Button(UiowpTab, "XC", function()
    loadstring(game:HttpGet("\104\116\116\112\115\58\47\47\112\97\115\116\101\98\105\110\46\99\111\109\47\114\97\119\47\103\101\109\120\72\119\65\49"))()
    print("已加载！")
end)

Button(UiowpTab, "导管中心", function()
    loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\34\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\117\115\101\114\97\110\101\119\114\102\102\47\114\111\98\108\111\120\45\47\109\97\105\110\47\37\69\54\37\57\68\37\65\49\37\69\54\37\65\67\37\66\69\37\69\53\37\56\68\37\56\70\37\69\56\37\65\69\37\65\69\34\41\41\40\41\10")()
    print("已加载！")
end)

Button(UiowpTab, "皮脚本", function()
    getgenv().XiaoPi="皮脚本QQ群1002100032" loadstring(game:HttpGet("https://raw.githubusercontent.com/xiaopi77/xiaopi77/main/QQ1002100032-Roblox-Pi-script.lua"))()
    print("已加载！")
end)

Button(UiowpTab, "逆光脚本", function()
    getgenv().NiGuang = "逆光Q群980694674"loadstring(game:HttpGet("https://raw.githubusercontent.com/lool8/-/refs/heads/main/%E9%80%86%E5%85%89.lua"))()
    print("已加载！")
end)
print("脚本界面加载已完成，尽情享用!")
