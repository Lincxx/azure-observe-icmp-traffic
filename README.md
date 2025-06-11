# Azure: Observe ICMP Traffic
---

In this lab we are going to connect to the VMs we create in the previous labs. We are going to install Wireshark and watch the traffic
---

1. If using Mac, install Microsoft Remote Desktop
2. Use Remote Desktop to connect to your Windows 10 Virtual Machine
3. Within your Windows 10 Virtual Machine, Install Wireshark
4. Open Wireshark and start packet capture
5. Within Wireshark, filter for ICMP traffic only
6. Retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows 10 VM
   - Observe ping requests and replies within WireShark
7. From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark

---
