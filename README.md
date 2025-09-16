# AZURE_SOC_SENTINEL
This project demonstrates how to build a fully functional home Security Operations Center (SOC) in the cloud using Microsoft Azure. The goal of this lab is to simulate a real-world enterprise security environment where logs are collected, analyzed, and visualized to detect and respond to attacks.

To start the project first I will navigate to the Microsoft Azure page and create a free AZURE account. After this is done we will create a resource group and this is done by searching resource groups and then selectuing create. For this lab I am using the free subscription and the resource group name is RG-SOC-LAB.

<img width="958" height="545" alt="image" src="https://github.com/user-attachments/assets/08a8ee3a-f100-4fbd-b06f-7a9a6bee77ca" />

This is the folder in the cloud that will contain the contents of the lab. Next we will create a virtual network that the virtual machine will connect to. When creating this network we want to make sure that resource group is set to the newly created one.

<img width="945" height="790" alt="image" src="https://github.com/user-attachments/assets/615cc6b7-ccd5-4eae-9d4c-b287098f3b98" />

Now the network is configured and deployed. After this is done we want to create a virtual machine. This is done by navigating to virtual machines and selectung create. I will be doing mine on Windows 10 and choose the network that we created when asked for network. After finishing the set up process the VM will be created. 

<img width="948" height="782" alt="image" src="https://github.com/user-attachments/assets/8f324805-8099-48cd-b4da-e38e215da253" />

<img width="938" height="721" alt="image" src="https://github.com/user-attachments/assets/dce6531b-ca78-4f0b-a3d2-64ad126fc070" />

Now we can check the resource folder and see that the virtual machine was created along with a firewall. 

<img width="958" height="696" alt="image" src="https://github.com/user-attachments/assets/fa1caba1-3a22-4d80-8626-617724aa1bb4" />

For the lab we will be opening the firewall to the internet and allowing for other to access it. To do this I will navigate to the firewall and check the inbound rules. Then I will remove RDP whcich means that only remote desktops can connect. Then we navigate to the settings and then inbound security rules and add one. It allows any traffic to be rerouted to the virtual machine. 

<img width="622" height="503" alt="image" src="https://github.com/user-attachments/assets/bddeaca9-db20-4379-98d1-6726a699182e" />
