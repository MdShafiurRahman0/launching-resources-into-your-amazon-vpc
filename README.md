# Launching Resources Into Your Amazon VPC

# Step 1: Create VPC

![2024-07-29_22h51_01](https://github.com/user-attachments/assets/cacb812c-6726-46dd-b525-eae390a22876)


![image](https://github.com/user-attachments/assets/dc32fb77-2ce4-41a1-9f76-83529c44f93c)




# Step 2: Create Public Subnet 

![2024-07-29_22h57_36](https://github.com/user-attachments/assets/81a5db9c-33ec-45e4-9831-8d089e6461a4)


![2024-07-29_22h58_40](https://github.com/user-attachments/assets/8e2d8771-a435-45ee-860f-c9800e236741)


![image](https://github.com/user-attachments/assets/5131e727-ec3a-4dc5-a19d-84dc396afdfb)



# Step 3: Enable auto-assign public IPv4 address


1. In the Actions menu, select Edit subnet settings.
2. Check the box next to Enable auto-assign public IPv4 address.
3. Choose Save.


# Step 4: Create an Internet gateway

![image](https://github.com/user-attachments/assets/dd548bd4-1454-4ddd-99c1-f7aaccec752f)


1. In the left navigation pane, choose Internet gateways.

2. Choose Create internet gateway.

3. Configure your internet gateway settings:

4. Choose Create internet gateway.

5. Select your newly created internet gateway and choose Actions, then Attach to VPC.

6. Select Attach internet gateway.



# Step 5: Create a route table


![image](https://github.com/user-attachments/assets/6e198d6f-091d-4e87-b047-c537b427efac)




![2024-07-29_23h05_55](https://github.com/user-attachments/assets/4f3144ba-80d4-42cd-a69c-f2445fb700db)


1. Select the Routes tab.
2. Choose Edit routes.
3. Choose Add route near the bottom of the page.
4. Destination:



![2024-07-29_23h11_14](https://github.com/user-attachments/assets/e4d34dd9-c816-4f2c-8629-dfb3e0c068fd)



![2024-07-29_23h12_42](https://github.com/user-attachments/assets/9c3916f0-2697-4fa8-9abc-341c89061cb8)


1. For the Target, select Internet Gateway.
2. Select the only Internet Gateway id option.
3. Choose Save changes.
4. Choose the Subnet associations tab.
5. Under the Explicit subnet associations tab, choose Edit subnet associations
6. Select Public 1.
7. Choose Save associations.


![2024-07-29_23h17_40](https://github.com/user-attachments/assets/7f32a222-c49a-4592-8457-95df6bdb7f9d)



# Step 6: Create a security group

![image](https://github.com/user-attachments/assets/034300e0-19a1-40cd-b12a-1d5755112521)


1. In the left navigation pane, choose Security groups.
2. Choose Create security group.
3. Security group name:  
4. VPC: created VPC
5. Under the Inbound rules panel, choose Add rule.


![2024-07-29_23h24_49](https://github.com/user-attachments/assets/571a00ff-7841-40c9-82bb-69d4c1b3d48d)



# Step 7: Set up a Private Subnet



![image](https://github.com/user-attachments/assets/f17b28e2-1f74-486d-9fda-6a70c2ee76b0)

1. Still in your VPC console, select the Subnets tab again.

2. Select Create subnet.

3. For the VPC ID, select NextWork VPC.

4. Set the Subnet name as 

5. For the subnet's Availability Zone, use the second AZ on the dropdown (not the first!)

6. The IPv4 VPC CIDR block is already pre-set to 10.0.0.0/16

7. For the IPv4 subnet CIDR block, enter 

8. Select Create subnet.

![2024-07-30_00h09_31](https://github.com/user-attachments/assets/36cff7cb-2998-4fd1-8d21-4bda4203daba)




# Step 7: Create a Dedicated Route Table for your Private Subnet


![image](https://github.com/user-attachments/assets/c4a2fdae-e3eb-46d2-a876-94c32bc60c9c)



1. Head to the Route tables page in your console.
2. Select Create route table.
3. Name your new route table 
5. Under VPC, select NextWork VPC.
6. Select Create route table.



![2024-07-30_00h13_55](https://github.com/user-attachments/assets/9f870099-ebb6-4f2b-b334-8a2812e48503)



1. Switch tabs to Subnet associations.
2. Select Edit subnet associations under the Explicit subnet associations tab.
3. Select the checkbox next to NextWork Private Subnet.
4. Select Save associations.
5. To tidy up your Route tables' naming conventions, let's also retitle NextWork route table to 




![2024-07-30_00h16_26](https://github.com/user-attachments/assets/df374692-4e82-4571-9de5-3d246bd417f3)



# Step 8: Create a Dedicated Network ACL for your Private Subnet

![image](https://github.com/user-attachments/assets/02fff4e6-dd44-4153-86b7-83573ba08d5a)

1. Select Network ACLs from the left hand navigation panel.
2. Select Create network ACL on the top right.
3. For the name, enter 
4. Select NextWork VPC.
5. Select Create network ACL.



![2024-07-30_00h25_09](https://github.com/user-attachments/assets/e590c6f5-85d7-4853-a6a8-bad6708106f5)

1. Switch tabs to Subnet associations.
2. Select Edit subnet associations.
3. Select your private subnet.
4. Select Save changes.


![image](https://github.com/user-attachments/assets/47f66712-e93a-4d77-86e1-3a9381208f99)



# Step 9: Create 2 EC2 instances in Public & Private Subnet 



![high-step3 3](https://github.com/user-attachments/assets/5d129f2b-3859-4b6a-bc80-5cf94c07c35f)



![high-step3 6](https://github.com/user-attachments/assets/e38b12b6-3060-44a7-ada4-1abbced62a8c)


![image](https://github.com/user-attachments/assets/2aecb124-6c27-45c1-9863-f932ebc2bb11)


# Step 9: Launch a Private EC2 Instance

![image](https://github.com/user-attachments/assets/17c41d83-c7fc-43ff-9d70-a2678249784a)


## Same as previous steps:

1. Select Launch instances again.
2. Name: 
3. Amazon Machine Image (AMI): Amazon Linux 2023 AMI
5. Instance type: t2.micro


