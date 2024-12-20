# HGL Flatpak 

This repository contains the Flatpak package for the Heroic Games Launcher.

# Bug reports
Please report bugs here that only happen in the flatpak version. Bugs that happen regardless of the pkg go [here](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher)

# Wayland

Please note that the Wayland backend is disabled by default due to compatibility issues with NVIDIA.

To enable the Wayland backend, set the following environment variable
`ELECTRON_OZONE_PLATFORM_HINT=auto`
