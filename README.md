![ASCP OS](https://github.com/Pixelify-AOSP/manifest/raw/sixteen-qpr2/Banner.png)

# The ASCP Project | Android Open Source Software
An Android Operating System Based On AOSP.

# Initialize local repository

```bash
repo init -u https://github.com/Pixelify-AOSP/manifest.git -b sixteen-qpr2 --git-lfs
```
Or if you want to save some system space and don't care about repo history depths:
```bash
repo init -u https://github.com/vos-ascp/pos_manifest.git -b sixteen-qpr2 --git-lfs --depth=1
```

# Sync up

```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

# Build

- Set up the build environment
```bash
. build/envsetup.sh
```

- Lunch a target
```bash
lunch custom_codename-bp4a-user
```

- Build Configuration
Customize the build by defining configuration flags in your device makefile (e.g., `ascp_<device_codename>.mk` or `custom_device.mk`):

```make
# ASCP Configuration Flags
ASCP_MAINTAINER := Maintainer_name
WITH_REVANCED := true
ASCP_OFFICIAL := true
PERF_ANIM_OVERRIDE := true
```

### Configuration Options

#### Maintainer Info
* `ASCP_MAINTAINER` — Name of the device maintainer to be displayed in system info. [Default: None]

#### Package Inclusion
* `WITH_REVANCED` — Pre-build and bundle ReVanced applications. [Default: false]

#### Build & Performance
* `ASCP_OFFICIAL` — Mark the build as official. [Default: false]
* `PERF_ANIM_OVERRIDE` — Enable custom animation scales and overrides for smoother performance. [Default: false]


