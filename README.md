local Settings = {
    InviteCode = "urs2cRBHXU"
  }
  
  -- Objects
  local HttpService = game:GetService("HttpService")
  local RequestFunction
  
  if syn and syn.request then
    RequestFunction = syn.request
  elseif request then
    RequestFunction = request
  elseif http and http.request then
    RequestFunction = http.request
  elseif http_request then
    RequestFunction = http_request
  end
  
  local DiscordApiUrl = "http://127.0.0.1:%s/rpc?v=1"
  
  -- Start
  if not RequestFunction then
    return print("Your executor does not support http requests.")
  end
  
  for i = 6453, 6464 do
    local DiscordInviteRequest = function()
        local Request = RequestFunction({
            Url = string.format(DiscordApiUrl, tostring(i)),
            Method = "POST",
            Body = HttpService:JSONEncode({
                nonce = HttpService:GenerateGUID(false),
                args = {
                    invite = {code = Settings.InviteCode},
                    code = Settings.InviteCode
                },
                cmd = "INVITE_BROWSER"
            }),
            Headers = {
                ["Origin"] = "https://discord.com",
                ["Content-Type"] = "application/json"
            }
        })
    end
    spawn(DiscordInviteRequest)
  end

  local colors = {
    SchemeColor = Color3.fromRGB(0,255,255),
    Background = Color3.fromRGB(0, 0, 0),
    Header = Color3.fromRGB(0, 0, 0),
    TextColor = Color3.fromRGB(255,255,255),
    ElementColor = Color3.fromRGB(20, 20, 20)
}

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Untitled Hood / Dupe Cash", "Sentinel")
local Tab = Window:NewTab("Dupe")
local Section = Tab:NewSection("Dupe Lol")






local Workspace = game:GetService("Workspace")
local Players = game.Players.LocalPlayer

local Character = Players.Character




function Buy(Object)
    local Object = Object
    local LockPicker = Workspace.Ignored.Shop[Object]
    Character.HumanoidRootPart.CFrame = LockPicker.Head.CFrame + Vector3.new(0, 3, 0)
    wait(0.5)
    fireclickdetector(LockPicker.ClickDetector)
    fireclickdetector(LockPicker.ClickDetector)
end

Buy("[Revolver] - $1300")

wait(0.5)


wait(0.5)

game.ReplicatedStorage:FindFirstChild(".gg/untitledhood"):FireServer(
    "Reload",
    {
        Name = "[Revolver]", --// reminder: [Double-Barrel SG] or [Revolver] works for any gun but i put it here so i can just copy and paste whenever i want to
        Parent = Game.Players.LocalPlayer.Backpack,
        ClassName = "Tool",
        Ammo = {Value = math.huge*9e9},
        MaxAmmo = {Value = 0},
        GunScript = game:GetService("Players").LocalPlayer.Backpack["[Revolver]"].GunScript,
        Handle = game:GetService("Players").LocalPlayer.Backpack["[Revolver]"].Handle
    }
)

wait(2)



_G.Aiden = Players --CHANGE NAME HERE

_G.Amount = 999999999999 --999999999999

_G.Amount2 = 7777777777
---

_G.Reset = 1 

Section:NewButton("Give 999999999999 Cash", "", function()

game.ReplicatedStorage:FindFirstChild(".gg/untitledhood"):FireServer(
    "Reload",
    {
         Name = "[Revolver]",
        Parent = Game.Players.LocalPlayer.Backpack,
        ClassName = "Tool",
        Ammo = game:GetService("Players")[_G.Aiden].DataFolder.Currency,
        MaxAmmo = {Value = _G.Amount},
        GunScript = game:GetService("Players").LocalPlayer.Backpack["[Revolver]"].GunScript,
        Handle = game:GetService("Players").LocalPlayer.Backpack["[Revolver]"].Handle
    }
) 
end)





       
Section:NewButton("Reset Cash", "", function()

game.ReplicatedStorage:FindFirstChild(".gg/untitledhood"):FireServer(
    "Reload",
    {
        Name = "[Revolver]",
        Parent = Game.Players.LocalPlayer.Backpack,
        ClassName = "Tool",
        Ammo = game:GetService("Players")[_G.Aiden].DataFolder.Currency,
        MaxAmmo = {Value = _G.Reset},
        GunScript = game:GetService("Players").LocalPlayer.Backpack["[Revolver]"].GunScript,
        Handle = game:GetService("Players").LocalPlayer.Backpack["[Revolver]"].Handle
    }
) 
end)




--game:GetService("Players").BadSnif






Section:NewTextBox("Username", "the guy who receive cash", function(value)
    _G.Aiden = value
end)


local Tab = Window:NewTab("HotKeys")
local Section = Tab:NewSection("HotKeys")
Section:NewKeybind("HotKeys", "KeybindInfo", Enum.KeyCode.Q, function()
    Library:ToggleUI()
end)

local Tab = Window:NewTab("Credits")
local Section = Tab:NewSection("Credit 03.s#6260")
Section:NewButton("Copy Discord", "Credits", function()
    setclipboard("https://discord.gg/urs2cRBHXU")("Clicked")
end)

local Section = Tab:NewSection("Youtube : Reality")

Section:NewButton("Copy Youtube", "Copy", function()
    setclipboard("https://www.youtube.com/channel/UC92aBBDpwMA8DIv0UArKDKA/videos")("Clicked")
end)

local Section = Tab:NewSection("Youtube : Klee Dan Paiimon")

Section:NewButton("Copy Youtube 2", "Copy", function()
    setclipboard("https://www.youtube.com/channel/UC46AtUT2wYwjxDImBBWmKlw/videos")("Clicked")
end)
