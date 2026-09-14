# Build a Virtual Private Cloud (VPC)

<p align="center">
  <img src="" width="500">
</p>

This project demonstrates how to build a Virtual Private Cloud (VPC).

- VPCs are isolated sections of the AWS Cloud that help to keep my AWS resources private and secure.
- There was already a default VPC Iin my account ever sice my AWS account was created.
- This is because AWS has set up a default VPC to allow me to deploy resources like EC2 instances / RDS databases right away - without having to create my own VPC from scratch.
- To set up my VPC, i had to define an IPv4 CIDR, which means a range of IP addresses that my VPC can allocate to the resources deployed into my VPC.

---


## 1.0 Create an Amazon VPC


Explainging the Network part:

What's a IP address and Why do i need to configure this?
R:

What does IPV4 mean?
R: 

What's CIDR block ?
R: 

- Open VPC tab -> Your VPCs

Example:
VPC = My city
IP = Number of the house
Subnet = It's a neighborhood inside my city (VPC).
CIDR block = A range of houses in my neighborhood

- Click in Create VPC
    - In VPC Settings, select:
        - VPC Only
        - In nametag, write: Vitor-VPC
        - IPv4 CIDR Block: IPv4 CIDR manual input
        - IPv4 CIDR: 10.0.0.0/16
    
    Click in CREATE VPC


---

## 1.1 Create a public subnet

- Click in Subnets tab -> Create Subnet
- In VPC ID, select the VPC that we just create, in this case, Vitor-VPC.
- In IPv4 subnet CIDR block, type 10.0.0.0/24 
- In Tags, add one tag, the key should be "Name" and the value shoud be "Public 1"
- Click in Create Subnet

Next Step:

- Select the public subnet that we created.
- In the Actions button, ckick in Edit subnet settings.
- In Auto-assign IP settings, click in "Enable-assign public IPv4 Address -> Click in Save.

Explanation:
- Subnets are subsections of my VPC, just like how neighbourhoods are subsections of a city.
- There are already subnets existing in my account, one for every Availability Azone in the Region that i've set up my VPC in.
- I named my subnet Public 1, but that doesn't automatically make my subnet a public subnet.
    - For a subnet to be considered public, it has to be connected to an internet gateway.

What's the difference between a Public Subnet and a Private Subnet ?
R:


---

## 1.2 Create an Internet Gateway

What's an Internet Gateway ?
R:

- Click in Internet Gateways -> Click in Create internet gateway.
- In the Name tag, the name should be "Vitor IG".
- In Tags, key should be "Name" and value should be "Vitor IG".
- Click in the created Internet Gateway "Vitor IG" -> Go to Actions and click in Attach to VPC.
- In available VPCs, select the VPC that we have created, in this case, Vitor-VPC ans click in the orange button Attach internet Gateway.



