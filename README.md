# ENABLING SYSTEMCTL ON WSL2 UBUNTU

## Step 1: Start Docker Service
By default, `systemd` (which `systemctl` relies on) is not enabled in WSL2 Ubuntu. We need to enable `systemd` in WSL2.

### a. Edit the WSL Configuration File
Open the `wsl.conf` file using a text editor:
```sh
sudo vi /etc/wsl.conf
```

Add the following lines inside the `wsl.conf` file:
```ini
[boot]
systemd=true
```

### b. Close WSL and Restart it
Run the following command in PowerShell or Command Prompt to restart WSL:
```sh
wsl --shutdown
```

### c. Verify `systemd` is Running
Once WSL restarts, verify that `systemd` is enabled by running:
```sh
systemctl status
```

### Expected Outcome:
If `systemd` is properly enabled, you should see an output similar to this:
```sh
● systemd 245 (245.4-4ubuntu3.19) running in system mode.
  - Detected virtualization wsl.
  - Detected architecture x86-64.

Active: active (running) since Mon 2024-03-10 12:34:56 UTC; 10s ago
```


