# Virtualbox

## Disable "green-turtle" / Hyper-V - run in vtx mode
1. Make sure, following features are off `Control Panel -> Programs -> Turn Windows features onor off`:
   - Hyper-V
   - Windows Hypervisor Platform
   - Virtual Machine Platform
   - Windows Sandbox
   - Microsoft Defender Application Guard
2. Disable Hyper-V at boot level
   ```
   bcdedit /set hypervisorlaunchtype off
   ```
3. Turn off Core Isolation (Memory Integrity)
   `Windows Security -> Device Security -> Core isolation -> Memory integrity`
4. Check for WSL2
   `wsl --status`
   
   If it says version 2, either:
     1. Switch to WSL1
        ```
        wsl --set-default-version 1
        ```
     2. Uninstall it
5. Disable virtualization-based security (VBS)
   ```
   Run gpedit.msc:
   Go to:
   Computer Configuration -> Administrative Templates -> System -> Device Guard
   ```
6. Check whether hypervisor has been turned off
   ```
   # cmd:
   systeminfo

   # Look for "A hypervisor has been detected" -> should NOT appear
   ```

### Revert changes
Depending on changes done, reverse them.
For example: on 4790k, win11 pro default install: only Hyper-V at boot level must have been disabled.

- Set Hyper-V default at boot level
  ```
  bcdedit /set hypervisorlaunchtype auto
  ```
