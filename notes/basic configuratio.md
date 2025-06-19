.                                       IOS NAVIGATION
User EXEC Mode - This mode has limited capabilities but is useful for basic operations. It allows only a limited number of basic monitoring commands but does not allow the execution of any commands that might change the configuration of the device. The user EXEC mode is identified by the CLI prompt that ends with the > symbol.
Privileged EXEC Mode - To execute configuration commands, a network administrator must access privileged EXEC mode. Higher configuration modes, like global configuration mode, can only be reached from privileged EXEC mode. The privileged EXEC mode can be identified by the prompt ending with the # symbol.


Line Configuration Mode - Used to configure console, SSH, Telnet, or AUX access.
Interface Configuration Mode - Used to configure a switch port or router network interface.

note : To move from user EXEC mode to privileged EXEC mode, use the enable command. Use the disable privileged EXEC mode command to return to user EXEC mode.
    : Use the exit command to exit a subconfiguration mode and return to global configuration mode.

THESE ARE THE VARIOUS NAVIGATIONS ON  COMMAND LINE COMMANDS
Enter privileged EXEC mode using the enable command.

Switch>enable
Return to user EXEC mode using the disable command.

Switch#disable
Re-enter privileged EXEC mode.

Switch>enable
Enter global configuration mode using the configure terminal command.

Switch#configure terminal
Exit global configuration mode and return to privileged EXEC mode using the exit command.

Switch(config)#exit
Re-enter global configuration mode.

Switch#configure terminal
Enter line subconfiguration mode for the console port using the line console 0 command.

Switch(config)#line console 0
Return to global configuration mode using the exit command.

Switch(config-line)#exit
Enter VTY line subconfiguration mode using the line vty 0 15 command.

Switch(config)#line vty 0 15
Return to global configuration mode.

Switch(config-line)#exit
Enter the VLAN 1 interface subconfiguration mode using the interface vlan 1 command.

Switch(config)#interface vlan 1
From interface configuration mode, switch to line console subconfiguration mode using the line console 0 global configuration command.

Switch(config-if)#line console 0
Return to privileged EXEC mode using the end command.

Switch(config-line)#end
.                              SAVING CONFIGURATIONS
There are two system files that store the device configuration:

startup-config - This is the saved configuration file that is stored in NVRAM. It contains all the commands that will be used by the device upon startup or reboot. Flash does not lose its contents when the device is powered off.
running-config - This is stored in Random Access Memory (RAM). It reflects the current configuration. Modifying a running configuration affects the operation of a Cisco device immediately. RAM is volatile memory. It loses all of its content when the device is powered off or restarted.
The show running-config privileged EXEC mode command is used to view the running config. As shown in the example, the command will list the complete configuration currently stored in RAM.


.                              IP ADDRESSING
The structure of an IPv4 address is called dotted decimal notation and is represented by four decimal numbers between 0 and 255.

With the IPv4 address, a subnet mask is also necessary. An IPv4 subnet mask is a 32-bit value that differentiates the network portion of the address from the host portion. Coupled with the IPv4 address, the subnet mask determines to which subnet the device is a member.


.                                 CONFIGURING IP ADDRESS
To manually configure an IPv4 address on a Windows host, open the Control Panel > Network Sharing Center > Change adapter settings and choose the adapter. Next right-click and select Properties to display the Local Area Connection Properties, as shown in the figure.
The DNS server addresses are the IPv4 and IPv6 addresses of the Domain Name System (DNS) servers, which are used to translate IP addresses to domain names.
In a network, DHCP enables automatic IPv4 address configuration for every end device that is DHCP-enabled. 
To configure an SVI on a switch, use the interface vlan 1 global configuration command. Vlan 1 is not an actual physical interface but a virtual one.

Next assign an IPv4 address using the ip address ip-address subnet-mask interface configuration command. Finally, enable the virtual interface using the no shutdown interface configuration command.

Note: Similar to a Windows hosts, switches configured with an IPv4 address will typically also need to have a default gateway assigned. This can be done using the ip default-gateway ip-address global configuration command. The ip-address parameter would be the IPv4 address of the local router on the network, as shown in the example. However, in this module you will only be configuring a network with switches and hosts. Routers will be introduced later.

example 

Sw-Floor-1# configure terminal
Sw-Floor-1(config)# interface vlan 1
Sw-Floor-1(config-if)# ip address 192.168.1.20 255.255.255.0
Sw-Floor-1(config-if)# no shutdown
Sw-Floor-1(config-if)# exit
Sw-Floor-1(config)# ip default-gateway 192.168.1.1