# TWRP for Tolino eInk reader devices

### Known working devices
- Tolino Page
- Tolino Page 2
- Tolino Shine 2 HD
- Tolino Vision 2 HD
- Tolino Vision 3 HD
- Tolino Vision 4 HD
- Tolino Epos

### How to build TWRP
1. `repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0`
2. `repo sync`
3.  Clone this repo to `device/TOLINO/tolino_generic`
4.  Apply patches from `device/TOLINO/tolino_generic/patches` directory: `cd bootable/recovery && git apply ../../device/TOLINO/tolino_generic/patches/* && cd ../..`
5.  Run the commands below ↓
```
. build/envsetup.sh
lunch omni_tolino_generic-userdebug
mka recoveryimage
```

If you want to use an theme adjusted for eInk screens:
1. Clone [monochrome theme repo](https://github.com/Ryogo-Z/twrp_monochrome_portrait_hdpi_theme/) into `<twrp_repo>/device/TOLINO/tolino_generic/theme`
2. Uncomment `TW_IMX_EINK_MONOCHROME` in `BoardConfig.mk`

If everything goes well, your image will be at out/target/product/tolino_generic/recovery.img
