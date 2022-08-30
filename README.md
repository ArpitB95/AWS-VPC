# AWS-VPC


![AWS VPC](https://user-images.githubusercontent.com/110182832/187451639-0f3ffc38-96d3-4bd2-b65d-fcfa8bd2f9b9.png)




### What is VPC ?
- The following features help you configure a VPC to provide the connectivity that your applications need:

- Virtual private clouds (VPC)
  A VPC is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets.

- Subnets
  A subnet is a range of IP addresses in your VPC. A subnet must reside in a single Availability Zone. After you add subnets, you can deploy AWS resources in your VPC.

- IP addressing
  You can assign IPv4 addresses and IPv6 addresses to your VPCs and subnets. You can also bring your public IPv4 and IPv6 GUA addresses to AWS and allocate them to     resources in your VPC, such as EC2 instances, NAT gateways, and Network Load Balancers.

- Routing
  Use route tables to determine where network traffic from your subnet or gateway is directed.

- Gateways and endpoints
  A gateway connects your VPC to another network. For example, use an internet gateway to connect your VPC to the internet. Use a VPC endpoint to connect to AWS   services privately, without the use of an internet gateway or NAT device.



### What is CIDR ?
CIDR stands for Classless Inter-Domain Routing. In simpler terms, a CIDR block is an IP address range
 A VPC can accommodate two CIDR blocks, one for IPv4 and another for IPv6
