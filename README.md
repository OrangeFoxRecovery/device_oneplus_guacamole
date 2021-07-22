# Device Tree for OnePlus 7/7 Pro/7 Pro 5G (guacamole, guacamoleb, guacamolec)

The OnePlus 7 Pro (codenamed _"guacamole"_) is a flagship smartphone from OnePlus.
It was released in May 2019.




## Compile

First clone the fox_9.0 manifest repo:

```
repo init --depth=1 -u https://gitlab.com/OrangeFox/Manifest.git -b fox_9.0
```
Then add these string to .repo/manifests/remove.xml


Then add these projects to .repo/local_manifests/roomservice.xml (If you don't have it, you can add them to .repo/manifest.xml): 

```xml
<project name="OrangeFoxRecovery/device_oneplus_guacamole" path="device/oneplus/guacamole" remote="github" revision="fox_9.0" />
```

Now you can sync your source:

```
repo sync -j8 --force-sync
```
Finally execute these:

```
. build/envsetup.sh
lunch omni_guacamole-eng 
mka recoveryimage 
```

To test it:

```
fastboot boot out/target/product/guacamole/recovery.img
```

Kernel Source: https://gitlab.com/HolyAngel/op7
## Credits

@Sushrut1101
@mauronofrio
I want to say a big thanks to @twinnfamous
Thanks to @dianlujitao for the base multidevice commit: https://github.com/TeamWin/android_device_oneplus_oneplus3/tree/android-9.0/init
