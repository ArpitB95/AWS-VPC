# AWS-VPC


![AWS VPC](https://user-images.githubusercontent.com/110182832/187451639-0f3ffc38-96d3-4bd2-b65d-fcfa8bd2f9b9.png)


## Steps for VPC:

- Step-1:In AWS create a VPC with CIDR block (your post code, address on internet) 10.0.0.0/16

- CIDR 10.0.2.0/24 (for me)


- Step-2: Internet gateway
  2.1- add internet gateway to your VPC-name


- CIDR 10.0.2.0/24
- Step-3: create public subnet 

- Step-4: Create route table -
  4.1:    edit rules to add subnet(public for now)
  allow in security rules - 0.0.0.0/16
                            10.0.0.0/16





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




## How to setup vpc ?

## Step-1:
 - In AWS create a VPC with CIDR block (your post code, address on internet) 10.0.0.0/16
 - Go to VPc and click create vpc and name your vpc
 - Give IPv4 CIDR 
 - click on create vpc
 
 <img width="419" alt="image" src="https://user-images.githubusercontent.com/110182832/187741604-7b6639b8-156d-452b-8476-3c3c615aaf96.png">


## Step-2
- Create internet gateway

<img width="425" alt="image" src="https://user-images.githubusercontent.com/110182832/187745438-0948adb2-7246-4460-8bb6-d93f2b291c36.png">


## Step-2:
- create public subnet
- go to subnet and click create subnet


<img width="635" alt="image" src="https://user-images.githubusercontent.com/110182832/187742084-01c68c60-c205-4788-a456-810dcf5e1849.png">



- select the vpc that you want to create your private/public subnet in (In this case : eng122-Arpit-devops-vpc)
- Give Ipv4 CIDR block (address of your subnet) (Here it's 10.0.2.0/24)
- click on create subnet

<img width="375" alt="image" src="https://user-images.githubusercontent.com/110182832/187742688-b3a82453-5096-4e79-a432-92561e1f0f24.png">


## Step-3
- create route table

<img width="441" alt="image" src="https://user-images.githubusercontent.com/110182832/187743900-f58ff17f-bbef-43f6-b615-c3553af83cfe.png">

- Edit routes and allow internet gateway (0.0.0.0/0) and local (10.0.0.0/16)
- for public subnet, we need to allow requests from the internet and requests from the internet comes through internet gateway


<img width="613" alt="image" src="https://user-images.githubusercontent.com/110182832/187744494-a1f8d118-20c2-465c-a988-c44dd9dfd92e.png">

- attach this route table to public subnet that you created

<img width="610" alt="image" src="https://user-images.githubusercontent.com/110182832/187745267-e3c71159-c024-415f-964e-294308e03ba0.png">




- CIDR 10.0.2.0/24 (for me)


- Step-2: Internet gateway
  2.1- add internet gateway to your VPC-name


- CIDR 10.0.2.0/24
- Step-3: create public subnet 


- Step-4: Create route table -
  4.1:    edit rules to add subnet(public for now)
  allow in security rules - 0.0.0.0/16
                            10.0.0.0/16
                            
                           
## Create private subnet
- Give name
- Select your created VPC
- Assign IPv4 CIDR block (10.0.13.0/24)

<img width="385" alt="image" src="https://user-images.githubusercontent.com/110182832/187745907-a47db253-ef88-4ab4-a53c-ab30eb1b1773.png">


## Create rout table for private subnet

<img width="385" alt="image" src="https://user-images.githubusercontent.com/110182832/187746399-b2f0f466-f74f-481a-a6c0-8c9c2c74acd5.png">

- For private subnet, you need to allow requests from the app only, because database is hosted in the private subnet and database should not be
  accessed by anyone from the internet.
 - So for the route rules allow only local (10.0.0.0/16)
 
 <img width="614" alt="image" src="https://user-images.githubusercontent.com/110182832/187746839-5c04c57a-05e1-43fc-a631-2d3a47960f3b.png">

- Attach this route table to private subnet that you created in previous step

<img width="614" alt="image" src="https://user-images.githubusercontent.com/110182832/187747049-d31199c1-3052-4ae1-8373-56901b9c9e1f.png">


<img width="497" alt="image" src="https://user-images.githubusercontent.com/110182832/187747434-0df871c1-9ac9-422b-ac85-90eae41f1490.png">



## Now launch App Ec2 instance and DB EC2 from AMI

## Launch App EC2 from AMI (eng122-Arpit-App-AMI)

<img width="941" alt="image" src="https://user-images.githubusercontent.com/110182832/187747794-b6f14143-60c8-4dd4-a620-0501f0bf6329.png">


- While launching an instance from AMI- on 3rd step 
- select your VPC that you created
- select public subnet for your app instance and
- Auto assigning public ID enable

<img width="933" alt="image" src="https://user-images.githubusercontent.com/110182832/187748468-3ac15bd5-7396-451b-9331-104eaf15d1a9.png">


- For security group allow port 22 (my IP), port 3000(for reverse proxy), port 80 (for http requests)


## Launch database EC2 from API

- Launch db instance from AMI (eng122-Arpit-DBAMI)
- Follow the same steps but in security configuration step-6 , assign IPv4 CIDR of private subnet

<img width="624" alt="image" src="https://user-images.githubusercontent.com/110182832/187749642-3292c1f4-c475-4b7a-a24f-ab763a27fced.png">


<img width="943" alt="image" src="https://user-images.githubusercontent.com/110182832/187749769-2753d237-5f8d-4b49-9e7b-7f631d7a93c0.png">


- Then launch the instance



## Now ssh into the app ec2
- create environment variable of db instance into app instance
- in app instance go to sudo nano .bash.rc
- create env variable
- export DB_HOST=mongodb://"private ipv4 of db instance":27017/posts


debugging npm error:

run
ps aux
sudo kill -9 2246 (after -9 give the number of node app.js process)
keep changing number at the end

if persists try:
sudo systemctl disable npm.service
sudo systemctl kill npm.service
sudo systemctl stop npm.service
npm start
