🖥️ Windows VM Installation (VirtualBox)
Objective

Set up a Windows virtual machine for IT support lab simulations.

Configuration

OS: Windows 10

RAM: 6 GB

CPU: 2 cores

Storage: 80 GB (VDI)

Issue Encountered

VM failed to boot after attaching ISO.

Troubleshooting Steps

Verified ISO was attached

Checked boot order

Inspected storage controller configuration

Root Cause

ISO was attached under incorrect controller (SATA misconfiguration).

Resolution

Moved ISO to correct controller

Restarted VM

Boot successful

Result

Windows installation successfully started.
