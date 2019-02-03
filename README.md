# asrock-deskmini-110-hackintosh
asrock deskmini 110 hackintosh

DeskMini 110 (case+motherboard+PSU)

#### Hardware:
* Intel i5-6400
* Intel HD Graphics 530
* BCM94350ZAE/DW1820A
* 240GB SSD
* DDR4 8G x 2
* macOS High Sierra 10.14.3
* Clover+MultiBeast+Unibeast

#### Not working:
Bluetooth
Sleep/wake

#### Working:
Graphics acceleration (4K 60Hz)
Audio
WiFi
Analog audio
USB 2.0 & 3.0

#### Not tested yet:
    Handoff
    Continuity


#### Fix HD530 glitches
https://www.tonymacx86.com/threads/skylake-intel-hd-530-graphics-glitch-fix.206410
```
<key>Devices</key>
<dict>
    <key>AddProperties</key>
    <array>
        <dict>
            <key>Device</key>
            <string>IntelGFX</string>
            <key>Key</key>
            <string>AAPL,GfxYTile</string>
            <key>Value</key>
            <data>
            AQAAAA==
            </data>
        </dict>
    </array>
</dict>
```
