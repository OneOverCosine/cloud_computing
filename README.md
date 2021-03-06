# Cloud Computing with AWS

## [Setting up a Web Server](web_app_setup.md)

## What is Cloud Computing?
It's the on-demand delivery of IT resources - such as computing power, storage, and databases - via the Internet. This is an alternative to buying, owning, and maintaining physical servers.  
You recieve this service on a pay-as-you-go basis, so you only spend money on what you need.  

### Benefits of Cloud Computing
- Pay as you go (only pay for what you need)
- More scalable than on-premises computing
- Better disaster recovery
- Server maintainance done by servive provider

## What is AWS?
_(It's a cloud service provider. They offer more than 100 cloud services on their platform.)_ Duplicated notes

It's a secure cloud service platfrom. They offer computing power, databases, networking, content sorage, and more. Services are offered on a pay-as-you-go basis.

### Three Benefits of using AWS
- Security
- Experience (these guys have been doing this for a while)
- Flexible
- Easy to use
- Scalable

### Who Uses AWS?
- BBC
- Netflix
- Twitch
- Facebook
- LinkedIn

## Types of Computing
__On premises__  
__Cloud__  
__Hybrid__

## Scaling
__Scaling up__ - This is when you upgrade the servers that are currently in use. This can be increasing the memory the servers have.  
__Scaling out__ - This is when you get new servers.  
__Scaling down__ - Removing resources (usually servers) that aren't in use to save money and resources.

## Auto-scaling
This is a handy tool for making sure your business can always keep up with demand. It also saves money when the demand is low. Consider this senario:  
You own an online shop. Most of the year, you get around (let's say) 100-150 customers each day. At Christmas, the number of customers per day increases by 500% (the important think is that your servers as they are can't handle this traffic). With `on premises` computing you need to buy and setup servers that will only be used once a year. With `cloud computing` you can pay for more resources as and when you need them.

## Software Architecture
### Monolithic (One-Tier or Standalone application)
![One-Tier](./images/one-tier-software-architecture.png)

### Two-Tier (Client-Server application)
![Two-Tier](./images/two-tier-software-architecture.png)

### Three-Tier
![Three-Tier](./images/three-tier-software-architecture.png) 

## EC2 - Elastic Cloud Compute
### App server
- Spinning up an EC2 instance (we use the Ireland region) - make sure it's Ubuntu 16.04
- Choose free tier for t2.micro when selecting instance type
- Naming convention for naming any service on AWS - `Eng84_myname_app`. For this example do `Eng84_katalyst_app`
- Create a security group named `Eng84_katalyst_app_sg`. Details: SSH, TCP, 22, IP
- Review and launch

---
Once inside the machine (in admin mode):
- Run `apt-get update` and `apt-get upgrade`
- Run `apt-get install ngnix` to install Nginx
- To check that it has installed, run `systemctl status nginx`
- Now you can use the public ip to access the default Nginx page!
.  
.  
- `scp -ri [pem file] [file/folder] ubuntu@[ip]:[path]` For copying files from main os to vm
- `git clone [repository]`

### DB server
This one won't have a public IP. It will only be accessed through the `app` machine.  

### AMI - Amazon Machine Image
Create a snapshot of a VM instance for use later.

## Extras
I am responsible for the security of the instances I create  
[Info](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/) from AWS themselves!

### Security groups
Works like a firewall for the instance. It only lets specific traffic through.

### Subnet
Divides a network into two or more 'sub' networks.
- Works across the whole application.
- 

### Virtual Private Cloud (VPC)
Can have multiple subnets inside them. Determines who can access the application.

### Multi-cloud Arcitecture
Deploying the same app using different clouds (using two or more cloud service providers). This is to increase availability. If one goes down then we still have the other.

### Network Access Control List (NACL)
[Detailed reading](https://www.knowledgehut.com/tutorials/aws/aws-nacl)
Helps provide a laayer of security to the AWS stack. It helps in providing a firewall, thus helping secure VPCs and subnets.  
Components of a NACL
- __Rule number__ - Every rule is assigned a unique number. The rule's priority is also determined by this number. Note that rule are created with specific increments. For example, the difference between two rules could be 1, 10, or 100. _All rules created have the same difference_
- __Type__ - Tells us about the type of traffic. SSH, HTTP, HTTPS
- __Protocol__ - The set of rules that are applied to every request
- __Portrange__ - The listening port
- __Inbound rules__ - Aka source. These rules talk about the source from where the request or traffic is coming from. Also about the destination port/ the port through which the response is sent
- __Outbound rules__ - Aka destination. These rules talk about where ther response should be sent. Also about the destination port
- __Allow/Deny__ - Whether the specific traffic has to be allowed or denied


### REGIONS
Geographical position of servers, used to host applications

.  
.  
.  
.  
Note: I tend to use 'Katalyst' as a placeholder name