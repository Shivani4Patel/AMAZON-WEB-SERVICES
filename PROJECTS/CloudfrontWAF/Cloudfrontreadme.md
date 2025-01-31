# Deploying a Web App in NGINX Server using CloudFront, WAF, Load Balancer, and Auto Scaling Group

## Overview
This deployment creates a robust, scalable infrastructure ensuring optimal performance, security, and user experience. NGINX provides secure, high-performance web serving. AWS CloudFront reduces latency for fast global content delivery, and AWS WAF enhances security. The Elastic Load Balancer ensures high availability by distributing traffic and routing away from unhealthy instances. The Auto Scaling group adjusts server instances based on traffic, ensuring efficient load handling and cost-effectiveness. This results in a seamless, high-performing, and secure user experience, even under heavy traffic.

---

## EC2 Instance Launch

1. Go to the AWS Management Console.
2. Navigate to EC2 and click on "Launch Instance."
3. Choose an Amazon Machine Image (AMI), preferably Amazon Linux 2 or Ubuntu.
4. Select an instance type, such as t2.micro.
5. Configure instance details, add storage, and configure security groups.
6. Add a key pair for SSH access.
7. In the instance configuration, under "Advanced Details," add a user data script to install NGINX and deploy the static webpage.
8. Named the instance "instance one" and chose Ubuntu as the operating system.

![EC2 Instance Configuration](https://github.com/user-attachments/assets/ca878cfb-30c6-4c67-85aa-8c362bbb42c3)
![Instance Selection](https://github.com/user-attachments/assets/21c20845-df45-453d-bb7b-713f1d999668)
![Security Groups](https://github.com/user-attachments/assets/f8266da8-0f63-4d75-8383-1b4990d2dc27)

---

## SCP Tool
Using an SCP tool like WinSCP to transfer static webpage files to the EC2 instance if updates are needed. The key pair created during the instance launch is used for SSH authentication.

![SCP Authentication](https://github.com/user-attachments/assets/76fcb550-977c-4acb-8437-3ae8b68fd667)
![File Transfer](https://github.com/user-attachments/assets/d49d5f9a-a71d-46a4-aaea-cb711eb3b401)
![SCP Setup](https://github.com/user-attachments/assets/469fc6f6-4317-4663-a3fe-f17a25d5c721)
![image](https://github.com/user-attachments/assets/98b4736f-0705-4640-b18e-f34ab895d1fa)


---

## Target Group

1. Navigate to the "Target Groups" section under the EC2 dashboard.
2. Create a target group, selecting "Instances" as the target type and specifying protocol and port (HTTP, port 80).
3. Register your EC2 instance with this target group.
4. Set up health check path to `/var/www/html/index.html`.

![Target Group Setup](https://github.com/user-attachments/assets/933540d8-ca44-4e68-8032-32197df084b1)
![Health Check Path](https://github.com/user-attachments/assets/253e1dbc-f3bd-4fdf-bf80-ebe19e3b7638)

---

## Load Balancer

1. Navigate to the "Load Balancers" section under the EC2 dashboard.
2. Create an Application Load Balancer (ALB).
3. Select "Internet-facing" for the scheme.
4. Choose the appropriate VPC and subnets.
5. Configure security groups.
6. Add listeners (HTTP, port 80) and associate them with the target group created earlier.

![Load Balancer Configuration](https://github.com/user-attachments/assets/19155ccb-6f8a-43ab-8c3b-7b1e91a0acd7)
![Load Balancer IP Type](https://github.com/user-attachments/assets/7b8682f8-d50e-46ef-8619-1747f644b439)
![VPC & Subnets](https://github.com/user-attachments/assets/cc101fc4-8f17-411a-9283-edfa86a57c37)
![Load Balancer DNS](https://github.com/user-attachments/assets/01d102c0-a4b0-4363-b83e-53a7eac5e32b)
![image](https://github.com/user-attachments/assets/e6a508ef-21ce-4c49-8f6f-bd59682fa7f4)
![image](https://github.com/user-attachments/assets/5ea4806e-ebd2-43b8-a2cf-cb6863f772db)


---

## Auto Scaling Group

1. Create an AMI from the configured instance.
2. Navigate to "Auto Scaling Groups" in the EC2 dashboard.
3. Create a new Auto Scaling Group and attach the created AMI.
4. Configure scaling policies to ensure optimal performance.

![AMI Creation](https://github.com/user-attachments/assets/e44783ea-78f7-4dff-a747-48b3664eb0d4)
![Auto Scaling Setup](https://github.com/user-attachments/assets/8ea7bc93-8bf2-4f3a-bb55-5e691db17107)

---

## CloudFront

1. Go to AWS CloudFront and create a distribution with ELB as the origin.
2. Enable security settings and legacy configurations.

![CloudFront Setup](https://github.com/user-attachments/assets/876b8fef-a63a-42aa-8c8c-717247a927ff)
![CloudFront Configuration](https://github.com/user-attachments/assets/71470773-8da5-4c2e-86fa-b2a03be8d45a)
![image](https://github.com/user-attachments/assets/23a87d8d-4faa-4037-9a42-1bf17497893f)
![image](https://github.com/user-attachments/assets/548ff974-2bab-4d50-9ae8-3f77e2e0aa98)
![image](https://github.com/user-attachments/assets/460a887f-1971-4b3c-b01c-a8e34307498e)
![image](https://github.com/user-attachments/assets/b07422b8-2947-474e-b772-e39550992c91)
![image](https://github.com/user-attachments/assets/e522b67e-0f77-44e1-93b5-a37b7dfe5cf0)


---

## WAF (Web Application Firewall)

1. Navigate to WAF and Shield in AWS.
2. Create a rule to block specific IP addresses.
3. Associate the rule with the Load Balancer.

![WAF Rule Setup](https://github.com/user-attachments/assets/836f5896-e8b5-4d90-bde2-255873b77573)
![WAF Integration](https://github.com/user-attachments/assets/7f800d7d-8e69-4f41-af8c-debf96255e24)
![image](https://github.com/user-attachments/assets/e330135d-95d7-412a-ab46-ea68839fbacc)
In this process, we configure a Web Application Firewall (WAF) to enhance security by blocking specific IP addresses. First, we create a custom rule to block the IP address of a device, such as a personal computer. This rule is implemented in the WAF settings. Next, we verify that the WAF is integrated with the Load Balancer (LB) under the "Integration" section, ensuring that the traffic passing through the LB is protected by the WAF.

Once the rule is added, the specified IP address will be blocked from accessing the website, providing an additional layer of security. If needed, the rule can be disassociated, allowing access again. This feature is useful for blocking malicious or unauthorized IP addresses, improving the overall security of your application and infrastructure.


![image](https://github.com/user-attachments/assets/cefd1689-8c0c-4bf3-af14-3ee7a7b130b4)
![image](https://github.com/user-attachments/assets/9976dfc7-13bb-43e8-86d7-72a5158fcb81)
![image](https://github.com/user-attachments/assets/3dadd6a5-c9d1-4848-af0c-77846dc1ca51)
![image](https://github.com/user-attachments/assets/c134db66-e104-48a1-99fe-22a7d0445369)
![image](https://github.com/user-attachments/assets/ea2bee59-cc2d-4b8f-849e-375c5e59a7e7)
![image](https://github.com/user-attachments/assets/d53dcb6e-fea2-4fd0-91bc-4b5cdcbfb0c4)
![image](https://github.com/user-attachments/assets/e3077323-e218-4f63-8f71-52fa7f2c5126)

---

## Benefits

1. **Enhanced Performance and Availability**
   - Load balancing evenly distributes traffic.
   - Auto scaling optimizes resource utilization.

2. **Improved Security**
   - AWS WAF protects against web exploits.
   - CloudFront mitigates DDoS attacks.

3. **Enhanced User Experience**
   - CloudFront caches content for reduced latency.

4. **Scalability and Flexibility**
   - Auto Scaling Groups adjust instances based on demand.

5. **Cost Efficiency**
   - Pay-as-you-go model ensures cost-effectiveness.

6. **Reliability and Redundancy**
   - Multi-AZ deployment ensures high availability.

---

## Conclusion
By leveraging AWS services such as EC2, Auto Scaling, Load Balancer, CloudFront, and WAF, we achieve a highly secure, scalable, and cost-effective web application deployment.

---
