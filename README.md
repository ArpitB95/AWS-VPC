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
 
 -  Classless Inter-Domain Routing (CIDR) is a range of IP addresses a network uses.
 -  A CIDR address looks like a normal IP address, except that it ends with a slash followed by a number.
 -  The number after the slash represents the number of addresses in the range.


### What is NACL ?
- An optional layer of security that acts as a firewall for controlling traffic in and out of a subnet. You can associate multiple subnets with a single network ACL, but a subnet can be associated with only one network ACL at a time.


![image](https://user-images.githubusercontent.com/110182832/187655765-c53afbaf-2cc3-4c4d-9eef-d2f900839edd.png)


## NACL VS SG
- Security Group is applied to an instance only when you specify a security group while launching an instance. NACL has applied automatically to all the instances which are associated with an instance. 
- It is the first layer of defense.  
- Security group is the second layer of defense.

## Stateless VS Stateful
- The key difference between stateful and stateless applications is that stateless applications don't “store” data whereas stateful applications require backing storage. 
- Stateful applications like the Cassandra, MongoDB and mySQL databases all require some type of persistent storage that will survive service restarts.

![image](https://user-images.githubusercontent.com/110182832/187655612-2d1f2e46-2950-4571-8fb5-0fd9851d3313.png)
