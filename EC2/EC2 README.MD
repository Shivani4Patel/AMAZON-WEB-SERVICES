# **Basics of EC2 instance and Launching EC2 Instance**

---

## **Table of Contents**
- [Introduction](#introduction)
- [Launching EC2 Instances](#launching-ec2-instances)
  - [Using Windows AMI](#using-windows-ami)
  - [Using Ubuntu AMI](#using-ubuntu-ami)
  - [Using Linux AMI](#using-linux-ami)
  - [Using PuTTY](#using-putty)
- [Exploring AWS EC2 Dashboard](#exploring-aws-ec2-dashboard)
- [AWS Protocols](#aws-protocols)
-  EC2 Instance Setup and Security Group Configuration

---

## **Introduction**

This guide provides detailed steps to launch EC2 instances using various Amazon Machine Images (AMIs), such as **Windows**, **Ubuntu**, and **Linux**. It also includes instructions for connecting instances using **Git Bash**, **PuTTY**, and **RDP**, along with a walkthrough of the AWS EC2 dashboard and supported communication protocols.

---

## **Launching EC2 Instances**

### **EC2 Instance Launch Using Windows AMI**

1. **Access EC2 Service**:
   - Navigate to the AWS Management Console and search for **EC2**.
   - Click on **"Launch Instance"** to start creating a new instance.

2. **Configure Instance**:
   - Assign a name to the instance.
   - Choose **Windows Server** from the Amazon Machine Images (AMI).
   - Select an instance type (e.g., `t2.micro` for free-tier eligibility).
   - Generate or select a key pair for secure access.
   - Configure security groups to allow **RDP (Remote Desktop Protocol)** access.

3. **Launch and Connect**:
   - Click **"Launch Instance"** and ensure the RDP inbound rule is correctly configured.
   - Generate the administrator password from the AWS Console and use an **RDP client** to connect by entering the public DNS and administrator credentials.
  
## **Using Windows AMI**

1. Navigate to the AWS console and search for the EC2 service. The homepage should look like this:  
   ![EC2 Homepage](https://github.com/user-attachments/assets/a620307b-59d4-4bb5-9374-c2c376707fa6)

2. Click on **Launch Instance**, provide the name of the instance, and select the operating system (OS) you want. Here, **Windows** was chosen:  
   ![Windows AMI Selection](https://github.com/user-attachments/assets/20258dea-8c92-46c2-8250-223fca0969fb)

3. Choose the instance type and select the key pair:  
   ![Instance Type and Key Pair](https://github.com/user-attachments/assets/cbb896ce-4173-4c24-ba60-0ab43b68d6f1)

4. Configure the security group and enable **RDP traffic**:  
   ![RDP Traffic Configuration](https://github.com/user-attachments/assets/613a0854-2c7a-4106-8695-5eaf96d2bab9)

5. Launch the instance and double-check the **inbound rules** for RDP in the security group:  
   ![Security Group Inbound Rule](https://github.com/user-attachments/assets/493cd70a-7d9d-426d-bc6d-56b76fbd2a09)

6. Connect to the EC2 instance using **RDP Client**:
   - Generate the password:  
     ![Generate Password](https://github.com/user-attachments/assets/edf37582-8ea9-4ff7-bb48-ffd788624bd1)
   - The generated password appears as follows:  
     ![Generated Password](https://github.com/user-attachments/assets/7e4a4256-2166-4aee-92b2-600cdebed09f)

7. Use **Remote Desktop Connection** to paste the **Public DNS Address** and connect:  
   ![Remote Desktop Connection](https://github.com/user-attachments/assets/9b1fe7ed-a2e6-4335-bc3e-df4ae559e028)  
   ![RDP Instance Connection](https://github.com/user-attachments/assets/35cd9897-d242-4184-adb9-fca23308e209)

---

---

### **EC2 Instance Launch Using Ubuntu AMI**

1. **Select Ubuntu AMI**:
   - Follow the same steps as above but select **Ubuntu** as the AMI.

2. **Key Pair and Security Group**:
   - Generate or use an existing key pair.
   - Enable **SSH** traffic in the security group.

3. **Connect via Git Bash**:
   - Use the SSH command provided in the AWS Console under **"Connect"**.
   - Open Git Bash, paste the command, and hit Enter to establish the connection.
     

## Using Ubuntu AMI

1. Follow the same steps as above but choose **Ubuntu AMI**.
2. Copy the **SSH command** from the instance and paste it in Git Bash:  
   ![Ubuntu AMI Selection](https://github.com/user-attachments/assets/0b34aeb9-fb62-4683-9ba8-2381d1f9dc1e)

3. Launch the instance and configure the **SSH connection**:  
   ![SSH Connection](https://github.com/user-attachments/assets/6bcc3e24-67d6-4aa7-8fa0-b0a1414180b1)

---


##  EC2 Instance Launch Using Linux AMI

### Select Linux AMI:
- Choose **Linux AMI** from the AWS Management Console.

### Key Pair and Security Group:
- Create or use an existing **key pair**.
- Ensure the **security group** allows inbound SSH traffic (port 22).

### Connect via Git Bash:
- Use the **SSH command** provided in the AWS Console under "Connect".
- Open **Git Bash**, paste the command, and hit Enter to establish the connection.

![Linux AMI Selection](https://github.com/user-attachments/assets/4812e130-0513-4c37-a6d6-fbbbe621d4f6)  
![SSH Client](https://github.com/user-attachments/assets/1a5adbf7-8608-4fa3-97ed-2f365236a4fd)  
![Linux SSH Connection](https://github.com/user-attachments/assets/b534752b-808b-4fff-9477-a13289c2f6a5)

##  EC2 Instance Launch Using PuTTY

### Convert Key Pair:
- Use **PuTTYgen** to convert the **.pem** key pair to **.ppk** format.

### Key Pair and Security Group:
- Create or use an existing **key pair**.
- Ensure the **security group** allows inbound SSH traffic (port 22).

### Connect via PuTTY:
- Open **PuTTY**, enter the **Public IP Address** of the EC2 instance.
- Under SSH > Auth, upload the converted **.ppk** key.
- Click **Open** to establish the connection.

![PuTTYgen Key Conversion](https://github.com/user-attachments/assets/c503b4e1-f033-42c4-831e-ca396a33d65c)  
![PuTTY Connection](https://github.com/user-attachments/assets/400367af-5214-4174-be06-46e8a479cc7b)  
![PuTTY EC2 Connection](https://github.com/user-attachments/assets/17202524-92e4-4187-a8b4-06d8ca82faa4)


---

## **Exploring AWS EC2 Dashboard**

### **Instance Overview**
- View details such as **Instance ID**, **State**, **Public DNS**, **Security Group**, and more.

### **Monitoring Metrics**
- **CPU Utilization**: Analyze the percentage of CPU usage.
- **Disk I/O**: Monitor read/write operations.
- **Network Traffic**: Track data flow in and out of the instance.

- ## **Exploring AWS EC2 Dashboard**

- The dashboard provides various features for monitoring and managing your instance:  
  ![Dashboard](https://github.com/user-attachments/assets/5d009f83-3b0a-4718-901f-36a58eafc8e8)

### Key Features:
- **Security Tab**: View IAM roles and security group details.  
  ![Security Tab](https://github.com/user-attachments/assets/14513dfc-abfd-457f-8fcd-b684782c52c2)

- **CPU Utilization**: Monitor workload performance.  
  ![CPU Utilization](https://github.com/user-attachments/assets/e190635c-6db9-4f78-84b4-a754c525c41c)

- **Networking Tab**: Adjust and diagnose networking setups.  
  ![Networking Tab](https://github.com/user-attachments/assets/5412367c-2fc0-4bd5-87dd-34a69aeff300)

---


## **AWS Protocols**

### Device Communication Protocols in AWS IoT Core:
- **MQTT**: Lightweight protocol for small data transfers.
- **HTTPS**: Secure website connection for one-way data transfer.
- **TLS**: Encryption layer ensuring secure communication.

### AWS API Protocols:
- **ec2**: Manage EC2 services.
- **json/rest-json**: Communication for newer AWS services.
- **query/rest-xml**: Communication for older AWS services.

### Amazon Workspaces Protocols:
- **PCoIP**: High-quality graphics streaming.
- **WSP**: Optimized for low bandwidth usage.

---

# EC2 Instance Setup and Security Group Configuration

## Steps to Create a Security Group and Launch an EC2 Instance

### 1. **Creating a Security Group**

1. **Go to EC2 Service**:
   - In the EC2 dashboard, click on **Security Groups** under **Network & Security**.
   - Security groups created during instance setup will appear here.

   ![Security Groups](https://github.com/user-attachments/assets/1cc882dd-1af9-4e8a-a2a1-c75404014ffe)

2. **Create Security Group**:
   - Click on **Create Security Group**.
   - Provide the following basic details:
     - **Name**: `webserver`
     - **Description**: `Allow all HTTP traffic to access the webpage`.

   ![Create Security Group](https://github.com/user-attachments/assets/c53156b9-4895-4616-8650-17169b4a4779)

3. **Configure Inbound Rules**:
   - Add an **HTTP rule**:
     - **Type**: HTTP
     - **Source**: Anywhere (0.0.0.0/0)
   - Add an **SSH rule**:
     - **Type**: SSH
     - **Source**: Anywhere (0.0.0.0/0)

   ![Inbound Rules HTTP](https://github.com/user-attachments/assets/98184b41-338b-4054-9639-21411a6e5c02)
   ![Inbound Rules SSH](https://github.com/user-attachments/assets/bbed891e-59c0-4074-89fc-e8a65b99f774)

4. **Create Security Group**:
   - Click **Create Security Group**.
   - You will see the newly created security group with the applied rules.

   ![Security Group Created](https://github.com/user-attachments/assets/4731f906-1756-4fcf-8850-c7b37ae48740)
   ![Security Group Details](https://github.com/user-attachments/assets/b511fe2f-772f-446f-88ba-bd4406715ae6)

### 2. **Launching EC2 Instance with User Data**

1. **Create an EC2 Instance**:
   - In the EC2 dashboard, click on **Launch Instance**.
   - Choose an **AMI** (Amazon Machine Image), e.g., **Linux**.
   - Select the **Instance Type** suitable for your use case (e.g., T2.micro for testing).

   ![Choose AMI](https://github.com/user-attachments/assets/7de173d3-05cc-45e3-aad5-0f190174146a)
   ![Choose Instance Type](https://github.com/user-attachments/assets/3c91e5ec-8dd6-44c9-a227-1a714fb1fb9a)

2. **Network Settings**:
   - Under **Network Settings**, choose **Select an existing security group**.
   - Select the previously created **webserver** security group.

   ![Select Security Group](https://github.com/user-attachments/assets/607b6219-d13d-450b-a9e5-ed3592048f3f)

3. **Add User Data Script**:
   - Scroll down to **User Data** and provide a script to:
     - Update the package.
     - Set permissions.
     - Write simple HTML content for the webpage.

   Example script:
   ```bash
   #!/bin/bash
   sudo apt-get update -y
   sudo apt-get install -y apache2
   echo "Hello, World!" | sudo tee /var/www/html/index.html
   sudo systemctl restart apache2

![image](https://github.com/user-attachments/assets/42a31909-5ac2-4b03-9be3-7dc1c6e07073)

**Review and Launch:**

Check the Status Check and make sure it's passed.
Select the instance and click Launch.
![image](https://github.com/user-attachments/assets/4e173d04-38c7-4cbe-abf2-62915bd68178)

**Access the Webpage:**

After the instance is running, copy the Public IP address of the EC2 instance.


![image](https://github.com/user-attachments/assets/ba3df689-2e25-43c1-92a6-25e4a5f5f29a)
Paste it in the browser’s address bar to access the simple webpage.

![image](https://github.com/user-attachments/assets/2dc808cf-87f5-467d-b3b5-da4c781c6fff)



## Instance Types
 1  **General Purpose Instances (T-Series):**
- T2: Store extra CPU power when not in use, suitable for small to medium-sized websites and basic development.
- T3: Faster overall, better handling of sudden CPU spikes.
2. **Compute Optimized Instances (C-Series):**
  - Best for compute-heavy tasks such as powerful web servers or complex scientific calculations.

3. **Memory Optimized Instances (R-Series):**
    - Suitable for large databases and applications requiring lots of memory.

4. **Storage Optimized Instances (I-Series):**
- Perfect for storage-intensive apps that require fast SSD storage for large files and databases.


