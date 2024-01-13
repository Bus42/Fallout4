# .ini Files for (F)All Out War

Back up your original .ini files and replace them with these.

These include the necessary tweaks to run mods as well as to enable logging for Buffout4. You will need to customize a few settings, I suggest using BethINI
however, you can set them manually.

These are the primary settings you may want to change (tweaked to balance performance on _my_ setup)

```toml
[Display]
iSizeW=6840
iSizeH=2160
[General]
bEnableRainOcclusion=0
bLensFlare=0
bReflectLODObjects=0
bReflectLODLand=0
bReflectSky=0
bReflectLODTrees=0
```

## Steam Launch Options

I run Kubuntu 22.04 with an AMD Ryzen 5 3600 and a RTX 3060 via Proton Experimental. I use the following launch options in Steam:

```cli
WINEDLLOVERRIDES="xaudio2_7=n,b;d3dcompiler_47=n;dxgi=n,b" PROTON_ENABLE_NVAPI=1 PROTON_NO_ESYNC=1 ENABLE_VKBASALT=1 MANGOHUD_CONFIGFILE=/home/greg/.steam/debian-installation/steamapps/common/Fallout\ 4/MangoHud.conf mangohud gamemoderun %command%
```

Maybe in the future, I will create other branches for different performance levels.

I would liked to have included a folder with MCM presets, but MCM does not seem to play nice with Steam on Linux in my current config for some reason. If you would like to contribute one, create a branch named feature/mcm-settings and upload your presets then create a Pull Request and I'll add them!

## Available Console Commands

- `rff` - [Rusty Face Fix](https://www.nexusmods.com/fallout4/mods/31028?_gl=1*pjlqx5*_ga*MTIzNjgwMzk0Mi4xNjk4MjA3MzQ1*_ga_N0TELNQ37M*MTcwNTE4NzQyMC45My4xLjE3MDUxODc1ODIuMC4wLjA.): Fixes the rusty face bug, select the affected NPC and type `rff` in the console (works on the player, too).
- `rename` - [Rename Anything](https://www.nexusmods.com/fallout4/mods/22105?_gl=1*14ykf5c*_ga*MTIzNjgwMzk0Mi4xNjk4MjA3MzQ1*_ga_N0TELNQ37M*MTcwNTE4NzQyMC45My4xLjE3MDUxODc1MzUuMC4wLjA.): Rename any NPC, container, weapon, armor, etc. by selecting it and typing `rename <new name>` in the console.
- `help` - [Console Commands Extender](https://www.nexusmods.com/fallout4/mods/47328?_gl=1*1yeuva8*_ga*MTIzNjgwMzk0Mi4xNjk4MjA3MzQ1*_ga_N0TELNQ37M*MTcwNTE4NzQyMC45My4xLjE3MDUxODc0NDkuMC4wLjA.): Adds a simplified search function to the console, type `help <search term>` to search for a command.

## Scripts

### settlement

This script will increase the build limit for settlements. It is a modified version of the script found [here](https://www.nexusmods.com/fallout4/mods/818/). Save it as _settlement.txt_ to your Fallout 4 directory and run it from the developer console by typing `bat settlement`.

```bash
modav 349 500000.00
modav 34B 500.00
getav 349
getav 34B
```

### reset_materials

This script will reset the quantity of several common building materials to 999 to make building easier (while avoiding astronomical quantities). Save it as _reset_materials.txt_ to your Fallout 4 directory and run it from the developer console by typing `bat reset_materials` with any container - such as the workshop bench, crafting bench or power armor station - selected.

```bash
removeItem 001BF72D 999
additem 001BF72D 999 ;Acid
removeItem 001BF72E 999
additem 001BF72E 999 ;Adhesive
removeItem 0006907A 999
additem 0006907A 999 ;Aluminum
removeItem 001BF72F 999
additem 001BF72F 999 ;Antiseptic
removeItem 000AEC5C 999
additem 000AEC5C 999 ;Asbestos
removeItem 000AEC5B 999
additem 000AEC5B 999 ;Ballistic Fiber
removeItem 000AEC5D 999
additem 000AEC5D 999 ;Bone
removeItem 000AEC5E 999
additem 000AEC5E 999 ;Ceramic
removeItem 0006907B 999
additem 0006907B 999 ;Circuitry
removeItem 000AEC5F 999
additem 000AEC5F 999 ;Cloth
removeItem 00106D99 999
additem 00106D99 999 ;Concrete
removeItem 0006907C 999
additem 0006907C 999 ;Copper
removeItem 000AEC60 999
additem 000AEC60 999 ;Cork
removeItem 0006907D 999
additem 0006907D 999 ;Crystal
removeItem 001BF730 999
additem 001BF730 999 ;Fertilizer
removeItem 00069087 999
additem 00069087 999 ;Fiber Optics
removeItem 000AEC61 999
additem 000AEC61 999 ;Fiberglass
removeItem 0006907E 999
additem 0006907E 999 ;Gears
removeItem 00069085 999
additem 00069085 999 ;Glass
removeItem 000AEC62 999
additem 000AEC62 999 ;Gold
removeItem 000AEC63 999
additem 000AEC63 999 ;Lead
removeItem 000AEC64 999
additem 000AEC64 999 ;Leather
removeItem 00069086 999
additem 00069086 999 ;Nuclear Material
removeItem 001BF732 999
additem 001BF732 999 ;Oil
removeItem 0006907F 999
additem 0006907F 999 ;Plastic
removeItem 00106D98 999
additem 00106D98 999 ;Rubber
removeItem 00069081 999
additem 00069081 999 ;Screw
removeItem 000AEC66 999
additem 000AEC66 999 ;Silver
removeItem 00069082 999
additem 00069082 999 ;Spring
removeItem 000731A4 999
additem 000731A4 999 ;Steel
removeItem 000731A3 999
additem 000731A3 999 ;Wood
```

### npc_boost

A simple script to boost the stats of the selected NPC. Save it as _npc_boost.txt_ to your Fallout 4 directory and run it from the developer console by typing `bat npc_boost` with any NPC selected.

```bash
modav strength 3
modav perception 3
modav endurance 3
modav charisma 3
modav intelligence 3
modav agility 3
modav luck 3
```
