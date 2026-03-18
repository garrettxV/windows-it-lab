# 🖥️ Windows VM Installation (VirtualBox)

## Objective
Set up a Windows virtual machine to simulate real-world IT support scenarios.

---

## Configuration
- **OS:** Windows 10  
- **RAM:** 6 GB  
- **CPU:** 2 cores  
- **Storage:** 80 GB (VDI)

---

## Initial VM Configuration
The virtual machine was created with a virtual hard disk attached to the SATA controller.

![Initial Configuration](screenshots/01-initial-state-no-iso.png)

---

## Issue
The virtual machine initially failed to boot into the Windows installation environment.

### Observed Behavior
- System did not enter Windows setup  
- Error message displayed:

> "No bootable option or device was found."

![Boot Error](screenshots/03-boot-error.png)

---

## Troubleshooting Process
1. Verified that the Windows ISO file was properly attached to the virtual machine  
2. Reviewed storage controller configuration  
3. Confirmed boot order prioritization (optical drive first)  
4. Observed system behavior during startup  

### ISO Verification
The ISO was confirmed to be attached to the SATA controller.

![ISO Attached](screenshots/02-iso-attached.png)

---

## Root Cause
The system displayed a boot prompt during startup:

> "Press any key to boot from CD or DVD..."

No input was provided within the required time window, causing the VM to skip the ISO and attempt to boot from the virtual hard disk instead.

---

## Resolution
- Restarted the virtual machine  
- Pressed a key immediately when prompted during boot  

---

## Result
The virtual machine successfully booted into the Windows installation environment.

![Windows Installation Screen](screenshots/05-windows-start.png)

---

## ⚠️ Common Pitfall: Missed Boot Prompt
This behavior can appear to be a configuration or hardware issue but is actually expected system behavior.

If no key is pressed during the boot prompt:
- The system defaults to the next boot device  
- This can result in a misleading “no bootable device” error  

---

## Key Takeaway
Not all boot failures are caused by misconfiguration. Carefully observing system prompts and verifying system behavior is critical for accurate troubleshooting.

---

## Skills Demonstrated
- Virtual machine setup (VirtualBox)  
- OS installation process  
- Boot sequence troubleshooting  
- Root cause analysis (user interaction vs system issue)  
- Technical documentation and structured problem-solving  
