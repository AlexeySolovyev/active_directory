# Active Direcotry setup


# 00 - Install VMs

1. Installed Windows Server 2022 as a Virtual machine in ESXi
2. Installed Windows 11 as a Virtual machine Workstation in ESXi


# 01 - Installing the Domain controller

on the target: 
Enable-PSRemoting
ipconfig

1. Use sconfig to:
 - Change the hostname
 - Change the IP address to static
 - Change the DNS server to our own IP address


2. 
on the control machine:
Service-Start WinRM
set-item wsman:\localhost\Client\TrustedHosts -value <target ip>
New-PSSession -ComputerName <target ip> -Credential (Get-Credential)
remember id
Enter-PSSession <id>


sconfig
Set static IP
Set DNS Server as your set static IP
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
