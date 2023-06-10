# Cisco-CCNA-200-301-Command-List
A summary of Cisco Commands to prepare for the CCNA Exam.

### Changing switch hostname
`Switch(config)#hostname <hostname>`

### Configuring passwords
Create password for privileged EXEC mode in Clear text:
`Switch(config)#enable password <password>`

Create password for privileged EXEC mode with MD5 hash:
`Switch(config)#enable secret <password>`

### Securing console port
```
Switch(config)#line con 0
Switch(config-line)#password <password>
Switch(config-line)#login
```