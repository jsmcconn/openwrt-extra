## Openwrt extra package feed

### Description

This is an OpenWrt package feed containing **thin-provisioning-tools**.  This
package provides utilities which are used by lvm2 when activating LVs that
use caching or thin provisioning.


#### Note
The package **thin-provisioning-tools** depends on **libaio**, which requires
a kernel built with asynchronous IO support.  You must select that option
under **Global build settings->Kernel build options** before **thin-provisioning-tools**
will appear.

### Usage
To use these packages, add the following line to your ```feeds.conf``` or
```feeds.conf.default``` in the OpenWrt buildroot:

```src-git extrajsm https://github.com/jsmcconn/openwrt-extra.git```

Then include and install all packages from your ```feeds.conf``` via:
```
./scripts/feeds clean
./scripts/feeds update -a
./scripts/feeds install -a
```
Afterwards run ```make menuconfig``` or ```make defconfig```.
After selecting **Global build settings->Kernel build options->Compile the
kernel with asynchronus IO support**, the package **thin-provisioning-tools**
should appear under **Utilities->Disk**.

