8812au
======

Linux driver for Realtek 802.11ac, used in many dual-band Wifi USB dongles.

This source was [originally distributed by TP-LINK](http://www.tplink.com/be/support/download/?model=Archer+T4U&version=V1) on 2015/8/21 to be used with their [Archer T4U AC1200 V1](http://www.tplink.com/be/products/details/?model=Archer+T4U).

I have not tested it on other 8812au devices.

Modifications
-------------

* Added support for Linux 3.18 and above (the issue was a change in the `rtw_cfg80211_rx_mgmt` API)
* Added support for [DKMS](http://linux.dell.com/dkms/)

Installing with DKMS
--------------------

This will make your life much easier, as it will automatically recompile and install the driver for any new kernel you add. Simply `cd` to the directory and run:

    sudo dkms install .

To uninstall the driver from all kernels:

    sudo dkms remove 8812au/150821 --all

Other Implementations
---------------------

There are many versions of this driver out there, with many modifications. It is unfortunate that the effort is so dispersed! I've tried all of them, but unfortunately only the one distributed TP-LINK worked with no network drops or slowdowns. But these may work for you:

* [gnab](https://github.com/gnab/rtl8812au)
* [abperiasamy](https://github.com/abperiasamy/rtl8812AU\_8821AU\_linux)
* [ulli-kroll](https://github.com/ulli-kroll/rtl8821au)
* [scrivy](https://github.com/scrivy/rtl8812AU\_8821AU\_linux)
* [csssuf](https://github.com/csssuf/rtl8812au)
