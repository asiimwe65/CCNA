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

✅ Logical AND in Networking (Explained Clearly)
The logical AND is one of the three basic Boolean operations (the others are OR and NOT). In digital logic:

1 = True

0 = False

AND only gives 1 (True) when both inputs are 1.

Input A	Input B	A AND B
1	1	1
1	0	0
0	1	0
0	0	0

So: both bits must be 1 for the result to be 1.

📌 Why is AND Used in IPv4?
To find the network address of a host, the host’s IPv4 address is ANDed bit by bit with its subnet mask.

This process determines:

The network portion of the address (bits where the subnet mask has 1s).

Sets the host portion to 0 (bits where the subnet mask has 0s).

📝 Example: Find the Network Address
Host IPv4 Address: 192.168.10.10
Subnet Mask: 255.255.255.0 (/24)

Step 1: Convert both to binary

Address	Binary Representation
192.168.10.10	11000000.10101000.00001010.00001010
255.255.255.0	11111111.11111111.11111111.00000000

Step 2: Perform bitwise AND

Copy
Edit
11000000.10101000.00001010.00001010 (Host Address)
AND
11111111.11111111.11111111.00000000 (Subnet Mask)
=
11000000.10101000.00001010.00000000 (Network Address)
Step 3: Convert result back to decimal
Result:

scss
Copy
Edit
192.168.10.0 (/24)
This is the network address for the host.

🌟 Key Takeaways
✔ Logical AND finds the network portion of an IPv4 address.
✔ Only 1 AND 1 gives 1; any other combination gives 0.
✔ ANDing host address with subnet mask zeros out the host bits, leaving only the network bits.
✔ Example:
192.168.10.10 AND 255.255.255.0 = 192.168.10.0
This tells the host it belongs to the 192.168.10.0/24 network.