Pixel Experience /Android 13 (AOSP)

```
repo init -u https://github.com/PixelExperience/manifest -b thirteen
```
Make a directory named local_manifests under .repo, and create a new manifest file, for example lisa_local.xml
and then paste the following

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
<remote name="github"
	fetch="https://github.com/" />

<project path="device/xiaomi/lisa"
	name="dkpost3/device_xiaomi_lisa-oss"
	remote="github"
	revision="thirteen" />
</manifest>
```

```
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Build ###
```bash
$ . build/envsetup.sh
$ lunch aosp_lisa-userdebug
$ mka bacon -j$(nproc --all)
```
