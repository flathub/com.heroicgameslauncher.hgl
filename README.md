# Troubleshooting
## MangoHud integration
To use MangoHud with the Heroic Games Launcher, use `flatpak install org.freedesktop.Platform.VulkanLayer.MangoHud` in a terminal and pick the latest version available.

This will allow you to use the MangoHud option in the launcher.

### Access to personal MangoHud configuration
To allow the sandbox to access your personal non-sandboxed configuration for MangoHud, you can type the following in a terminal:
`flatpak override -u --filesystem=xdg-config/MangoHud:ro com.heroicgameslauncher.hgl`
This will grant HGL read-only access for the configuration files.

Afterwards, you may need to force an environment variable for MangoHud to detect your personal configuration. If needed, use the following command:
`flatpak override -u --env=MANGOHUD_CONFIGFILE=$HOME/.config/MangoHud/MangoHud.conf com.heroicgameslauncher.hgl`
The path needs to be absolute for the MangoHud environment variable to work. `$HOME` will automatically resolve to your home path and make the path absolute.

## Custom installation path
The default installation path is `~/Games/Heroic`. This folder will be automatically created if it does not exist.

If you want to use a custom installation path, you first have to give the Flatpak sandbox the permission to the path and then set it on the launcher afterwards.

For instance, if you want your instalation path to be `~/MyHeroicGames`, you need to add the following override:
`flatpak override -u --filesystem=~/MyHeroicGames:create com.heroicgameslauncher.hgl`

For external drives, the HGL sandbox already has complete access to `/media` and `/run/media`, so you just need to create a folder there and set it in the launcher afterwards.
