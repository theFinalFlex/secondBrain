Create Simulated Azure SOC Lab
![image](https://github.com/user-attachments/assets/9c80c5d9-1f2d-4b3a-82ee-d31782560990)

Configuration
- Full Terraform Deployment
- azure components include Vnet, Subnet, Azure sentinel for SIEM, Azure Defender for EDR, NSG with Security Rules, Azure Log Analytics for workspace, Azure Logic apps for playbook automation

Flow 
Brute Force logins from same IP targetted towards windows and ubuntu machine

steps to deploy lab
- design flow using draw.io
- install and create terraform file to deploy components to azure  
  ![image](https://github.com/user-attachments/assets/185ae3b9-bb68-4281-a2a3-46ddfab92a32)  
- create ssh key on local host  
- "terraform init/terraform plan/terraform apply"  
- ![image](https://github.com/user-attachments/assets/54f1e4b8-acd7-4119-b123-035f98ae3157)
- check azure portal for resources that exist  
![image](https://github.com/user-attachments/assets/4b0ef310-bdbd-4d72-9174-2be1967fbefd)  




### main.tf
```
provider "azurerm" {
  features {}
}

# Resource Group
resource "azurerm_resource_group" "soc_lab_rg" {
  name     = "SOC-Lab-Resources"
  location = "East US"
}

# Virtual Network
resource "azurerm_virtual_network" "soc_lab_vnet" {
  name                = "SOC-Lab-VNet"
  location            = azurerm_resource_group.soc_lab_rg.location
  resource_group_name = azurerm_resource_group.soc_lab_rg.name
  address_space       = ["10.0.0.0/16"]
}

# Subnet for Internal Resources
resource "azurerm_subnet" "soc_lab_subnet" {
  name                 = "SOC-Lab-Subnet"
  resource_group_name  = azurerm_resource_group.soc_lab_rg.name
  virtual_network_name = azurerm_virtual_network.soc_lab_vnet.name
  address_prefixes     = ["10.0.1.0/24"]
}

# Subnet for External Attacker VM
resource "azurerm_subnet" "attacker_subnet" {
  name                 = "Attacker-Subnet"
  resource_group_name  = azurerm_resource_group.soc_lab_rg.name
  virtual_network_name = azurerm_virtual_network.soc_lab_vnet.name
  address_prefixes     = ["10.0.2.0/24"]
}

# Network Security Group
resource "azurerm_network_security_group" "soc_lab_nsg" {
  name                = "SOC-Lab-NSG"
  location            = azurerm_resource_group.soc_lab_rg.location
  resource_group_name = azurerm_resource_group.soc_lab_rg.name
}

# NSG Rules - Allow RDP and SSH
resource "azurerm_network_security_rule" "allow_rdp" {
  name                        = "Allow-RDP"
  priority                    = 100
  direction                   = "Inbound"
  access                      = "Allow"
  protocol                    = "Tcp"
  source_port_range           = "*"
  destination_port_range      = "3389"
  source_address_prefix       = "*"
  destination_address_prefix  = "*"
  network_security_group_name = azurerm_network_security_group.soc_lab_nsg.name
  resource_group_name         = azurerm_resource_group.soc_lab_rg.name
}

resource "azurerm_network_security_rule" "allow_ssh" {
  name                        = "Allow-SSH"
  priority                    = 110
  direction                   = "Inbound"
  access                      = "Allow"
  protocol                    = "Tcp"
  source_port_range           = "*"
  destination_port_range      = "22"
  source_address_prefix       = "*"
  destination_address_prefix  = "*"
  network_security_group_name = azurerm_network_security_group.soc_lab_nsg.name
  resource_group_name         = azurerm_resource_group.soc_lab_rg.name
}

# Associate NSG with Internal Subnet
resource "azurerm_subnet_network_security_group_association" "soc_lab_subnet_nsg" {
  subnet_id                 = azurerm_subnet.soc_lab_subnet.id
  network_security_group_id = azurerm_network_security_group.soc_lab_nsg.id
}

# Network Interface for Windows VM
resource "azurerm_network_interface" "soc_vm_win_nic" {
  name                = "SOC-VM-Win-NIC"
  location            = azurerm_resource_group.soc_lab_rg.location
  resource_group_name = azurerm_resource_group.soc_lab_rg.name

  ip_configuration {
    name                          = "internal"
    subnet_id                     = azurerm_subnet.soc_lab_subnet.id
    private_ip_address_allocation = "Dynamic"
  }
}

# Network Interface for Linux VM
resource "azurerm_network_interface" "soc_vm_linux_nic" {
  name                = "SOC-VM-Linux-NIC"
  location            = azurerm_resource_group.soc_lab_rg.location
  resource_group_name = azurerm_resource_group.soc_lab_rg.name

  ip_configuration {
    name                          = "internal"
    subnet_id                     = azurerm_subnet.soc_lab_subnet.id
    private_ip_address_allocation = "Dynamic"
  }
}

# Windows Virtual Machine
resource "azurerm_windows_virtual_machine" "soc_vm_win" {
  name                = "SOC-VM-Win"
  resource_group_name = azurerm_resource_group.soc_lab_rg.name
  location            = azurerm_resource_group.soc_lab_rg.location
  size                = "Standard_D2s_v3"
  admin_username      = "adminuser"
  admin_password      = "Password1234!"

  network_interface_ids = [
    azurerm_network_interface.soc_vm_win_nic.id,
  ]

  os_disk {
    name                = "soc-vm-win-osdisk"
    caching             = "ReadWrite"
    storage_account_type = "Standard_LRS"
  }

  source_image_reference {
    publisher = "MicrosoftWindowsServer"
    offer     = "WindowsServer"
    sku       = "2019-Datacenter"
    version   = "latest"
  }
}

# Linux Virtual Machine
resource "azurerm_linux_virtual_machine" "soc_vm_linux" {
  name                = "SOC-VM-Linux"
  resource_group_name = azurerm_resource_group.soc_lab_rg.name
  location            = azurerm_resource_group.soc_lab_rg.location
  size                = "Standard_D2s_v3"
  admin_username      = "adminuser"
  admin_ssh_key {
    username   = "adminuser"
    public_key = file("C:\\Users\\avenkatraman\\andyssh.pub")
  }

  network_interface_ids = [
    azurerm_network_interface.soc_vm_linux_nic.id,
  ]

  os_disk {
    name                = "soc-vm-linux-osdisk"
    caching             = "ReadWrite"
    storage_account_type = "Standard_LRS"
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "UbuntuServer"
    sku       = "20.04-LTS"
    version   = "latest"
  }
}

# Attacker VM Network Interface
resource "azurerm_network_interface" "attacker_vm_nic" {
  name                = "Attacker-VM-NIC"
  location            = azurerm_resource_group.soc_lab_rg.location
  resource_group_name = azurerm_resource_group.soc_lab_rg.name

  ip_configuration {
    name                          = "internal"
    subnet_id                     = azurerm_subnet.attacker_subnet.id
    private_ip_address_allocation = "Dynamic"
  }
}

# Attacker VM
resource "azurerm_linux_virtual_machine" "attacker_vm" {
  name                = "Attacker-VM"
  resource_group_name = azurerm_resource_group.soc_lab_rg.name
  location            = azurerm_resource_group.soc_lab_rg.location
  size                = "Standard_D2s_v3"
  admin_username      = "attacker"
  admin_ssh_key {
    username   = "attacker"
    public_key = file("C:\\Users\\avenkatraman\\andyssh.pub")
  }

  network_interface_ids = [
    azurerm_network_interface.attacker_vm_nic.id,
  ]

  os_disk {
    name                = "attacker-vm-osdisk"
    caching             = "ReadWrite"
    storage_account_type = "Standard_LRS"
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "UbuntuServer"
    sku       = "20.04-LTS"
    version   = "latest"
  }
}

# Log Analytics Workspace
resource "azurerm_log_analytics_workspace" "soc_lab_law" {
  name                = "SOC-Lab-Workspace"
  location            = azurerm_resource_group.soc_lab_rg.location
  resource_group_name = azurerm_resource_group.soc_lab_rg.name
  sku                 = "PerGB2018"
}

# Azure Sentinel
resource "azurerm_sentinel_alert_rule_scheduled" "example_rule" {
  name                     = "Example-Scheduled-Rule"
  log_analytics_workspace_id = azurerm_log_analytics_workspace.soc_lab_law.id

  display_name             = "Example Scheduled Rule"
  severity                 = "High"
  query                    = "SigninLogs | where ResultType == '50074'"
  query_frequency          = "PT5M"
  query_period             = "PT1H"
  trigger_operator         = "GreaterThan"
  trigger_threshold        = 0
  suppression_duration     = "PT1H"
  suppression_enabled      = false
}

# Azure Defender for VMs
resource "azurerm_security_center_subscription_pricing" "vm_defender" {
  tier            = "Standard"
  resource_type   = "VirtualMachines"
}

```
