# Setting up a Web Server
## Prerequisites
- Have an AWS account
- Have a key pair set up

## Setting up a Virtual Private Cloud (VPC)
- Navigate to the VPC section of AWS (you can enter "VPC" in the top search bar)
- Hit the orange `Create VPC` button on the top right. This will take you to the "Create VPC" page
- Give your VPC a name. In this case, the format is `Eng84_name_vpc`
- Give your VPC an IPv4 following this pattern: `x.y.0.0/16` where x and y are between 0 and 255
- Hit the ornage `Create VPC` button in the bottom right
- 

## Setting up Subnets
- Navigate to the Subnets section of AWS (on the left there is a sidebar where you should find "Subnets")
- Hit the orange `Create subnet` button on the top right. This will take you to the "Create subnet" page
- Select the VPC you made earlier
- Name the subnet something useful to you. For example, `Eng84_name_private_subnet`
- Choose an Availablity Zone if you want
- Enter a IPv4 CIDR block following this pattern: `x.y.z.0/24`, with x and y being the same as your VPC and z being between 0 and 255
- Hit the orange `Create subnet` button on the bottom right
- Repeat for the number of subnets you require

## Setting up a Route Table
- Navigate to the Route Tables section of AWS (on the left there is a sidebar where you should find "Route Tables")