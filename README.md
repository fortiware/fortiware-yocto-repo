# Quickstart projects for meta-fortiware

## Getting started

This repo is not intended to be cloned directly. Use the [Android repo](https://source.android.com/source/downloading.html) tool instead:

```sh
sudo apt install repo
repo init -u https://github.com/fortiware/fortiware-yocto-repo.git -m default.xml
repo sync -j8
```

You should specify a particular branch when initializing. Currently, thud (2.6), warrior (2.7), zeus (3.0), and dunfell (3.1) are supported; manifests for older branches are available but not actively maintained. For more information about supported branches, please refer to the [documentation portal](https://docs.ota.here.com/ota-client/latest/yocto-release-branches.html)

Install the build dependencies for [OpenEmbedded](https://www.yoctoproject.org/docs/2.6/ref-manual/ref-manual.html#required-packages-for-the-build-host) and [meta-updater](https://github.com/advancedtelematic/meta-updater/). See [the documentation portal](https://docs.ota.here.com/ota-client/dev/build-raspberry.html) for more information.

A convenience script is provided to set up your environment to produce OTA-enabled images for your target device:

```sh
source meta-updater/scripts/envsetup.sh`<machine>`  # for example, raspberrypi3 or qemux86-64
```

A list of supported boards can be found on the [documentation portal](https://docs.ota.here.com/ota-client/latest/supported-boards.html).

Then you can build an image. `core-image-minimal` is a good start:

```sh
bitbake core-image-minimal
```

For more documentation on using these repos and [HERE OTA Connect](https://connect.ota.here.com/), please see the [OTA Connect documentation portal](https://docs.ota.here.com/).

## License

This code is licensed under the [MIT license](COPYING.MIT), a copy of which can be found in this repository. All code is copyright HERE Europe B.V., 2017-2020.

We require that contributors accept the terms of Linux Foundation's [Developer Certificate of Origin](https://developercertificate.org/). Please see the [contribution instructions of aktualizr](https://github.com/advancedtelematic/aktualizr/blob/master/CONTRIBUTING.md) for more information.
