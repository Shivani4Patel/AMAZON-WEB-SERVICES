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

