# QEMU-Ubuntu-PowerShell-scripts---Server-install-and-run
### This provides 2 universal PowerShell scripts (.PS1) that make running Ubuntu (e.g Server) easy on Windows host with QEMU much easier.
___
### Works on Intel and AMD machines.

___
## General steps:
1. Download these 2 text files
2. Download Ubuntu `.iso` (Ubuntu or Ubuntu Server, doesn't matter)
3. Put it in the folder you want to (I placed this on my Desktop along with these 2 scripts - so my path was `C:\Users\<your-user-name>\Desktop\QEMU_Ubuntu\`, you can adjust it for yourself)
4. Adjust the `$Base` / `$QEMU` paths in both of `.ps1` scripts
5. Run powershell and paste: `powershell.exe -ExecutionPolicy Bypass -File "C:\Users\<your-user-name>\Desktop\QEMU_Ubuntu\ubuntu-server-first-run.ps1"`
6. (Optional:) Configure `sharehost` functionality directly in your Linux distro
___


## Scripts 📂 
### 1. ubuntu-server-first-run.ps1 -> One-time setup:
- Creates a qcow2 virtual disk (40 GB default)
- Boots the Ubuntu ISO using TCG (stable software emulation)
- Use this only for the installation step

### 2. ubuntu-server-run.ps1 -> Run your VM after installation:
- Prefers WHPX (hardware acceleration) and falls back to TCG
- Supports optional `share/` host folder (virtio-9p)
- Logs are saved in the `logs/` folder

## Requirements 🛠 
- Windows host
- QEMU for Windows installed
- Ubuntu ISO (Desktop or Server, recommended: Ubuntu Server ISO)
- PowerShell 5+ (Windows PowerShell or PowerShell Core)
