# RancherOS Base System

This repo contains the Linux kernel and system programs for RancherOS.  RancherOS is built from [buildroot](http://buildroot.uclibc.org/).


This is a fork of `os-base` to work on Raspberry Pi 2, and all other ARM boards.
Switch to the `raspberrypi` branch to build this.

## Building

You need a linux machine with docker installed.

Linux laptop or VM
```
git clone https://github.com/luxas/os-base
cd os-base
git checkout raspberrypi
sudo ./build.sh
scp dist/artifacts/os-base.tar.xz [your rpi here]
```

Your Raspberry Pi
```
git clone https://github.com/luxas/os-images
cd os-images
git checkout raspberrypi

# Copy your os-base.tar.xz to this folder

sudo ./build.sh
```

At the moment you have to enter many times, for the buildroot config.
The image is going to be cross-compiled for ARM.

--------------------------------

## Building

You need Docker 1.5+

    ./build.sh

## Using a custom version of os-base in RancherOS

```
# Clone repos
git clone https://github.com/rancherio/os.git
git clone https://github.com/rancherio/os-base.git

# Build os-base
cd os-base
./build.sh

# Copy custom
cp dist/artifacts/os-base.tar.xz ../os/assets

# Build RancherOS
cd ../os
sed -i -e 's/^\(download.*os-base.*\)/#\1/' scripts/download
./build.sh
```
## Contact
For bugs, questions, comments, corrections, suggestions, etc., open an issue in
 [rancher/os](//github.com/rancher/os/issues) with a title starting with `[os-base] `.

Or just [click here](//github.com/rancher/os/issues/new?title=%5Bos-base%5D%20) to create a new issue.


# License
Copyright (c) 2014-2015 [Rancher Labs, Inc.](http://rancher.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

