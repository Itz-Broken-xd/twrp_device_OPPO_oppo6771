Unofficial TWRP for Oppo A91 (CPH2021) and Oppo F15 (CPH2001) running Android 11. \
<b>⚠️Recovery does not work on the PCPM00 model.<b>
<hr>

### Installation
Since this phone has fastboot disabled it is necessary to use alternative tools. I recommend using [MTKClient](https://github.com/bkerler/mtkclient). \
Just download the latest recovery from Releases and flash the recovery.bin file to recovery partition.

⚠️ After flashing, when device is set to boot to recovery mode, it might show a dm-verity
error. \
For fix press the power button once to continue booting otherwise device will shut down. 

<hr>

### How to build
Use the minimal manifest twrp aosp 11 [here](https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp/tree/twrp-11) \
Clone this repository as it is the device tree under `[location of your manifest]\device\OPPO\OP4B9B`
and use these commands:
```
source build/envsetup.sh
export ALLOW_MISSING_DEPENDENCIES=true
lunch twrp_OP4B9B-eng
export TW_DEVICE_VERSION
mka -j$(nproc --all) recoveryimage
```
