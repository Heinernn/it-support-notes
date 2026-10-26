# Virtualization lab

Notes from building virtual machines for testing and learning. I use **VirtualBox** and **VMware** regularly.
My experience with **Proxmox** is still basic, so that section is short on purpose.

## Why use VMs

- Test an installation or a change without risking a real computer.
- Reproduce a user's problem on a clean system.
- Practise Linux and server administration safely.

## VirtualBox: a Linux VM in a few steps

1. Download an Ubuntu Server or Desktop ISO.
2. New > name the VM, pick the ISO, choose Linux / Ubuntu (64-bit).
3. Give it resources. For a test machine: 2 CPU cores, 4 GB of RAM, 25 GB disk.
4. Start it and follow the installer.
5. Install the **Guest Additions** (better screen, clipboard and shared folders).

Useful details:

- **NAT** gives the VM internet access but hides it from the local network.
- **Bridged adapter** puts the VM on the same network as the host, so it gets its own IP.
- **Snapshots** let you go back to a known good state. I take one before every risky change.

## VMware (Workstation / Player)

The idea is the same as VirtualBox:

- Create a VM from an ISO and choose the guest operating system.
- Install **VMware Tools** for drivers and integration.
- Network modes are equivalent: NAT, Bridged and Host-only.
- Clone a VM when you need several machines with the same base setup.

## Proxmox (basic notes)

- It is a platform to manage VMs and containers from a web interface (port 8006).
- Upload ISO images to the storage, create a VM from the web UI and start it from there.
- Backups and snapshots are available from the same interface.

I have used it only once, so I treat it as something I am still learning.

## Good practices I follow

- Name the VMs clearly (`ubuntu-test-01`, `win11-clean`).
- Keep a short text file per lab with what was installed and the IP used.
- Delete the VMs you no longer use to free disk space.
- Never use real customer data in a lab.
