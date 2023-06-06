# OpenCore-Lenovo-X13

* CPU : QuadCore Intel Core i7-10510U, 4800 MHz (48 x 100)
* GPU :	Intel(R) UHD Graphics (1 Go)
* Monitor :	LCD 1366x768
* Intel(R) Ethernet Connection (10) I219-V
* Intel(R) Wi-Fi 6 AX201 160MHz

Warning : It won't work if you have Samsung SSD!

## Fix sleep

You have to correctly map your USB ports and set Bluethooth Card and Integrated Camera as `Internal` port type.

To cancel all scheduled wake from MacOS Ventura and preserve your battery life : 

- Open Terminal
- First make sure the com.apple.AutoWake.plist file is empty by using the following command : `sudo pmset sched cancelall`
- Next we need to set the immutable flag to lock/protect the file using the chflags command : `sudo chflags schg /Library/Preferences/SystemConfiguration/com.apple.AutoWake.plist`
- Reboot the System

Source : https://www.tonymacx86.com/threads/solved-ventura-random-scheduled-pm-wake-from-sleep.323359/