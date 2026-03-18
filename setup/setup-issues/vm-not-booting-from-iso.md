# 🖥️ Windows VM Installation (VirtualBox)

## Objective
Set up a Windows virtual machine to simulate real-world IT support and troubleshooting scenarios.

---

## Configuration
- **OS:** Windows 10  
- **RAM:** 6 GB  
- **CPU:** 2 cores  
- **Storage:** 80 GB (VDI)

---

## Initial VM Configuration
![VM Settings](screenshots/01-vm-settings.png)

---

## Issue
The virtual machine failed to boot after attaching the Windows ISO.

### Boot Error
![Boot Error](screenshots/03-boot-error.png)

---

## Troubleshooting Steps
1. Verified the Windows ISO was properly attached  
2. Checked VM boot order settings  
3. Reviewed storage controller configuration in VirtualBox  

---

## Root Cause
The Windows ISO was attached to the **SATA controller**, which prevented the VM from recognizing it as a bootable device.

### Incorrect Configuration
![Incorrect Controller](screenshots/02-iso-attached.png)

---

## Resolution
- Powered off the virtual machine  
- Reattached the ISO to the **PIIX4 (IDE) controller**  
- Restarted the virtual machine  
- Confirmed correct boot sequence  

### Fixed Configuration
![Controller Fix](screenshots/04-controller-fixed.png)

---

## Result
The virtual machine successfully booted into the Windows installation environment.

### Successful Boot
![Windows Install](screenshots/05-windows-start.png)

---

## Key Takeaway
Proper storage controller configuration is essential for booting installation media.  
Attaching an ISO to the wrong controller can prevent the system from detecting a bootable device.
