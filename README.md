8812au
======

Linux driver for Realtek 802.11ac, used in many dual-band (5Ghz/2.4Ghz) WiFi USB adapters (dongles).

This source was [originally distributed by TP-LINK](http://www.tplink.com/be/support/download/?model=Archer+T4U&version=V1) on 2015/8/21 to be used with their [Archer T4U AC1200 V1](http://www.tplink.com/be/products/details/?model=Archer+T4U). I made some modifications to allow it to work for me.

I have not tested it on other 8812au devices, but it may work for you.

Note that this driver only uses USB 2.0. You will not get USB 3.0 speeds on Linux, even if you use a USB 3.0 port. As far as I can tell, nobody has implemented USB 3.0 support for 8812au on Linux. :(

Please don't open issues here with general problems. I did not write this driver and do not maintain it. I can only assist with the specific modifications that I made.


My Modifications
----------------

* Added support for Linux 3.18 and above (the issue was a change in the `rtw_cfg80211_rx_mgmt` API)
* Added support for [DKMS](http://linux.dell.com/dkms/)


Installing with DKMS
--------------------

This will make your life much easier, as it will automatically recompile and install the driver for any new kernel you add. Simply `cd` to the directory and run:

    sudo dkms install .

To uninstall the driver from all kernels:

    sudo dkms remove 8812au/150821 --all

(Note that I configured DKMS to use all your cores for compilation of the driver. This is a good practice that greatly speeds up installation. I hope to see it used more often!)


Other Implementations
---------------------

There are many versions of this driver out there, with many modifications. It is unfortunate that the effort is so dispersed! I've tried all of them, but unfortunately only the one distributed TP-LINK worked with no network drops or slowdowns. But these may work for you:

* [gnab](https://github.com/gnab/rtl8812au)
* [abperiasamy](https://github.com/abperiasamy/rtl8812AU\_8821AU\_linux)
* [ulli-kroll](https://github.com/ulli-kroll/rtl8821au)
* [scrivy](https://github.com/scrivy/rtl8812AU\_8821AU\_linux)
* [csssuf](https://github.com/csssuf/rtl8812au)
