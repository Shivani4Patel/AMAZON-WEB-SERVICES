## S3 WITH CLOUDFRONT
WE WILL FIRST CREATE AN S3 BUCKET AND GIVE IT A NAME AND UPLOAD ONE INDEX.HTML FILE  
![image](https://github.com/user-attachments/assets/717a3f2f-c557-43de-b19e-acef536b3de5)
![image](https://github.com/user-attachments/assets/01b64bef-669f-4e2c-9c0b-d939f4841aa0)
![image](https://github.com/user-attachments/assets/ddfc2dd4-3ada-4cc5-8895-0c004a012508)

WE WILL NOW GO TO CLOUDFRONT CREAT EA DISTRIBUTION AND CHOOSE ORIGIN AS S3.  

![image](https://github.com/user-attachments/assets/6891796f-d954-4482-9056-02942702a4c9)

![image](https://github.com/user-attachments/assets/1af5af0c-8b70-48bd-8f58-49c4c9eba895)

CREATE A ORIGIN ACCESS CONTROL AND CREATE A DISTRIBUTION 

 ![image](https://github.com/user-attachments/assets/e084b27c-590a-4cd3-8346-63956887cba2)

AS YOU CAN SEE IT SHOWS THE S3 BUCKT POLICY TO BE COPIED IN ORDER TO ACCESS THE DATA FROM S3 SO WE WILL COPY THAT AND THEN PASTE IT TO THE S3 BUCKET POLICY. 

![image](https://github.com/user-attachments/assets/eebf40f0-f732-4026-acf7-53fd05febb5f)

![image](https://github.com/user-attachments/assets/571fb5dd-a70d-499d-ad4b-7047fb6d14aa)

![image](https://github.com/user-attachments/assets/1bb15a00-7a7f-4f1f-87ef-f489306ddbf3)

![image](https://github.com/user-attachments/assets/81cd416e-1637-46ea-94e1-7b9ddd618f48)

when we copy and paste the dns name we can able to access our webpage. 

 ![image](https://github.com/user-attachments/assets/4771adeb-1c32-4671-977e-1b35fd557bc5)

GLOBAL ACCELERATOR 
AWS Global Accelerator is a service that helps improve the performance and availability of your applications by routing user traffic through AWS's global network. Here’s a simple breakdown of what it does:
Key Features of AWS Global Accelerator:
1.	Performance Improvement:
o	Faster Access: Routes traffic through the closest AWS edge location, reducing latency and speeding up response times for users worldwide.
2.	High Availability:
o	Reliable: Uses multiple paths for routing traffic, so if one path fails, it automatically reroutes to another, ensuring your application stays online.
3.	Traffic Management:
o	Global Load Balancing: Distributes traffic across multiple AWS regions, balancing the load to keep your application running smoothly even under high demand.
4.	DDoS Protection:
o	Security: Provides built-in protection against Distributed Denial of Service (DDoS) attacks, helping to keep your application safe.
How It Works:
1.	Accelerators:
o	You create an accelerator which gives you two static IP addresses that act as fixed entry points for your application traffic.
2.	Routing:
o	When users access your application, their traffic is routed through the AWS global network to the closest edge location, then directed to your application servers in the optimal region.
3.	Automatic Failover:
o	If an issue is detected in one path, traffic is automatically redirected to another healthy path, maintaining continuous availability.
Benefits:
•	Improved Speed: Users get faster access to your application, no matter where they are located.
•	Increased Reliability: High availability and automatic failover mean your application is more reliable and resilient.
•	Enhanced Security: Built-in protection against DDoS attacks.
Use Cases:
•	Web Applications: Speed up websites and web services for a global audience.
•	Gaming: Provide low-latency connections for online games.
•	Content Delivery: Improve performance for media streaming and large file downloads.
In essence, AWS Global Accelerator makes your applications faster, more reliable, and more secure by leveraging the global infrastructure of AWS
Hands-On

 ![image](https://github.com/user-attachments/assets/e035433a-5b72-4c9e-8e5f-cd120e26e911)

we first create a ec2 instance with autoscaling and loadbalncer with simple html webpage and now we will go to the global accelerator and create it 
 

 ![image](https://github.com/user-attachments/assets/e92ac404-c80b-446a-8d50-2fd4e80ba0dd)

![image](https://github.com/user-attachments/assets/986d98c9-a6c2-4538-b8c0-e896b8f9f8b8)

![image](https://github.com/user-attachments/assets/f6d1b772-682b-4075-b290-145e29d70400)


 we will give the name and type and then add port number as 80 with tcp   

 ![image](https://github.com/user-attachments/assets/3fe9d35e-8eed-4fa6-94a1-ef6053f49115)

![image](https://github.com/user-attachments/assets/d3eefe84-30fc-4bc9-8ac8-da6b4899ee1e)

choose endpoint origin and endpoint type as a loadbalancer.   

![image](https://github.com/user-attachments/assets/0b83965b-1a09-4917-bb32-a6441f9ca04e)

![image](https://github.com/user-attachments/assets/236e631f-02c1-4b13-86c9-f14befd15a85)

![image](https://github.com/user-attachments/assets/7cb7ef2d-dfa8-493f-a423-17cfba401614)

create an accelerator and paste the dns name and you can able to see the webpage.  

![image](https://github.com/user-attachments/assets/b5f3426b-617e-426b-8f58-937f14b7fbda)

![image](https://github.com/user-attachments/assets/a38e757c-a993-4091-9c97-e23bc7323026)

