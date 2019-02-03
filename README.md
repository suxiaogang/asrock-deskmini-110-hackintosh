# asrock-deskmini-110-hackintosh
asrock deskmini 110 hackintosh

DeskMini 110 (case+motherboard+PSU)

#### Hardware:
    Intel i5-7500
    Intel HD Graphics 630
    BCM94352Z
    macOS 10.12.6
    Clover+MultiBeast+Unibeast

#### Not working:

HDMI audio (this should work, I'll try a vanilla install later)

Sleep/wake

#### Working:

Graphics acceleration
WiFi
Bluetooth
Analog audio
USB only speakers
#### Not tested yet:

    Handoff
    Continuity

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
