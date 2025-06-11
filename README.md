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

**First we are going to lookup the VMs we create, by searching for them**

![step1](https://github.com/user-attachments/assets/dcd64425-8127-429a-9924-6829975a1d1b)

**Next, we are going to select our Windows VM. We need to get the private IP Address for it so we can connect to it via a remote desktop application**

![step2](https://github.com/user-attachments/assets/ff06921f-1898-4f2a-bf6c-eec332ad2049)

![step3](https://github.com/user-attachments/assets/e7979cb5-e7f9-4d45-882f-ee20ab66b7b8)

**I use Linux, so I'm going to use an application called Remmina. Windows has a built-in one, and for Apple you can download Windows App (formerly called remote desktop)**
**After you enter in the IP Adress and credentials to access your VM, it should look something like this**

![step4](https://github.com/user-attachments/assets/62719c9f-ddd3-41c4-8174-cc44b0fa60e3)

**Go ahead and open up the Edge browser and download Wireshark. Once it's downloaded, go ahead and proceed and install it**
**After you install, go ahead and open Wireshark and then select the enternet and click on the blue fin.**






