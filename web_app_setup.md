# Setting up a Web Server (Part One)
## Prerequisites
- Have an AWS account

## Setting up a Virtual Private Cloud (VPC)
1. Navigate to the VPC section of AWS (you can enter "VPC" in the top search bar)
2. Hit the `Create VPC` button. This will take you to the "Create VPC" page
3. Give your VPC a name. In this case, the format is `Eng84_name_vpc`
4. Give your VPC an IPv4 following this pattern: `x.y.0.0/16` where x and y are between 0 and 255
5. Hit the `Create VPC` button. This will complete the creation of the VPC

## Setting up Subnets
1. Navigate to the Subnets section of AWS (on the left there is a sidebar where you should find "Subnets")
2. Hit the `Create subnet` button. This will take you to the "Create subnet" page
3. Select the VPC you made earlier
4. Name the subnet something useful to you. For example, `Eng84_name_private_subnet`
5. Choose an Availablity Zone if you want
6. Enter a IPv4 CIDR block following this pattern: `x.y.z.0/24`, with x and y being the same as your VPC and z being between 0 and 255
7. Hit the `Create subnet` button
8. Repeat for the number of subnets you require

## Setting up a Route Table
1. Navigate to the Route Tables section of AWS (on the left there is a sidebar where you should find "Route Tables")
2. Hit the `Create route table` button. This will take you to the "Create route table" page
3. Give this route table a name corrosponding to what it will be used for. For the private network example, I'm using `Eng84_katalyst_public_rt`
4. Select your VPC
5. Hit the `Create route table` button
6. Repeat for the number of subnets you have

## Assigning a Subnet to a Route Table
1. Navigate to the Route Tables section of AWS if you are not there already (on the left there is a sidebar where you should find "Route Tables")
2. Select your route table and then the tab labled "Subnet Associations"
3. Click the `Edit subnet associations` button. It will take you to the "Edit subnet associations" page
4. Select the subnet that corrosponds to the route table, then hit "Save"
5. Repeat for the number of subnets you have

## Create and Attach an Internet Gateway
1. Nagviate to Internet Gateways section of AWS (on the left there is a sidebar where you should find "Internet Gateways)
2. Hit the `Create internet gateway` button. This will take you to the "Create internet gateway" page
3. Name your gateway then click the `Create internet gateway` button
4. Make sure your internet gateway is selected then go the "Actions" dropdown menu and select "Attach to VPC" (this will take you to a new page)
5. Select your VPC then hit the `Attach internet gateway` button

## Connecting Subnets to the Internet
1. Navigate back to the Route Tables section
2. Select your public route table and navigate to the "Routes" tab
3. Select the `Edit routes` button. You will be taken to the "Edit Routes" page
4. Add the route `0.0.0.0/0` to the destination
5. Select `Internet Gateway` then the name of you gateway for the target
6. Hit the `Save routes` button

## Creating EC2 Instances
This will be covered in [another guide](ec2_instance_setup.md)