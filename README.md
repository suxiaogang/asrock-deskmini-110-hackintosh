# asrock-deskmini-110-hackintosh

#### Hardware:
* [Intel® i5-6500 Skylake](https://ark.intel.com/content/www/us/en/ark/products/88184/intel-core-i5-6500-processor-6m-cache-up-to-3-60-ghz.html)
* Intel® HD Graphics 530
* [BCM94350ZAE/DW1820A](https://www.tonymacx86.com/threads/bcm94350zae-dw1820a-only-802-11n-wifi-and-no-bluetooth-devices.250592)
* PCIe m2 NVMe 256SSD
* DDR4 16G RAM
* macOS Mojave 10.14.6 (18G84)

![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/desktop.jpg)
![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/4k.jpg)
![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/clover-theme.png)
![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/remove-clover-boot.jpg)

#### Working:
* ✅ Graphics acceleration (4K 60Hz and I'm using 1920*1080 HiDPi)
* ✅ Audio
* ✅ WiFi (2.4G & 5G) / Ethernet
* ✅ Bluetooth
* ✅ USB 2.0 & 3.0
* ✅ iCloud

#### Not Perfect:
* Audio

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

#### DW1820A/BCM94350ZAE/BCM94356ZEPA50DX插入的正确姿势
```
DW1820A/BCM94350ZAE/BCM94356ZEPA50DX插入的正确姿势
https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html

将【DW1820A蓝牙专用程序】 解压缩到/EFI/CLOVER/kexts/Other目录下，重启即可。
```

#### 修复声卡杂音
摘自远景论坛: 之前的CLOVER文件，声卡能正常驱动，不过耳机会杂音（之前没发觉到），可在clover的kexts文件夹里放入CodecCommander.kext驱动，并重建缓存，即可解决杂音问题。
或者也可注入其他layoutID，一样可以解决耳机杂音问题，不过麦克风会有点问题。或者调节左右声道也可以解决。不过还是推荐第一种。

https://bitbucket.org/RehabMan/os-x-eapd-codec-commander/downloads/

![screenshot](https://raw.githubusercontent.com/suxiaogang/asrock-deskmini-110-hackintosh/master/audio.jpg)

#### change device name 
```
sudo scutil --set ComputerName "newname"
sudo scutil --set LocalHostName "newname"
sudo scutil --set HostName "newname"
```


#### change about this mac section
```
/Applications/Utilities/System Information.app/Contents/Resources/SystemLogo.tiff
```

Clover Themes
https://sourceforge.net/p/cloverefiboot/themes/ci/master/tree/themes