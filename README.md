# asrock-deskmini-110-hackintosh

#### Hardware:
* [Intel® i5-6400 Skylake](https://ark.intel.com/products/88185/Intel-Core-i5-6400-Processor-6M-Cache-up-to-3-30-GHz-)
* Intel® HD Graphics 530
* [BCM94350ZAE/DW1820A](https://www.tonymacx86.com/threads/bcm94350zae-dw1820a-only-802-11n-wifi-and-no-bluetooth-devices.250592/page-4)
* 240GB SSD
* DDR4 8G RAM x 2
* macOS High Sierra 10.14.3
* Clover+MultiBeast+Unibeast

!(https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/desktop.jpg)

#### Not working:
* Bluetooth
* Sleep/wake

Bluetooth device show up in USB ports but not working

#### Working:
* Graphics acceleration (4K 60Hz)
* Audio
* WiFi
* Analog audio
* USB 2.0 & 3.0

#### Not tested yet:
* Handoff
* Continuity

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
