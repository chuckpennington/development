# Setup ubuntu desktop on Yogo 3 14
Fix wireless on suspend
```
sudo nano /etc/pm/config.d/config
```
Add line
```
SUSPEND_MODULES="ath10k_pci"
```
Reboot
