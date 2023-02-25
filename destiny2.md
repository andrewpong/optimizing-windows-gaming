# Destiny

## Reduce graphics settings 
Set ingame graphics settings to Low to improve performance, stop flashbanging yourself, etc. haha
## NVIDIA: Use DLDSS to improve image quality with minimum performance penalty
You can use NVIDIA RTX Deep Learning Super Sampling to make Destiny look better.
* I have a 4K 144Hz Sony M9, so I set a DSR factor of `1.78x DL` in Nvidia Global Settings with `33% smoothness`, so Destiny renders at 5120x2880 and I maintain 100 FPS, but I cap mine at 95 due to HDR 10-bit color bandwidth limits on the cable.
* This can work the other way to run Destiny at a lower resolution, then use NVIDIA RTX Deep Learning to upscale up to native resolution
## Use NVIDIA Reflex
NVIDIA Reflex is supported by Destiny, and will modify several GPU parameters to reduce frame rendering and queing to minimize latency to the monitor. To enable it do the following:
* Open `%APPDATA%\Bungie\DestinyPC\prefs\cvars.xml`
* Under the `graphics namespace`, add or set `<cvar name="low_latency_mode" value="2" />` you may need to test between values `1` and `2` to see what works with your system. Disable this change by setting the value to `0`.
## Disable game overlays if possible
I've confirmed slight FPS drops when Steam's overlay is enabled. Disable other overlays too for Destiny at least (e.g. Discord, Xbox Game Bar, Overwolf, Destiny Tracker, etc.)


# Networking
Use a wired connection if possible, and use a decent router.
## Configure your router
* Enable UPnP
* QoS Destiny traffic if able to in router so downloads and other high bandwidth activities doesn't lag you out
* Configure port availability and forwarding per Bungie's guidance: https://help.bungie.net/hc/en-us/articles/360049496751-Advanced-Troubleshooting-UPnP-Port-Forwarding-and-NAT-Types
### Open ports for Destiny

| Platform         | TCP Destination Ports                                                       | UDP Destination Ports                                                      |
| ---------------- | --------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| PC               | 80, 443, 1119-1120, 3074, 3724, 4000, 6112-6114<br>7500-7509<br>30000-30009 | 80, 443, 1119-1120, 3074, 3097-3196, 3724, 4000, 6112-6114,<br>27015-27200 |
| Xbox Series X, S | 53, 80, 3074                                                                | 53, 88, 500, 3544, 3074, 27015-27200                                       |
| PlayStation 5    | 80, 443, 1935, 3478-3480                                                    | 3478, 3479, 49152-65535, 27015-27200                                       |
| PlayStation 4    | 80, 443, 1935, 3478-3480<br>7500-7509<br>30000-30009                        | 2001, 3074-3173, 3478-3479, 27015-27200                                    |
| Xbox ONE         | 53, 80, 443, 3074<br>7500-7509<br>30000-30009                               | 53, 88, 500, 3074, 3544, 4500, 1200-1299, 1001, 27015-27200                |
| PlayStation 3    | 80, 443, 5223, 3478-3480, 8080<br>7500-7509<br>30000-30009                  | 3478-3479, 3658<br>3074, 1001                                              |
| Xbox 360         | 53, 80, 443, 3074<br>7500-7509<br>30000-30009                               | 53, 88, 3074, 1001                                                         |

### Forward ports for Destiny matchmaking
Forwarding these ports will set your NAT type in Destiny to Open (Type 1 for PSN), which means:
* All network connections are allowed between the platform and other players.
* Players will be able to play and chat with any other player.

| Platform         | TCP Destination Ports                                                                         | UDP Destination Ports           |
| ---------------- | --------------------------------------------------------------------------------------------- | ------------------------------- |
| PC               | N/A                                                                                           | 3074, 3097                      |
| Xbox Series X, S | 3074                                                                                          | 88, 500, 3074, 3544, 4500       |
| Xbox ONE         | 3074                                                                                          | 88, 500, 1200, 3074, 3544, 4500 |
| Xbox 360         | 3074                                                                                          | 88, 3074                        |
| PlayStation 5    | If your router supports Protocol Both, use 1935,3074,3478-3480<br>If not, use 1935, 3478-3480 | 3074, 3478-3479                 |
| PlayStation 4    | 1935, 3478-3480                                                                               | 3074, 3478-3479                 |
| PlayStation 3    | 3478-3480, 5223, 8080                                                                         | 3074, 3478-3479, 3658           |

# GPU Hardware

## Reduce power draw and maintain performance
* Use MSI afterburner to undervolt your GPU to reduce heat, then you can crank up allowed Power Maximum in Geforce Experience overlay to max (mine is 115%)
* You can also flatten our your voltage/GPU core speed curve to reduce power draw/heat without impacting performance. 
* Here's the main guide I used: https://bjorn3d.com/2020/10/undervolting-the-rtx-3080-and-the-rtx3090/
* A different guide for the RTX 3080 FE: https://www.reddit.com/r/nvidia/comments/j63hcs/my_experience_undervolting_the_3080_fe/
## Reduce GPU usage from other programs
* Disable HW acceleration to reduce GPU usage, generally; Destiny doesn't use more than a couple CPU cores so the extra processor load isn't much of a deal.
## Reinstall or replace stock thermal pads
Some people are lucky with stock pad installation so aftermarket ones didn't help much, but others weren't so lucky: my temps dropped 10 C as some of my pads were really crooked or poorly installed. Dunno why the stock ones are so bad. Be super careful about confirming the height of the current pads and order the correct set! 
* I used Kritical Pads for my 3080 FEhttps://kriticalpads.com/nvidia-3080-fe-v2. 
* If you don't know what to purchase, email Kritical Pads as they're super friendly: kritpad@kriticalpads.com


# General Hardware

## Keep temps down and dust out!
Track temps and power draw for inefficient cooling - heat means less performance!
## Configure X570 BIOS settings correctly
* Here's a guide I used: https://www.overclock.net/threads/5800x3d-owners.1798046/
* ... but I'm lazy and after the latest update wiped my settings I just confirm XMP then ran Ryzen Master's Auto Optimization.
* Enable XMP profile for your RAM otherwise it'll run at stock settings.
* Configure the correct boost settings for your cooling type

# Drivers and Utilities

## Install the latest chipset drivers
* AMD X570: https://www.amd.com/en/support/chipsets/amd-socket-am4/x570
## Install the latest graphics drivers
### NVIDIA
Install the latest NVIDIA Studio driver that doesn't crash your game.
* (*Recommended*)  NVIDIA Studio driver 528.49: https://www.nvidia.com/download/driverResults.aspx/199662/en-us/
* (*Fallback, older*) NVIDIA Studio Driver 512.15:  https://www.nvidia.com/Download/driverResults.aspx/187302/en-us/
### AMD
Dunno, I don't use AMD.
* Install the latest driver for your model: https://www.amd.com/en/support/graphics/amd-radeon-rx-7000-series/amd-radeon-rx-7900-series/amd-radeon-rx-7900xtx

## Tune CPU performance
### AMD Ryzen Master 
Ryzen Master is a Windows program with an Auto Overclock feature; it can automatically overclock your CPU and test for stability by modifying CPU parameters, and it requires minimum effort: https://www.amd.com/en/technologies/ryzen-master)
### Bitsum ParkControl
Fiddle with Bitsum ParkControl to improve CPU scheduling and prioritization for Destiny automatically, set Windows Power Profiles, etc. This allows for max performance while gaming while activating more energy efficient Power Plans when not. Electricity prices are high for me, so I've been more energy conscious in general.

# Monitor/Display

## Use G-Sync/Adaptive sync
 * Use NVIDIA reflex if you have a supported monitor and mouse as listed here: https://www.nvidia.com/en-us/geforce/technologies/reflex/supported-products/
 * Make sure you set it up correctly - have your mouse plugged into your monitor, etc.

# Windows Settings

## Windows 10 and 11
* Enable Game Mode
* Enable Hardware-accelerated GPU scheduling
* Enable Variable Refresh Rate
* Use the Balanced Power Profile as it provides max performance for Ryzen processors in conjunction with the chipset drivers, no need to crutch on Max Performance anymore. Also, the Ryzen specific profiles aren't around anymore.
* Reduce system security if you want: Windows Security > Device Security: Core Isolation Settings > Disable Memory Integrity
## Windows 11
* Enable Optimizations for widowed games
* Enable Auto HDR (if compatible with monitor)

# Antivirus Settings

Exclude Destiny, BattleEye, etc. from AV scans; I'll post my exclusions as an example for Windows Defender ATP:
## Exclude processes
* `destiny2.exe`, 
* `destiny2launcher.exe`
## Exclude folders
* `D:\Games\Steam\steamapps\common\Destiny 2\`
## Exclude files
* `D:\Games\Steam\steamapps\common\Destiny 2\destiny2.exe` 
* `D:\Games\Steam\steamapps\common\Destiny 2\destiny2launcher.exe`

# Things I've read about that I could not confirm after testing
Below are things I've found that are either outdated with the engine updates, or just bad advice.

## Mouse polling lag with Destiny
1000hz refresh rates for mice might cause issues with Destiny's game engine, but I couldn't verify
## Improve performance by making your game look like a potato
Using NVIDIA Profile Inspector to set negative LOD clamping can make textures look like play-doh:
* Discussion thread here: https://forums.guru3d.com/threads/getting-nv-profile-inspector-to-have-an-effect-on-games-that-use-deferred-rendering-destiny-2.430951/
* Different thread here, toohttps://steamcommunity.com/sharedfiles/filedetails/?id=1884111121l
## Compatibility Mode fiddling
You can right click on the `Destiny2Launcher.exe` and/or `Destiny2.exe` binaries and mess around with Windows app Compatability Settings; some people reported improvements when disabling `fullscreen optimizations` or fiddling with `high DPI settings`, but I observed no change.
