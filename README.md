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
**After you install, go ahead and open Wireshark and then select the ethernet and click on the blue fin.**

![step6](https://github.com/user-attachments/assets/17227151-2700-4f5e-9faf-b7eaec748289)

**In the search bar of the Wireshark go ahead and enter in ICMP and press enter. The ping command uses the ICMP**

![step7](https://github.com/user-attachments/assets/764e09b3-b427-443b-80fd-36c2b14c6693)

**From, here we need to go back to Azure and get the private IP Address for the Linux. Just preform the steps we did to get the Windows VM IP Address**

![step8](https://github.com/user-attachments/assets/c7e73f0a-4f40-4747-93f5-677a2baaacb5)

**Now that we have it, open up a command window in the Windows VM and type in the following 'ping 10.0.0.x -t' where x is the correct number and do not include the single quote**
**As you can see we are capturing the ICMP traffic**
![step10](https://github.com/user-attachments/assets/ae109dfa-573f-4213-b7b0-b83d143f2b59)


**Let's know take a closer look at the packets and see if we recognize anything**
**We do, we see some data layer information - MAC Addresses.**

![step11](https://github.com/user-attachments/assets/4983a551-85b1-44b5-b603-6506a1d47361)

**Ok, now we are going to block any requests from happening that use the ping command (ICMP)**
**Go back to Azure and to the Linux VM. We are going to start a rule in the firewall**

![step12](https://github.com/user-attachments/assets/a759a353-0ba3-49cf-9998-41505cf2955f)

**Click on Network settings, then click Network security group**

<img width="948" alt="Screenshot 2025-06-11 at 2 53 31 PM" src="https://github.com/user-attachments/assets/f7c00b4d-6ff6-4c86-b0d6-a10cb80e5e16" />

**Click on settings on the left-hand side, from there on the inbound security rule. Finally, click on the add**

![step14](https://github.com/user-attachments/assets/ccc50c52-ffdf-4702-af7a-a4d633d55866)

**We are going to change the destination port to a wildcard '*', for the protocol select the ICMPv4, that's what ping uses**
**For the action, select the deny, and the priority will be set to 290. This will make it top of the list**

![step15](https://github.com/user-attachments/assets/3886ed57-9141-4bb9-89ff-9cbecfe9516a)

**Go back to the Windows VM and you'll see that the ping is now timing out**

![step16](https://github.com/user-attachments/assets/04a31d74-bd7e-4030-bb8d-0ed11d037bd9)

**Now go to Azure and delete the rule we created and finally go back to the Windows VM and you'll see the traffic flowing again**

![step17](https://github.com/user-attachments/assets/dbf2cdc0-c9c7-455b-887c-aedacaa38a59)

**Final step delete all resource groups that way we don't lose a lot of money ;)**

