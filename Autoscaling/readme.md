## AUTOSCALING 

An autoscaling application is a system that automatically adjusts the number of instances (servers) running your application based on demand. Here's how it works:

- Auto Scaling Groups: These are collections of EC2 instances managed by the autoscaling system.
- Minimum and Maximum Capacity: You set limits on the number of instances allowed in each group. The system ensures it never falls below the minimum or exceeds the maximum.
- Vertical Scaling: Upgrading the hardware of existing instances.
- Horizontal Scaling: Creating or removing identical instances.
- Desired Capacity: You can also specify how many instances you want to maintain at all times.
- Scaling Policies: These policies dictate when the system should add or remove instances based on demand.

* Types of Scaling Policies:

- Target-based: Keeping a certain metric (like CPU usage) at a specific level. CPU to stay around 40%
- Simple: Triggering scaling based on a simple condition (like CPU exceeding a threshold). CPU to stay around 40%
- Step: Adding or removing instances in predefined steps based on metrics.increse minimum capacity to 6 at 1 Am on Monday

In simpler terms, an autoscaling application automatically adjusts the number of servers you're using based on how much demand there is. If more people start using your app, it adds more servers; if fewer people are using it, it removes servers to save costs.



## CREATE AUTOSCALING GROUP 
To create an auto-scaling group in AWS EC2, navigate to the Auto Scaling Groups section, then click "Create Auto Scaling group." If a launch template isn't available, create one by specifying configurations similar to launching a new EC2 instance. Include user data in the Advanced details section to install an Apache web server with a basic webpage on the EC2 instance. After configuring, click "Create launch template" to finalize. This establishes the necessary infrastructure for auto-scaling based on defined parameters and configurations.
 
 
 ![image](https://github.com/user-attachments/assets/ead20481-2beb-4053-9754-224a4842cefc)
 ![image](https://github.com/user-attachments/assets/a4221949-5455-447a-9ae9-ab9d2abf58d0)
![image](https://github.com/user-attachments/assets/6ff729b5-4b3b-46af-8249-83943266f08d)

![image](https://github.com/user-attachments/assets/dd826c70-e74e-43e1-b86c-bb43d0302a59)
![image](https://github.com/user-attachments/assets/216834e0-36dd-4272-bc31-df957441d353)
![image](https://github.com/user-attachments/assets/8bed520a-3000-4b1f-8fc9-6625a729c51e)

 ![image](https://github.com/user-attachments/assets/cee0cec6-297f-4769-b421-c9e84f73e3d5)
 
To set up the auto-scaling group, first, choose a name here I chose she  Next, select all available zones for maximum availability, set the health check grace period to 300 seconds, and specify the desired capacity as 3 instances with a minimum of 1 and a maximum of 3. Enable instance scale-in protection to prevent new instances from being terminated. Skip notifications and tags, then review and create the auto-scaling group. 
 
 ![image](https://github.com/user-attachments/assets/805d859a-8e2c-4693-9333-10cab3627071)
![image](https://github.com/user-attachments/assets/2b6d0fb7-4eac-4dc8-8a74-7d7fd942605d)

 ![image](https://github.com/user-attachments/assets/cd48ae96-290b-43aa-b7b0-59d4511a51fb)

 
 ![image](https://github.com/user-attachments/assets/c2f6037b-317b-4586-866a-d39ac81d560d)
![image](https://github.com/user-attachments/assets/d7ec6b00-1284-4071-959a-fad115acbdbe)
![image](https://github.com/user-attachments/assets/1a5bcf3f-946c-48f4-8210-2328f50872d2)
![image](https://github.com/user-attachments/assets/7525deba-1aec-419b-bd4b-8ac7b7eab5d7)
![image](https://github.com/user-attachments/assets/37bb4a32-cd79-42f0-bbf1-ff49676df74c)
![image](https://github.com/user-attachments/assets/fc24b24d-bb2a-4d4a-b4a9-3130492ca99e)
![image](https://github.com/user-attachments/assets/62a01833-b12e-4ee7-b77c-e9a0cab43cbc)
![image](https://github.com/user-attachments/assets/28186962-df22-435a-be75-74c47c843acb)

The first auto-scaling group is now successfully created.

 ![image](https://github.com/user-attachments/assets/7c2f2074-e88d-4c7f-be0b-19d032e65ff3)

Now, we observe three running instances launched through the auto-scaling group. Checking one instance's public IP, we confirm the webpage is accessible. Termination of an instance is followed by its automatic replacement, maintaining the desired three-instance state. 
 
 ![image](https://github.com/user-attachments/assets/08a11bf4-f721-4774-91ea-b25d903a1b29)

 ![image](https://github.com/user-attachments/assets/b7318ad0-4dea-440d-9a53-361ea510ffc8)
![image](https://github.com/user-attachments/assets/5526c32b-ce60-4341-a9d3-dddaa12009ed)

 ![image](https://github.com/user-attachments/assets/2393dee6-10b6-4a4d-be7a-536d8946d521)

 ![image](https://github.com/user-attachments/assets/93fbad62-c87b-4d72-963e-65f9599ad0ef)

 ![image](https://github.com/user-attachments/assets/b346beb3-f0a6-44d3-a3fc-b5abee85932b)

 ![image](https://github.com/user-attachments/assets/4a3a5357-d4fc-4902-a40e-4c8bb1e4f013)

 ![image](https://github.com/user-attachments/assets/f065a1fc-d707-478e-a8c4-29bfa8166339)

the webpage still runs on the other ec2 instance 
 ![image](https://github.com/user-attachments/assets/3f87fefd-a986-4d40-9daa-15ae69c9268c)

now will delete the autoscaling group and our instances will automatically be terminate.
 
 ![image](https://github.com/user-attachments/assets/50066338-21dd-4e7a-8e0c-9b074d1bed9d)
![image](https://github.com/user-attachments/assets/15ef28a8-3ad0-43a8-a6ec-cfefe0cf009c)


# CREATE AMI USING AMI LAUNCH INSTANCE
To generate an AMI, choose an instance, navigate to actions, and select "create image." Provide a name for the image, ensure "enable no reboot" is checked, then click "Create image." The AMI creation process completes successfully.

 ![image](https://github.com/user-attachments/assets/b2159bd9-9a32-43ef-b30e-69698f5e924c)

give name and description 

 ![image](https://github.com/user-attachments/assets/fe76b936-b80a-4c34-b94d-5574422f5358)

 ![image](https://github.com/user-attachments/assets/6ff76ca8-8f86-43ec-ada0-5c8c165d043f)

ami image has successfully been created.
 ![image](https://github.com/user-attachments/assets/9a1fa72f-c4f5-453a-9930-9a93d90ee80d)

will start with clicking "Launch instance" from the AMI menu. Provide a name and select "My AMIs" from the Application and OS Images section. Under "owned by me," locate the AMI that we previously created.

 ![image](https://github.com/user-attachments/assets/9c01d4ac-e750-4db3-a19f-8a6f43f510c5)

 ![image](https://github.com/user-attachments/assets/67bfbdc8-8055-4f87-a1c5-c05e07af24f9)
![image](https://github.com/user-attachments/assets/ab8f13df-0ca4-436c-8725-683ea0737894)
![image](https://github.com/user-attachments/assets/eb80f2d2-84ec-44e7-8262-65694eedd8eb)
![image](https://github.com/user-attachments/assets/5943200b-b19e-478d-a54a-d6032c799321)

 
 
 
In this scenario, the instance was generated using the AMI image, yet the httpd server wasn't automatically initiated, thus hindering the webpage display. To resolve this, connect to the instance and manually launch the httpd web server to enable webpage visibility.
 ![image](https://github.com/user-attachments/assets/f3ae4b3b-7949-478d-8883-41eea024af5d)

and we can access the webpage finally.
 
![image](https://github.com/user-attachments/assets/6d68d68e-9135-4e68-aa44-bfb03c9d648e)



