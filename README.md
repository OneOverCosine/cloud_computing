# Cloud Computing with AWS

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
**On premises**  
**Cloud**  
**Hybrid**

## Scaling
**Scaling up** - This is when you upgrade the servers that are currently in use. This can be increasing the memory the servers have.  
**Scaling out** - This is when you get new servers.  
**Scaling down** - Removing resources (usually servers) that aren't in use to say money and resources.

## Auto-scaling
This is a handy tool for making sure your business can always keep up with demand. It also saves money when the demand is low.Consider this senario:  
You own an online shop. Most of the year, you get around (let's say) 100-150 customers each day. At Christmas, the number of customers per day increases by 500% (the important think is that your servers as they are can't handle this traffic). With `on premises` computing you need to buy and setup servers that will only be used once a year. With `cloud computing` you can pay for more resources as and when you need them.


## EC2 - Elastic Cloud Compute
### App server
- Spinning up an EC2 instance (we use the Ireland DZ) - make sure it's Ubuntu 16.04
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

### Extras
I am responsible for the security of the instances I create

.  
.  
.  
.  
Note: I tend to use 'Katalyst' as a placeholder name