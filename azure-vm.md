### Azure VM

Azure VM is an on demand, scalable and IAAS solution from azure. Fully configurable and provides cusomization facility to install any OS image and applications we need.
In IAAS model cloud provides platform for Compute, Networking and Storage for you.

All Azure VM contains atleast two disks.
1. Disk for OS
2. Temperory Disk for Data

Other components that VM may have after provisioning VM
1. Data (Managed) Disk
2. NIC (Network Interface) 
3. Subnet
4. Diagonostic Logs Storage
5. Public IP
6. Network Security Group
  
### Types
1. Windows
2. Linux

### Features
1. Scale set
2. Load balancer 

#### Azure virtual networks VNet
Virtual networks (VNets) are used in Azure to provide private connectivity between Azure Virtual Machines and other Azure services or resources. 
VMs and services that are part of the same virtual network can access one another.
By default, services outside the virtual network cannot connect to services within the virtual network.

#### VNet Peering
#### Public and private address in VNet
Azure reserves the first four addresses and the last address in each subnet for its use.

#### CIDR notation
#### VNet topology
#### DNS (DNS translates domain names to IP addresses so browsers can load Internet resources)
#### Hub and network spoke topology

#### Network Security group (NSG)
Filter Inbound and Outbound traffice, Can apply rules on traffice. Assign public IP to connect outside the network.

### Remote Desktop Connection Manager


### Resource Provisioning Steps
There are different options available to provision the resources. 
1. Azure CLI
2. PowerShell
3. REST API
4. Portal
These are the options that we can use to request Azure Resource manager(ARM) to create the resources. Azure Resource manager(ARM) takes care of resource provisioning.
We can also levereg another technique provided by ARM to build an ARM template for fast provisioning and deployment of resources. ARM template is a json file.

#### 1. Create VNet and Assign Subnet
In order to create VM you have to create VNet first so that we can assign sub net to our VM. If there is no VNet available in advance, Azure creates for you at time
of VM creation.
#### 2. Calculate VM pricing by Azure pricing calculator
#### 3. Select Ubuntu Server 18.04 LTS
#### 3.1 Select size of VM
#### 4. For Availability options, choose No infrastructure redundancy required.
#### 5. Select Password base authentication
#### 6. Using SSH connect the the VM
