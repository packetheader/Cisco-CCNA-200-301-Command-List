# Cisco-CCNA-200-301-Command-List
A summary of Cisco Commands to prepare for the CCNA Exam.

## Changing switch hostname
`Switch(config)#hostname <hostname>`

## Configuring passwords
Create password for privileged EXEC mode in Clear text:

`Switch(config)#enable password <password>`

Create password for privileged EXEC mode with MD5 hash:

`Switch(config)#enable secret <password>`

## Securing console port
```
Switch(config)#line con 0
Switch(config-line)#password <password>
Switch(config-line)#login
```

## Securing terminal lines
```
Switch(config)#line vty 0 4
Switch(config-line)#password <password>
Switch(config-line)#login
```

## Encrypting passwords (new and already created passwords)
``Switch(config)#service password-encryption?``

## Configuring banner
```
Switch(config)#banner motd %

!!! UNAUTHORIZED ACCESS IS PROHIBITED !!!

%
```

## Set IP addresses
```
Switch(config)#interface <interface/Vlan> <interface-/vlanid>
Switch(config-if)#ip address <ip-address> <subnet> (or dhcp)
```

## Setting the default gateway
``Switch(config)#ip default-gateway <ip-address>``

## Save configuration
```
Switch#copy running-config startup-config
  - or -
Switch#write memory
  - or -
Switch#write
```

## Configuring switch to use SSH
1. Configure DNS domain name

``Switch(config)#ip domain-name <domain-name>``

2. Configure username and password

``Switch(config)#username <name> password <password>``

3. Generate encryption keys

``Switch(config)#crypto key generate rsa``

4. Define SSH version to use

``Switch(config)#ip ssh version 2``

5. Enable vty lines to use SSH

```
Switch(config)#line vty 0 4
Switch(config-line)#login local
Switch(config-line)#transport input ssh
```

## Verify Basic Configuration
| Command | Description |
| --- | --- |
| `Switch#show version` | Shows information about the switch and its interfaces, RAM, NVRAM, flash, IOS, etc. |
| `Switch#show running-config` | Shows the current configuration file stored in DRAM |
| `Switch#show startup-config` | Shows the configuration file stored in NVRAM which is used at first boot process |
| `Switch#show history` | Lists the commands currently held in the history buffer |
| `Switch#show ip interface brief` | Shows an overview of all interfaces, their physical status (Layer 1), protocol status (Layer 2) and ip address if assigned |
| `Switch#show interface <interface>` | Shows detailed information about the specified interface, its status, protocol, duplex, speed, encapsulation, last 5 min traffic |
| `Switch#show interfaces description` | Shows the description of all interfaces |
| `Switch#show interfaces status` | Shows the status of all interfaces like connected or not, speed, duplex, trunk or access vlan
| `Switch#show dhcp lease` | Shows information about the leased IP address |
