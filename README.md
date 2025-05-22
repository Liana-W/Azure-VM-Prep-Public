# Configuring and Implementing a Honeypot in Azure

![image](https://github.com/user-attachments/assets/4734bbb3-aba1-42f6-9a46-7a3cd511d671)

<h4>Let's start setting up our Azure Honeynet project. First, we must create virtual machines (VMs) in Microsoft Azure. These cloud-based computers will form the core of our honeynet. Here's how we'll get started:</h4>

 <h3>1. Sign in to the Azure portal: The first step is to log in to your Azure account. If you don't have an account yet, you'll need to create one!</h3>
 <h3>2. Create a virtual machine:</h3>
   
   - Once you're in the Azure portal, navigate to the 'Virtual machines' section.

![image](https://github.com/user-attachments/assets/73f40a47-1acc-46ab-a68c-60d094f24efa)

   - Click on 'Create,' then 'Virtual machine.' This is where we'll set up our new VM!

![image](https://github.com/user-attachments/assets/a19fd447-f1c5-44b5-9467-cca3da0653f6)
    
 <h3>3. Configure the VM settings:</h3>

  - Subscription and resource group: Select your Azure subscription and resource group. For this project, use the existing resource group RG-Cyber-Lab2

  - Virtual Machine Name: Name your VM Lab-HoneyNet

  - Region: Choose the region, (US) East US 2

  - Availability Options: Select No infrastructure redundancy required since this VM will act as a honeypot.

  - Image: Select Windows 10 Pro, version 21H2 - x64 Gen2
    
![image](https://github.com/user-attachments/assets/c811ff9b-766b-4ec1-84bf-1fc9aae0e57e)

  - Networking: Use the default settings for the virtual network. For this lab, name it Lab-VNet.
    
![image](https://github.com/user-attachments/assets/e0637bee-b570-440f-99e4-519387b42373)


  <h3>4. NSG/Inbound Security Rule Configuration:</h3>

  - Navigate to the Network Security Group (NSG): In the Azure portal, search for 'Network Security Groups' in the search bar and select the NSG associated with your virtual machine.
  - Create an inbound security rule: Inside the NSG, you'll find a section for 'Inbound security rules'. This is where we control what kind of traffic is allowed to reach our VM. Click on 'Add' to create a new rule.
  - Configure the rule: We will be prompted to input details about the new rule. Configure the following settings:
  - Source: Set to Any to allow traffic from any location.
  - Source port ranges: Set to * or Any to allow all ports.
  - Destination: Set to Anyto direct traffic to your VM.
  - Destination port ranges: Set to * or Any to open all ports.
  - Priority: Set the priority to 300 for this lab. Note that lower-priority numbers are processed before higher-priority numbers.
  - Action: Set to Allow to permit traffic matching this rule.

![image](https://github.com/user-attachments/assets/83eef4f0-d081-4ca5-80e3-a8575b9eb5cc)

  - Review & Create: - After configuring the rule details, click 'Add' to create the new inbound security rule.

# Conclusion

<h4>By creating our Virtual Machines (VMs) and opening inbound security rules, we intentionally make our system vulnerable to attacks. This is not recommended for production environments, as it poses significant security risks.</h4>
<h4>However, in the context of our honeynet project, this setup serves a specific purpose. We're creating a decoy environment that attracts potential attackers by leaving our VM exposed.</h4>
<h4>This allows us to monitor and analyse their actions in a controlled environment.</h4>
