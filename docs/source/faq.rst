.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!



FAQ
================

**Q: How do I know if I have the Dual NVMe Raft or the General NVMe PIP?**  

The **Dual NVMe Raft** supports dual device installation, while the **General NVMe PIP** supports only a single device installation.


---------------------------------------------

**Q: Does the Dual NVMe Raft require driver installation?**  

No additional drivers are needed. Raspberry Pi OS and most mainstream Linux systems natively support PCIe NVMe devices.


---------------------------------------------

**Q: Does the General NVMe PIP support PCIe Gen3 or higher devices?**  

The General NVMe PIP is designed based on PCIe 2.0. Even if you install PCIe Gen3 or higher devices, they will operate at PCIe 2.0 speeds.


---------------------------------------------

**Q: For the Dual NVMe Raft, can I install only one NVMe SSD?**  

Yes. The Dual NVMe Raft can operate normally even with only one NVMe SSD installed; installing two devices is not required.


---------------------------------------------

**Q: Does the General NVMe PIP support hot swapping?**  

No. The PCIe interface does not support hot swapping. Please power off the Raspberry Pi before inserting or removing M.2 devices.


---------------------------------------------

**Q: Is the FPC cable length limited? Can I replace it with a longer one?**  

The included FPC cable length is optimized for signal integrity. It is not recommended to replace it with a longer or different cable, as this may cause unstable communication.


---------------------------------------------

**Q: Will connecting the Dual NVMe Raft reduce the performance of the Raspberry Pi?**  

Generally, no. However, please note that the Raspberry Pi 5 has limited PCIe lane resources, and the available bandwidth is shared among connected devices. Performance may be slightly affected during heavy simultaneous data transfers.


---------------------------------------------

**Q: PWR LED is off**

Troubleshooting steps:

1. Check if the PCIe cable is properly connected;
2. Verify the cable orientation and ensure it is fully inserted;
3. Try replacing the PCIe cable with another one.

---------------------------------------------

**Q: The system does not detect the SSD**

Follow these steps to diagnose:

1. Check if the activity LED (STA) blinks during Raspberry Pi startup;
2. Confirm PCIe is enabled by running ``dmesg | grep pcie`` in the terminal;
3. Use ``lspci`` to check for detected PCIe devices;
4. Use ``ls /dev/nvme*`` to see if the NVMe drive is recognized;
5. If the device is recognized but not mounted, check whether partitions and a file system have been created.

---------------------------------------------

**Q: Cannot boot from the NVMe SSD**

Make sure of the following:

1. STA activity LED blinks at startup;
2. EEPROM boot order is correctly configured to boot from PCIe;
3. The configuration includes ``dtparam=pciex1_no_l0s=on``;
4. The SSD has a bootable OS properly installed and is compatible with Raspberry Pi.

---------------------------------------------

**Q: What is FORCE ENABLE?**

The onboard 3.3V power supply is normally activated by a signal from the PCIe interface when the Raspberry Pi powers on. If the system does not provide this signal (due to OS or hardware limitations), you can short the J4 "FORCE EN" jumper to force the 3.3V power supply to turn on and ensure the NVMe SSD receives power.

