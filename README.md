_G.FastAttack = true
_G.AutoClick = true
loadstring(game:HttpGet("https://raw.githubusercontent.com/Namfonhub/FastAttackFree/main/FastAttackByNamfonHub.lua"))()
game.Players.LocalPlayer.Character.Humanoid.Health = 0
game.Lighting.FogEnd = 100000
game.Lighting.FogStart = 0
game.Lighting.ClockTime = 14
game.Lighting.Brightness = 2
game.Lighting.GlobalShadows = false
task.spawn(function()
    while wait() do
        for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"]:GetChildren()) do
            pcall(function()
                if v.Name == ("CurvedRing") or v.Name == ("SlashHit") or v.Name == ("SwordSlash") or v.Name == ("SlashTail") or v.Name == ("Sounds") then
                    v:Destroy()
                end
            end)
        end
    end
end)

if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
    game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
end
if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
    game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
end
 
(getgenv()).Config = {
 ["FastAttack"] = true,
 ["ClickAttack"] = true
} 
 
coroutine.wrap(function()
local StopCamera = require(game.ReplicatedStorage.Util.CameraShaker)StopCamera:Stop()
    for v,v in pairs(getreg()) do
        if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework then
             for v,v in pairs(debug.getupvalues(v)) do
                if typeof(v) == "table" then
                    spawn(function()
                        game:GetService("RunService").RenderStepped:Connect(function()
                            if getgenv().Config['FastAttack'] then
                                 pcall(function()
                                     v.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                                     v.activeController.attacking = false
                                     v.activeController.increment = 8
                                     v.activeController.blocking = false   
                                     v.activeController.hitboxMagnitude = 500
    		                         v.activeController.humanoid.AutoRotate = true
    	                      	     v.activeController.focusStart = 0
    	                      	     v.activeController.currentAttackTrack = 0
                                     sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRaxNerous", math.huge)
                                 end)
                             end
                         end)
                    end)
                end
            end
        end
    end
end)();
 
spawn(function()
    game:GetService("RunService").RenderStepped:Connect(function()
        if getgenv().Config['ClickAttack'] then
             pcall(function()
                game:GetService'VirtualUser':CaptureController()
			    game:GetService'VirtualUser':Button1Down(Vector2.new(0,1,0,1))
            end)
        end
    end)
end)
_G.Color = Color3.fromRGB(255, 0, 0)
_G.Logo = 0


local Evil = loadstring(game:HttpGet("https://newpchx2.0xlii.repl.co/AllUI/Protected_9405524596134885.lua"))()
local Win = library:Evil("kaitan","KOBEN",_G.Logo )

local tab1 = Win:CraftTab('Main')
local page1 = tab1:CraftPage('Main',1)

local player = page1:Label('Fast attack')


page1:Dropdown("FAST ATTACK",{"0.175","200","fast attack kaitan300"},{""},function(v)
    print(v)
end)

page1:Slider("Fast attack pcแบบเลื่อนเลื่อนน้อยยิงเร็ว",true,1,100,1,function(value)
    print(value)
end)

page1:Label('kaitan')


page1:Toggle('Fast attack',nil,function(a)
    print(a)
end)

loadstring(game:HttpGet("https://raw.githubusercontent.com/GooD1020/sazx_uino_kaitan/main/README.md"))()
