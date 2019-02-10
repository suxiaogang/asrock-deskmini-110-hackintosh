# asrock-deskmini-110-hackintosh

#### Hardware:
* [Intel® i5-6400 Skylake](https://ark.intel.com/products/88185/Intel-Core-i5-6400-Processor-6M-Cache-up-to-3-30-GHz-)
* Intel® HD Graphics 530
* [BCM94350ZAE/DW1820A](https://www.tonymacx86.com/threads/bcm94350zae-dw1820a-only-802-11n-wifi-and-no-bluetooth-devices.250592/page-4)
* 240GB SSD
* DDR4 8G RAM x 2
* macOS High Sierra 10.14.3
* Clover+MultiBeast+Unibeast

![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/desktop.jpg)

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

```
sudo chmod -R 755 /Library/Extensions
sudo chown -R root:wheel /Library/Extensions
sudo chmod -R 755 /System/Library/Extensions
sudo chown -R root:wheel /System/Library/Extensions
sudo touch /System/Library/Extensions && sudo kextcache -u /
```
#### Fix HD530 glitches
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
