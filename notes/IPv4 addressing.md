When working with IPv4 addresses, writing out subnet masks in dotted decimal form (like 255.255.255.0) can be long and repetitive. To make this easier, there is an alternative called the prefix length.

🌟 What is a Prefix Length?
The prefix length tells us how many bits in the subnet mask are set to 1. It is written using slash notation, which means placing a forward slash / after the IPv4 address, followed by the number of 1 bits.

For example:

A subnet mask of 255.255.255.0 in binary is:

Copy
Edit
11111111.11111111.11111111.00000000
Here, there are 24 bits set to 1.

So instead of writing 192.168.10.10 255.255.255.0, you write:

Copy
Edit
192.168.10.10/24
This shorthand makes it quicker to represent both the IP address and its subnet mask.

📌 Why is it Called a Prefix?
In networking, the part of the address covered by the 1s in the subnet mask is called the network prefix. It identifies the network portion of the IP address, while the remaining 0s represent the host portion (specific devices in that network).

So, the prefix length simply indicates how much of the address is reserved for the network.

📊 Example Table: Subnet Masks and Prefix Lengths
Subnet Mask	Binary Representation	Prefix Length
255.0.0.0	11111111.00000000.00000000.00000000	/8
255.255.0.0	11111111.11111111.00000000.00000000	/16
255.255.255.0	11111111.11111111.11111111.00000000	/24
255.255.255.128	11111111.11111111.11111111.10000000	/25
255.255.255.252	11111111.11111111.11111111.11111100	/30

This table shows how subnet masks can be written more compactly using prefix length.

✅ Key Takeaways:

The prefix length is the number of 1 bits in the subnet mask.

It uses slash notation (e.g., /24 for 255.255.255.0).

It simplifies how we write IP addresses and subnet information.

