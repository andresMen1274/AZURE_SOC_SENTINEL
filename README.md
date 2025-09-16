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

After doing this I select the windows key and then type in Remote Desktop Connection. Then I enter in the IP address of the virtual machine and login.

<img width="1551" height="933" alt="image" src="https://github.com/user-attachments/assets/05d1dd0f-ec82-4ffc-8863-3c405e32daf9" />

After this is done turn off the firewall rules. Then we will go into our local machine and ping the Virtual Machine to make sure that it is accessible.

<img width="1206" height="927" alt="image" src="https://github.com/user-attachments/assets/26ec4881-f235-4ac9-8864-190425eaee53" />

<img width="1311" height="747" alt="image" src="https://github.com/user-attachments/assets/523caeee-dccb-41bf-8bf5-3e8c1a81cf47" />

Now I will close the virtual machine and try to login incorrectly multiple times. Then I will correctly login to the machine and go to event viewer to check the failed login attempts. I then user Ctrl + F to 4625 to see failed in login attempts. 

<img width="782" height="823" alt="image" src="https://github.com/user-attachments/assets/d0518825-2375-41d4-bde2-f03d7546fe29" />

<img width="1307" height="550" alt="image" src="https://github.com/user-attachments/assets/7eaf5126-319d-49c8-88eb-fa7efa8eb06b" />

Next we want to create a log repository and forward all of the virtual machine logs. We go back to Azure and find Log Analytics Workspace and create a new one. Then we will create a Microsoft Sentinel to do this naviagte to Microsoft Sentinel and select the log repository that was just created. This links that log analytics workspace to the our SIEM(Microsoft Sentinel). After this is done we navigate to content hub and intsall Microsoft Security Events. 

<img width="1571" height="617" alt="image" src="https://github.com/user-attachments/assets/81dec633-c263-43ab-91a0-0468dc22a3b6" />

After it has been successfully installed we select manage. Then we select Window Secuirty Events via AMA and open it. After this is done we are going to create a new data collection rule. We will go through the regular configuration and select the virtual machine that we have created. 

<img width="940" height="762" alt="image" src="https://github.com/user-attachments/assets/f76820cf-2a54-4503-bc23-f6534088a64a" />

After it has been created we will open Log Analytics in Azure and select the one that we previously created and go into KQL mode. Then we will type in SecurityEvent and run. This will show the secuirty events table and display all of its contents.

<img width="1507" height="717" alt="image" src="https://github.com/user-attachments/assets/8fa96dc5-04cf-473b-b24e-924797a9820a" />

