# 

# **Problem Statement**

# **Project: Azure Bastion Deployment to Remove Public RDP Access**

**Course Code:** 24CC3046 · **Project Number:** P014 · **Team:** T218 (4 students)

# **Background**

Remote administration of Azure Virtual Machines commonly uses Remote Desktop Protocol (RDP). When a Windows Virtual Machine is assigned a public IP address and RDP port 3389 is exposed to the Internet, the VM becomes directly reachable from external networks. This increases the publicly accessible management surface and creates additional security concerns.

Azure Bastion provides a secure alternative by acting as a gateway between the administrator and the Virtual Machine. It allows administrators to connect to a VM through the Azure Portal and a web browser without assigning a public IP address to the VM.

In this project, the Windows Virtual Machine is deployed inside a private Azure Virtual Network, while Azure Bastion provides browser-based RDP access. Network Security Groups are also used to control RDP traffic between the Bastion subnet and the VM subnet.

# **Bottlenecks**

The main security concern is direct public RDP exposure. If a VM has a public IP address with TCP port 3389 accessible from the Internet, the administrative service is externally reachable and increases the attack surface.

Network configuration is another important bottleneck. Incorrect subnet configuration, NSG rules, or Bastion settings can prevent administrators from securely accessing the VM. The architecture therefore needs proper separation between the VM subnet and the dedicated Azure Bastion subnet.

Another challenge is maintaining secure access while keeping administration convenient. The administrator should be able to access the Windows VM without requiring a public IP on the VM or exposing RDP directly to the Internet.

# **Cost**

Azure Bastion is an Azure service that incurs usage-based charges while deployed. The Windows Virtual Machine and other Azure resources used in the project may also incur usage charges depending on their configuration and running time.

The project uses **Azure for Students** for implementation and testing. Resources can be deleted after the demonstration to avoid unnecessary ongoing charges.

# **The Design Problem**

How do you design and implement an Azure remote-access architecture that allows administrators to securely access a Windows Virtual Machine without exposing the VM directly to the public Internet through RDP?

The project requires a concrete network and security design using **Azure Virtual Network, separate subnets, Azure Bastion, Network Security Groups, and a private VM configuration**. The implementation should demonstrate that the VM can be accessed through Azure Bastion while the VM itself remains without a public IP address.

The final design should reduce direct public RDP exposure, control required network traffic, provide secure browser-based administration, and demonstrate successful connectivity through Azure Bastion.

