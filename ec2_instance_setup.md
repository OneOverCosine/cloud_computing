# Setting up an EC2 Instance

## Prerequisites
- Have an AWS account
- Have a key pair set up

## Setting up an Instance (for the app)
1. Navigate to the EC2 Dashboard
2. Navigate to the "Instances" page (using the sidebar on the left)
3. Select the `Launch instances` button
4. Select "Free tier only" then choose the machine image you want (for this example we're using `Ubuntu Server 16.04`)
5. Select `t2.micro` (should be automatically selected)
6. Click `Next: Configure Instance Details`

### Configure Instance Details
1. For `Network` choose the VPC you created
2. For `Subnet` select a subnet that corrosponds to the app
3. Select "Enable" for `Auto-assign Public IP`
4. Click `Next: Add Storage`, then `Next: Add Tags`
(We're not dealing with large amounts of data for this project)

### Adding Tags
1. Click `Add Tag`
2. For the Key, type "Name"
3. For Value, enter the name of this instance
4. Click `Next: Configure Security Group`

### Configure Security Group
1. Give your security group a name and description
2. Click `Add Rule`
3. Fill in the following values:
    - Type: HTTP, Protocol: TCP, Port Range: 80, Source: (Custom) 0.0.0.0/0, ::/0
4. Add a suitable description
5. Click `Review and Launch` then `Launch` once you've made sure everything is correct

##