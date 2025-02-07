## EBS: 
Amazon Elastic Block Store (EBS) is like a virtual hard drive for your EC2 instances in the AWS cloud. It provides persistent block storage that you can attach to your virtual servers. Think of it as a way to store your data separately from your EC2 instance, allowing you to keep your data even if your instance is stopped or terminated. You can create, attach, detach, and delete EBS volumes as needed, just like you would with a physical hard drive.
SSD (Solid State Drive) and HDD (Hard Disk Drive) are two primary types of storage devices, each with distinct characteristics.

 
SSDs utilize flash memory for data storage, enabling faster read and write speeds compared to HDDs. Moreover, SSDs have no moving parts, making them more durable against physical shock and less susceptible to mechanical failures. These qualities make SSDs particularly well-suited for workloads demanding high performance, such as databases, virtualization, and web servers. However, SSDs generally come at a higher cost per gigabyte compared to HDDs.

On the other hand, HDDs rely on spinning magnetic disks and a physical read/write head to store and access data. While they typically offer slower read and write speeds compared to SSDs, HDDs excel in providing larger storage capacities at a lower cost. This makes them a preferred choice for applications requiring ample storage space, such as bulk storage, archival, and backup solutions. 

## CREATE AN EBS VOLUME (SAME AVAILABILITY ZONE)
first create an ec2 insatnce 

 ![image](https://github.com/user-attachments/assets/3aeca2b6-e3a5-4eae-8c9e-29e783450e3b)

![image](https://github.com/user-attachments/assets/1f2ac1b4-d53c-4df3-b1ff-815a66e622d9)

 
from side navigation hit on volume and check the availability zone for that volume 

 ![image](https://github.com/user-attachments/assets/7d88289e-6b12-4596-83a6-3f85b0674ff5)

Create an EBS Volume:  select "Volumes" from the left-hand menu. Click on "Create Volume", choose the desired volume type, size, and availability zone(choose the same az as instance). 
 

 ![image](https://github.com/user-attachments/assets/df900cb3-8a0c-4ab4-85df-16f7ab20d5e4)

![image](https://github.com/user-attachments/assets/1e51d385-5034-41d9-addf-8034afe9e599)

Attach the Volume to an Instance: Once the volume is created, select it from the list of volumes, click "Actions", and choose "Attach Volume".

 ![image](https://github.com/user-attachments/assets/8698f57c-838e-4cc6-a7c2-657c16820b89)

![image](https://github.com/user-attachments/assets/c545f74d-f25e-4796-a6ae-1b499edddf4b)

check under instance >storage there are two volumes attached .

 ![image](https://github.com/user-attachments/assets/52619c76-e6b1-4610-9f7d-15f53c2ea537)

same way we can detach the volume by selecting volume >action>detach volume
 
 ![image](https://github.com/user-attachments/assets/0571e593-19c6-4a09-bebb-2e837739b6d3)

![image](https://github.com/user-attachments/assets/895c5147-b173-4e51-97e8-128a9062e9f3)

## CREATE AN EBS VOLUME (DIFFRENT AVAILABILITY ZONE)
Click on "Create Volume", choose the desired volume type, size, and availability zone(this time choose different one). Ensure that encryption is enabled while creating the volume.

 ![image](https://github.com/user-attachments/assets/3bbca8b1-3398-4beb-9764-7ae576d043c9)

![image](https://github.com/user-attachments/assets/5ef03db2-f134-4529-b6fc-20dc2a14b823)
 
Create a Snapshot: Select the EBS volume, click "Actions", and choose "Create Snapshot".and choose the volume id we just created.

 ![image](https://github.com/user-attachments/assets/cf423395-d2d7-48da-90f7-63353d1fe394)

click on create  volume from snapshot > and save 

 ![image](https://github.com/user-attachments/assets/a86d92eb-4992-4cf2-b1c9-d3e6fb231eec)

Attach Volume to the Instance: Once the volume is created select it from the volume list, click "Actions", and choose "Attach Volume". Select the instance to attach the volume.

![image](https://github.com/user-attachments/assets/276b5bd8-e374-457c-b91b-115d51cd8da4)

![image](https://github.com/user-attachments/assets/e73f831f-32f1-4307-a0eb-910af8ef34e4)

now you can see we have successfully created an EBS volume using snapshot for different az

 ![image](https://github.com/user-attachments/assets/99ff6454-8b4f-48e1-a075-f89d909596ba)



