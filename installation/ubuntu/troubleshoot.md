# Troubleshoot


## Wifi is not available after installation

* Check if `iwlwifi` is already loaded

```bash
lsmod | grep iwlwifi
```

* Load `iwlwifi`, if it's not loaded

```bash
sudo modprobe iwlwifi
```

* Reboot
