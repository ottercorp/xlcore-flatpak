# XIVLauncher Flatpak

This repo contains the work in progress flatpak for XIVLauncher.Core.

## Getting started
```bash
flatpak-builder --user --force-clean build-dir dev.goats.xivlauncher.yml --install
flatpak run dev.goats.xivlauncher
```

## Notes
* Dalamud does not store its files in `.config/XIVLauncher` (as of now) but in `~/.var/app/dev.goats.xivlauncher/config/XIVLauncher`.