# Private-Subnet

## Private Subnet demonstrates how to create and configure a private subnet within an AWS Virtual Private Cloud (VPC). This project ensures secure deployment of resources that do not require direct internet access, such as databases, backend servers, or internal services.



Features

Secure Networking: Deploy resources in a private subnet without direct internet exposure.

Access Control: Use NAT gateways or instances for controlled internet access.

Integration: Seamlessly connect private subnets to public subnets or other VPC resources.

Scalability: Leverage private subnets in multi-tier architecture.




## Prerequisites

Before starting, ensure you have:

An AWS account with permissions to manage VPCs, subnets, and gateways.

AWS CLI installed and configured.

Basic understanding of networking concepts.



## Setup and Installation

Step 1: Create a VPC

Open the AWS Management Console and navigate to VPC.

Click Create VPC and provide the following details:

Name: MyVPC

IPv4 CIDR Block: 10.0.0.0/16

IPv6 CIDR Block: No IPv6 CIDR Block.

Click Create.

Step 2: Create a Private Subnet

Navigate to Subnets in the VPC dashboard.

Click Create Subnet and provide the following details:

Name: PrivateSubnet

VPC: Select MyVPC.

Availability Zone: Choose one.

IPv4 CIDR Block: 10.0.1.0/24.

Click Create Subnet.

Step 3: Add a Route Table

Navigate to Route Tables in the VPC dashboard.

Click Create Route Table and select MyVPC.

Name the route table PrivateRouteTable.

Associate the private subnet with this route table.

Step 4: Configure NAT Gateway (Optional)

Navigate to NAT Gateways and create a new NAT gateway in a public subnet.

Attach an Elastic IP to the NAT gateway.

Update the PrivateRouteTable:

Add a route with destination 0.0.0.0/0 and target the NAT gateway.




$$ Usage

Launch Instances in the Private Subnet:

Use the EC2 dashboard to launch an instance.

Select PrivateSubnet during network configuration.

Access the Instance:

Use a bastion host or VPN to access instances in the private subnet.

Test Connectivity:

Verify internal communication between resources within the private subnet.

Confirm controlled internet access via the NAT gateway (if configured).


## Example Configuration

VPC CIDR Block:

10.0.0.0/16

Subnet CIDR Block:

Private Subnet: 10.0.1.0/24

Route Table:

Destination: 0.0.0.0/0

Target: NAT Gateway (nat-0abcd1234efgh5678)

## Outcome

By completing this project, you will:

Understand how to configure and use private subnets in AWS.

Implement secure and controlled networking for sensitive resources.

Gain hands-on experience with NAT gateways and routing configurations.


