# asrock-deskmini-110-hackintosh

#### Hardware:
* [Intel® i5-6500 Skylake](https://ark.intel.com/content/www/us/en/ark/products/88184/intel-core-i5-6500-processor-6m-cache-up-to-3-60-ghz.html)
* Intel® HD Graphics 530
* [BCM94350ZAE/DW1820A](https://www.tonymacx86.com/threads/bcm94350zae-dw1820a-only-802-11n-wifi-and-no-bluetooth-devices.250592/page-4)
* 256 SSD (M.2 NVMe SSD)
* DDR4 16G RAM (8Gb x 2)
* macOS High Sierra 10.13.6
* Clover + MultiBeast(optional) + Unibeast(optional)

![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/desktop.jpg)
![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/4k.jpg)
![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/remove-theme.png)
![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/remove-clover-boot.jpg)

#### Working:
* ✅ Graphics acceleration (4K 60Hz)
* ✅ Audio
* ✅ WiFi
* ✅ Audio
* ✅ Bluetooth
* ✅ USB 2.0 & 3.0

#### Not working:
* sleep/wake (which in fact I don't care)

#### Not tested yet:
* Handoff
* Continuity


#### rebuild cache
```
sudo chmod -R 755 /Library/Extensions
sudo chown -R root:wheel /Library/Extensions
sudo chmod -R 755 /System/Library/Extensions
sudo chown -R root:wheel /System/Library/Extensions
sudo touch /System/Library/Extensions && sudo kextcache -u /
```

#### Fix HD530 glitches
https://www.tonymacx86.com/threads/skylake-intel-hd-530-graphics-glitch-fix.206410
```
<dict>
    <key>Broadcom</key>
    <dict>
            <key>CFBundleIdentifier</key>
            <string>com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport</string>
            <key>IOClass</key>
            <string>BroadcomBluetoothHostControllerUSBTransport</string>
            <key>IOProviderClass</key>
            <string>IOUSBHostDevice</string>
            <key>idProduct</key>
            <integer>25618</integer>
            <key>idVendor</key>
            <integer>2652</integer>
    </dict>
</dict>    
```

#### DW1820A inject
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
