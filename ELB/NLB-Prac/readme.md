## Network load balancer 
An AWS Network Load Balancer (NLB) distributes incoming traffic to multiple servers to ensure your application stays available and can handle high loads.
* It provides:
	- High Performance: Handles millions of requests per second with low latency.
	- Automatic Scaling: Adjusts to traffic increases or decreases automatically.
	- Health Checks: Routes traffic only to healthy servers.
	- Static IP: Offers a fixed IP address for your application.
	- Protocol Support: Works with both TCP and UDP protocols.
to start with we will create two ec2 instances named she and jai and will add basic html webpage in both of the instances.
 
 ![image](https://github.com/user-attachments/assets/a66d3af4-170f-4886-8c29-46ac9ecc98ed)
![image](https://github.com/user-attachments/assets/868a19ad-e733-47cc-9cd0-c9f0e24f697a)
![image](https://github.com/user-attachments/assets/582f6012-3fa4-4601-857f-865b78c3edb0)

 ![image](https://github.com/user-attachments/assets/91f8cb5b-e158-472f-b3f0-5b06ecaedc89)
![image](https://github.com/user-attachments/assets/ca0e27d2-c8ad-4c97-a97c-228d7a591e6a)

 
 
so we have created two instances 
now will access then by copying public ip of both instances.
 ![image](https://github.com/user-attachments/assets/ead57a7f-3d77-4500-a76f-be72bf35fa40)
![image](https://github.com/user-attachments/assets/870bb03b-ad7a-4ef6-b5ec-7bb4f98d66ca)

 
now we will be creating application load balancer so will create application LB this time 
 ![image](https://github.com/user-attachments/assets/144d74ba-c7f5-45fd-a01c-545b64b34ac3)

will give name and select both insatnces as target and 
 ![image](https://github.com/user-attachments/assets/5445ffdc-7c0b-4367-a5a5-9053d26df491)

will create target group and will add both instances to that target group and create target groups.
 ![image](https://github.com/user-attachments/assets/c5393f3a-34c4-471f-9ac7-f028198f5c7e)

 
will come back and select the target group we have just created and under health check give path and create load balancer.
 
 ![image](https://github.com/user-attachments/assets/92f787a0-e99b-4e8a-9ebd-7fb08cdc63fa)

![image](https://github.com/user-attachments/assets/4e7b8852-9ce0-4e93-b6a8-55ec2e363dae)
![image](https://github.com/user-attachments/assets/03c17245-7768-4ba1-8355-cd96ef7c1e7b)
![image](https://github.com/user-attachments/assets/44b53459-cc0b-4964-84ed-a05c19191b64)


 
and when the load balancer status is active will copy the public DNS and paste it to new tab 
 ![image](https://github.com/user-attachments/assets/56188928-677b-4a8c-a129-4f6f08e559df)

as you can see we can access the webpage 
 ![image](https://github.com/user-attachments/assets/393cc738-d347-4419-8cdd-561bdab136aa)

now we will stop one one instance and then come back and refresh the page it will show us the second instance’s webpage 
 
 ![image](https://github.com/user-attachments/assets/88910fe3-8131-4c9a-abcf-a72ebdf417bc)

![image](https://github.com/user-attachments/assets/d4058bc3-405b-4166-8184-1b3cc1ea2924)
![image](https://github.com/user-attachments/assets/ad3d99d6-8785-45a3-a356-41d51dcf13b9)

 

what is the difference between aws network load balancer and application load balancer ?
AWS Network Load Balancer (NLB) is great for handling high-speed, low-latency traffic like real-time applications and games. It works at a basic level, focusing on distributing connections based on IP addresses without looking into the details of the data.

AWS Application Load Balancer (ALB) is perfect for web applications that need to manage HTTP and HTTPS traffic. It can make decisions based on the content of the traffic, like URLs and HTTP headers, making it ideal for directing traffic to different services within your app based on the request details.

In short:

NLB is for fast, simple traffic routing (like real-time applications).
ALB is for intelligent, content-based routing (like web applications).




