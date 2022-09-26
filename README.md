# XIVLauncherCN Flatpak

This repo contains the work in progress flatpak for XIVLauncherCN.Core.

## Getting started
```bash
flatpak-builder --user --force-clean build-dir cn.ottercorp.xivlaunchercn.yml --install
flatpak run cn.ottercorp.xivlaunchercn
```

## nuget-dependencies.json
Flatpak build process does not have network access (strictly on flathub apparently). Therefore we need to specify all nuget sources beforehand. To generate that file you can follow the following steps:
```bash
git clone https://github.com/ottercorp/FFXIVQuickLauncher.git
cd FFXIVQuickLauncher/src/XIVLauncher.Core
wget https://raw.githubusercontent.com/flatpak/flatpak-builder-tools/master/dotnet/flatpak-dotnet-generator.py # Then manually change the platform version from 21.08 to either 22.08 or the correct one
python3 flatpak-dotnet-generator.py nuget-dependencies.json XIVLauncher.Core.csproj
```

(FYI: Don't try that in /tmp)

## Notes
* Dalamud does not store its files in `.config/XIVLauncher` (as of now) but in `~/.var/app/cn.ottercorp.xivlaunchercn/config/XIVLauncher`.
