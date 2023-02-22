## Notes on setting thing sup for the live demo
Start with standard 32-bit OS (tested with Raspbian GNU/Linux 11 (bullseye)).

Enable SSH and add Wi-Fi credentials using the Raspeberry Pi Imager settings. You can also set a custom hostname and skip that step later (e.g., `elpi` to connect via `elpi.local`).

Update everything:
```bash
sudo apt update
sudo apt full-upgrade
```
Install xrdp (remote desktop)

```bash
sudo apt install xrdp
```

## Setup the Pi Zero 2 W as an Ethernet Gadget

Based on https://www.circuitbasics.com/raspberry-pi-zero-ethernet-gadget/.

Edit config.txt to add `dtoverlay=dwc2` to the end using 

```bash
sudo nano /boot/config.txt
```

then save and exit (Ctrl-S, Ctrl-X).

Edit cmdline.txt to add `modules-load=dwc2,g_ether` after `rootwait` using 

```bash
sudo nano /boot/cmdline.txt
```

then save and exit (Ctrl-S, Ctrl-X).

Set hostname to `elpi` to allow connections to `elpi.local`. 

```bash
sudo raspi-config
```

then select "System Options" > "Hostname".

## Windows RNDIS Driver
**[Follow this section at your own risk! I can't vouch for the safety, license status, etc., of this driver!]** 

Install RNDIS Gadget driver on the Windows host computer following these instructions: https://wiki.moddevices.com/wiki/Troubleshooting_Windows_Connection. The Pi showed up for me as Device Manager under Ports (COM & LPT) > USB Serial Device (COM3) (disconnect and reconnect with `sudo reboot` while watching Device Manager to confirm).

## Glamor
**[Not required for Pi Zero 2 W, it appears]** On Raspberry Pi 3 and earlier running _Bullseye_ , re-enable *Glamor* to get preview windows to work. Enter `sudo raspi-config`, choose `Advanced Options`, `Glamor` and `Yes`. Quit and reboot.

## Run the demo
Connect with remote desktop to elpi.local, open terminal, run:

```bash
libcamera-hello -t 0 --awbgains 1,1 --framerate 5 --gain 4
```

Optional: add `-f` to make the preview full screen. Exit with Alt-PgUp.
