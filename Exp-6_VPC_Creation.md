# VPC Creation

1. Go to AWS Management Console and navigate to EC2 instances.
2. Create an instance to it and specify the foolowing spaces.

```text
I. Create a VPC

1. Open the VPC Dashboard.
2. Click on "Create VPC."
3. Choose "VPC with a Single Public Subnet" or customize as needed.
4. Enter the VPC name, CIDR block (e.g., 10.0.0.0/16), and subnet details.
5. Click "Create VPC."

II. Create Subnets

Subnets divide your VPC's IP address range into smaller networks.

1. Go to the VPC Dashboard.
2. Select "Subnets" from the left-hand menu.
3. Click "Create Subnet."
4. Select the VPC, enter a name, availability zone, and CIDR block (e.g., 10.0.1.0/24).
5. Click "Create Subnet."

III. Create and Configure an Internet Gateway

1. In the VPC Dashboard, select "Internet Gateways."
2. Click "Create Internet Gateway."
3. Enter a name and click "Create."
4. Attach the Internet Gateway to your VPC:
          .Select your Internet Gateway.
          .Click "Actions" > "Attach to VPC."
          .Choose your VPC and click "Attach."

IV. Create Route Tables and Routes

1. In the VPC Dashboard, select "Route Tables."
2. Click "Create Route Table."
3. Select the VPC, enter a name, and click "Create."
4. Add a route for internet traffic:
    .Select your route table.
    .Click "Routes" > "Edit routes."
    .Click "Add route."
    .Destination: 0.0.0.0/0
    .Target: Select your Internet Gateway.
    .Click "Save routes."
5. Associate the route table with your subnets:
    .Select the route table.
    .Click "Subnet Associations" > "Edit subnet associations."
    .Select your subnets and click "Save."

V. Launch an EC2 Instance

1. Open the EC2 Dashboard.
2. Click "Launch Instance."
3. Choose an Amazon Machine Image (AMI).
4. Choose an instance type.
5. Configure instance details:
    .Network: Select your VPC.
    .Subnet: Select your subnet.
    .Auto-assign Public IP: Enable.
6.Add storage and tags as needed.
7.Configure security group:
    .Allow SSH (port 22) from your IP.
8.Review and launch the instance.

VI. Configure Dynamic Hostname Resolution

1. Open the Route 53 Dashboard.
2. Click "Create Hosted Zone."
3. Enter the domain name and click "Create."
4. Create a record set:
    .Click "Create Record Set."
    .Name: Enter a subdomain or leave blank for root domain.
    .Type: Select "A - IPv4 address."
    .Alias: No.
    .Value: Enter the public IP of your EC2 instance.
    .Click "Create."

VII.Update the EC2 Instance with New Hostname

1.SSH into your EC2 instance.
2.Edit the hostname configuration
``` bash
sudo hostnamectl set-hostname new-hostname






```
