# XIVLauncher Flatpak

This repo contains the work in progress flatpak for XIVLauncher.Core.

## Getting started
```bash
flatpak-builder --user --force-clean build-dir dev.goats.xivlauncher.yml --install
flatpak run dev.goats.xivlauncher
```

## output.json
Flatpak build process does not have network access (strictly on flathub apparently). Therefore we need to specify all nuget sources beforehand. To generate that file you can follow the following steps:
```bash
git clone https://github.com/goatcorp/FFXIVQuickLauncher.git
cd FFXIVQuickLauncher/src/XIVLauncher.Core
curl -LO https://github.com/flatpak/flatpak-builder-tools/blob/master/dotnet/flatpak-dotnet-generator.py
python3 flatpak-dotnet-generator.py output.json XIVLauncher.Core.csproj
```

(FYI: Don't try that in /tmp)

## Notes
* Dalamud does not store its files in `.config/XIVLauncher` (as of now) but in `~/.var/app/dev.goats.xivlauncher/config/XIVLauncher`.