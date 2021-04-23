# Setting up a Web Server (Part One)
## Prerequisites
- Have an AWS account

## Setting up a Virtual Private Cloud (VPC)
- Navigate to the VPC section of AWS (you can enter "VPC" in the top search bar)
- Hit the `Create VPC` button. This will take you to the "Create VPC" page
- Give your VPC a name. In this case, the format is `Eng84_name_vpc`
- Give your VPC an IPv4 following this pattern: `x.y.0.0/16` where x and y are between 0 and 255
- Hit the `Create VPC` button. This will complete the creation of the VPC

## Setting up Subnets
- Navigate to the Subnets section of AWS (on the left there is a sidebar where you should find "Subnets")
- Hit the `Create subnet` button. This will take you to the "Create subnet" page
- Select the VPC you made earlier
- Name the subnet something useful to you. For example, `Eng84_name_private_subnet`
- Choose an Availablity Zone if you want
- Enter a IPv4 CIDR block following this pattern: `x.y.z.0/24`, with x and y being the same as your VPC and z being between 0 and 255
- Hit the `Create subnet` button
- Repeat for the number of subnets you require

## Setting up a Route Table
- Navigate to the Route Tables section of AWS (on the left there is a sidebar where you should find "Route Tables")
- Hit the `Create route table` button. This will take you to the "Create route table" page
- Give this route table a name corrosponding to what it will be used for. For the private network example, I'm using `Eng84_katalyst_public_rt`
- Select your VPC
- Hit the `Create route table` button
- Repeat for the number of subnets you have

## Assigning a Subnet to a Route Table
- Navigate to the Route Tables section of AWS if you are not there already (on the left there is a sidebar where you should find "Route Tables")
- Select your route table and then the tab labled "Subnet Associations"
- Click the `Edit subnet associations` button. It will take you to the "Edit subnet associations" page
- Select the subnet that corrosponds to the route table, then hit "Save"
- Repeat for the number of subnets you have

## Create and Attach an Internet Gateway
- Nagviate to Internet Gateways section of AWS (on the left there is a sidebar where you should find "Internet Gateways)
- Hit the `Create internet gateway` button. This will take you to the "Create internet gateway" page
- Name your gateway then click the `Create internet gateway` button
- Make sure your internet gateway is selected then go the "Actions" dropdown menu and select "Attach to VPC" (this will take you to a new page)
- Select your VPC then hit the `Attach internet gateway` button

## Connecting Subnets to the Internet
- Navigate back to the Route Tables section
- Select your public route table and navigate to the "Routes" tab
- Select the `Edit routes` button. You will be taken to the "Edit Routes" page
- Add the route `0.0.0.0/0` to the destination
- Select `Internet Gateway` then the name of you gateway for the target
- Hit the `Save routes` button

## Creating EC2 Instances
This will be covered in [another guide](ec2_instance_setup.md)