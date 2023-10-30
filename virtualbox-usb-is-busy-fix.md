---
tags:
  - virtualbox
  - issue
  - usb
---
 1) In VirtualBox, Add new filters with the Product ID , and Vendor ID, put Any
2) Close VirtualBox
3) Go to your installation Directory: `C:\Program Files (x86)\Oracle\VirtualBox\drivers\USB`
4) Go to both Folder (device and filter), and in both folder : Right-click on the file `extension *.inf` ( `VBoxUSBMon.inf` and `VBoxUSB.inf`) and click install
5) Start VirtualBox then your VirtualMachine