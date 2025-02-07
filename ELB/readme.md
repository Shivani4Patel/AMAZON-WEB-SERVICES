## Elastic Load Balancer
An Elastic Load Balancer (ELB) is a service that automatically distributes incoming traffic across multiple servers. Think of it as a traffic cop that directs cars (internet requests) to different lanes (servers) to ensure no single lane gets too crowded, helping maintain fast and reliable performance of websites or applications. It adjusts to traffic changes and ensures high availability by rerouting traffic if any server fails.
There are three main types of Elastic Load Balancers provided by AWS:

1. Application Load Balancer (ALB):
   - Best suited for HTTP and HTTPS traffic.
   - Operates at the application layer (Layer 7 of the OSI model).
   - Supports advanced routing based on content, allowing for features like host-based or path-based routing, and handling WebSocket connections.

2. Network Load Balancer (NLB):
   - Ideal for handling TCP, UDP, and TLS traffic.
   - Operates at the transport layer (Layer 4 of the OSI model).
   - Designed for high-performance, low-latency, and high-throughput applications.
   - Capable of handling millions of requests per second while maintaining ultra-low latencies.

3. Classic Load Balancer (CLB):
   - Supports both HTTP/HTTPS and TCP traffic.
   - Operates at both the application layer (Layer 7) and the transport layer (Layer 4), but with fewer features than ALB and NLB.
   - Suitable for simple load balancing of traffic across multiple EC2 instances.
   - Considered legacy; AWS recommends using ALB or NLB for new applications.


EC2 instance 
first we will create a ec2 instance for give name to instance and choose AMI os here I chose ubuntu 
 ![image](https://github.com/user-attachments/assets/d6015894-31c1-4239-8f7f-cbf8bff5c135)
![image](https://github.com/user-attachments/assets/66568291-85f2-42b6-a546-303300f60e30)

then will create / choose existing security group 
 ![image](https://github.com/user-attachments/assets/eea486ef-3375-481a-9845-0f51ec3a2041)

then will give userdata by giving simple html script .
 ![image](https://github.com/user-attachments/assets/7e9e8031-da05-4f44-9fc4-326e6d047af5)

will make the other two instances as well I gave name to two and changed userdata.
 ![image](https://github.com/user-attachments/assets/c3216385-d59e-4fe5-abca-818869ceefb3)

 
will create third instance and will give user data to this instance as well 
 ![image](https://github.com/user-attachments/assets/b22f0d88-db86-4631-8bb1-fc64ce3646a9)

 ![image](https://github.com/user-attachments/assets/689615ce-2689-4d59-8d79-eb4b312e4667)

three instances are in running state 
 ![image](https://github.com/user-attachments/assets/94708a66-562f-45ae-b6d3-c4ed2273c079)

now will create target groups will create three target groups 
will start off eith giving target name here I gave TG, TGO,TGT and then chose instance as target target type and http port 80 b
 
* target group 

	 ![image](https://github.com/user-attachments/assets/d55ebe09-c140-4303-b99d-327f4c34a6f7)

 ![image](https://github.com/user-attachments/assets/60788df9-62bc-4ce6-b617-f21dea31cbae)

in health check will give path for each TG will give different path  based on the user data 
 ![image](https://github.com/user-attachments/assets/f9c93054-7034-4fcf-a574-49f423d3b5af)

will choose instances so for first target will choose first instance and create target group .
 
 ![image](https://github.com/user-attachments/assets/d1db21ab-7b7c-4c02-9b45-8312de6e5e0d)
![image](https://github.com/user-attachments/assets/d81e6b5a-5eb2-438a-9904-f982bb070c2d)

for the second target group will choose second instance  and create target group 
 ![image](https://github.com/user-attachments/assets/fa8f302d-bc81-46ed-ac99-7baf3896106d)

will repeat the process for third target group as well .
 ![image](https://github.com/user-attachments/assets/33d49748-8de0-4a17-b01f-5b0d7bfbd527)
![image](https://github.com/user-attachments/assets/a07f2ad6-3686-48e9-adb0-8f44a5f32d45)

 
will create three target groups.
 ![image](https://github.com/user-attachments/assets/396f26a9-3f68-4525-957b-3f2ef8299d4c)

load balancer 
load balancer types based on the requirements of the applications we will choose the load balancer types here we will be choosing the application load balancer 

 ![image](https://github.com/user-attachments/assets/957a7224-2b4e-4758-8401-ceb97d93ca6f)

now will give the basic configurations such as load balancer name and scheme ip address type 
 ![image](https://github.com/user-attachments/assets/8fe39d1c-f0ed-443c-b8f5-40323912281c)

in mappings will choose minimum of two mappings min two availability zones  
 ![image](https://github.com/user-attachments/assets/ca5621c9-0ec1-4014-bde4-d7b69d0a0687)

will select the security groups will choose the same while we use while created instance.
 ![image](https://github.com/user-attachments/assets/f25d17a1-8eb5-472c-8971-7bc28098fdc2)

listerns and routing will choose first tg .
 ![image](https://github.com/user-attachments/assets/bcf91388-88df-495c-9b8c-381ea1959bbf)

and will create load balancer and once it shows status active will copy and paste dns name and it will show the default it works “and when we refresh it it shows first instance html  
 ![image](https://github.com/user-attachments/assets/41d8b8b4-d30d-46ae-a51f-832d9c32e814)
![image](https://github.com/user-attachments/assets/b862f0a4-7c30-4275-b853-44e5d70d47a2)
![image](https://github.com/user-attachments/assets/fdbeb0b1-f29e-4628-b8af-6a9de3b42509)

 
 
* path based routing : 
under listener sections there is default http 80 lister will add rule will create three rules 
for each instance will add rule and condition and actions for condition will choose path based routing and will give path and for actions will choose target group and then when we access the load balancer and refresh it it will show all three instances html pages.
 
 ![image](https://github.com/user-attachments/assets/a199cb4b-ee30-4e56-81fc-acd9040f324d)

 
 ![image](https://github.com/user-attachments/assets/24a9f60d-879a-466b-a626-36533f45eda4)

![image](https://github.com/user-attachments/assets/72adb1e2-1b77-4940-bf18-6940ff66b476)

 ![image](https://github.com/user-attachments/assets/28f83368-e192-4079-a841-b99fa763620e)
![image](https://github.com/user-attachments/assets/b7c1d15d-4d75-4f81-a027-5fea9c1a5902)
![image](https://github.com/user-attachments/assets/ebd612f2-5381-4bc4-a636-863c1e51b68e)
![image](https://github.com/user-attachments/assets/eddb9d93-1995-492a-9c0a-99238d97ded2)

 
 




