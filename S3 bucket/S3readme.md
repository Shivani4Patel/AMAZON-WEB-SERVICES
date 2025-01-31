# Amazon S3: Scalable Cloud Storage

## Key Features and Concepts

### 1. Buckets and Object Storage
- **Bucket**: A container for storing objects (files, data).
- **Object Storage**: Data is stored as objects within these buckets.

![Object Storage Service](https://github.com/user-attachments/assets/8b5ec203-8c78-49bb-8946-e872d03bc2d6)

### 2. Replication
- Ensures data is duplicated across different locations for redundancy and availability.

### 3. Storage Classes
- Different tiers optimized for cost and access needs:
  - **Frequent access**
  - **Infrequent access**
  - **Archive storage**

### 4. Static Website Hosting
- Host static websites directly from an S3 bucket.

### 5. Access Control List (ACL)
- Manages permissions and can transfer object ownership.

### 6. Versioning
- Maintains multiple versions of an object.
- Helps in recovering deleted objects.

### 7. Encryption
- **Client-Side Encryption**: Data is encrypted before uploading.
- **In-Flight Encryption**: Secures data during transmission using HTTPS.
- **Server-Side Encryption**: AWS encrypts stored data.

### 8. Events
- Triggers actions (like notifications) based on bucket events (e.g., object creation, deletion).

### 9. Bucket Policies
- Define rules for access and management of bucket contents.

### 10. Global Uniqueness of Bucket Names
- Bucket names must be unique across all AWS regions.

### 11. Write-Once-Read-Many (WORM) with Object Lock
- Prevents objects from being modified or deleted for a set retention period.

### 12. Amazon Resource Name (ARN)
- Unique identifier for AWS resources.

### 13. Resource-Based Policies
- Define actions that can be performed on a resource and by whom.

## Properties
- Each object and bucket in S3 comes with properties like:
  - **Storage class**
  - **Metadata**
  - **Permissions**

## Use Cases
- Websites
- Mobile apps
- Enterprise applications
- Backup and restore
- Archiving data
- IoT devices
- Big data analytics

---

# Creating an S3 Bucket, Uploading an Object, and Generating a Policy

### **1. Creating an S3 Bucket**
- Navigate to the **S3 Console**.
- Click **Create Bucket**.

![Create S3 Bucket](https://github.com/user-attachments/assets/a667f956-fa49-4ca9-9963-fdd69c997660)

- Choose a globally unique bucket name.

![Bucket Name](https://github.com/user-attachments/assets/7f5352d3-1a18-484a-9f35-c0c6afcacf6c)

- Configure permissions:
  - Disable ACLs.

![Disable ACLs](https://github.com/user-attachments/assets/b1b7da5e-5015-4cc5-b144-23c9510746da)

  - Uncheck "Block public access" (if making public).

![Block Public Access](https://github.com/user-attachments/assets/5b259d03-29e9-4be9-9266-f48bc70b1d50)

- Enable **Bucket Versioning** (optional).

![Enable Versioning](https://github.com/user-attachments/assets/28a2b551-b04d-4e65-b347-f8e8769ea5f6)

- Click **Create Bucket**.

### **2. Uploading an Object**
- Open the created **S3 Bucket**.
- Click **Upload** > **Add Files** > **Select the file**.

![Upload Object](https://github.com/user-attachments/assets/b38c379c-8d6b-414e-a1d8-b428ac212bf3)

- Click **Upload**.

### **3. Granting Public Access via Bucket Policy**
- Go to **Bucket Permissions**.

![Bucket Permissions](https://github.com/user-attachments/assets/63c61492-2481-4932-95a9-fb47154b0417)

- Click **Edit Bucket Policy**.
- Use the **Policy Generator**:

![Policy Generator](https://github.com/user-attachments/assets/abf53242-db74-4c17-9982-dcb43a3353ba)

  - Select **S3 Bucket Policy**.
  - Set **Principal** to `*` (allows all users).
  - Copy and paste the **Object ARN**.
  - Generate and apply the policy.

![Generate Policy](https://github.com/user-attachments/assets/368a1572-0488-4869-aadf-7b7ea3241011)

### **4. Accessing the Object**
- Use the **Object URL** to check access.
- If "Access Denied" appears, verify the **Bucket Policy** and permissions.
- Once configured correctly, the object will be accessible via the public URL.

![Object Accessible](https://github.com/user-attachments/assets/75834ac0-ca7d-456f-a39f-22d56e1647b5)

---



# AWS S3 Storage Classes and Lifecycle Policies

## Storage Classes

1. **Standard:**
   - High availability and durability
   - Ideal for frequently accessed data

2. **Standard-IA (Infrequent Access):**
   - Lower cost than Standard
   - Higher retrieval cost
   - Good for data accessed less frequently
   - Example transition: Move from Standard to Standard-IA after 30 days

3. **Intelligent-Tiering:**
   - Automatically shifts data between frequent and infrequent access tiers
   - No specific transition days; managed automatically based on access patterns

4. **One Zone-IA:**
   - Lower cost than Standard-IA
   - Stores data in a single Availability Zone
   - Suitable for recreatable infrequently accessed data
   - Example transition: Move from Standard to One Zone-IA after 30 days

5. **Glacier:**
   - Very low-cost storage for data archiving
   - Retrieval times vary from minutes to hours
   - Best for rarely accessed data

## Cross-Origin Resource Sharing (CORS)
- **Cross-Origin Resource Sharing (CORS):**
  - Allows resources from one region to be accessible from another
  - Configure CORS rules on S3 buckets to enable cross-origin requests

## S3 Event Notifications
- **S3 EventBridge:**
  - Enables the triggering of automated responses to S3 events (e.g., object created, deleted)
  - Useful for automating workflows and integrating with other AWS services

## CloudFront and Content Delivery Network (CDN)
- **CloudFront:**
  - A CDN service to deliver data, videos, applications, and APIs to customers globally with low latency
  - Uses edge locations to cache content closer to users
  - Example: Set up CloudFront distribution with an S3 bucket as the origin

- **CloudFront Distribution:**
  - Configuring CloudFront to distribute content
  - Enhances performance and reduces latency

## Scalability and High Availability
- **Scalability:**
  - AWS services, including S3 and CloudFront, scale automatically to handle increased load

- **High Availability:**
  - Multi-AZ deployments ensure high availability and data durability

## Additional Concepts
- **Alias Records:**
  - Use alias records in Route 53 to point to CloudFront distributions for domain names

- **Replication:**
  - S3 Cross-Region Replication (CRR) can replicate objects across different AWS regions to enhance data availability and disaster recovery

## Example Use Cases
- **Lifecycle Policies:**
  - Use lifecycle policies to automatically transition objects between storage classes (e.g., from Standard to Glacier after a set period)

- **CDN with CloudFront:**
  - Improve content delivery speed globally by using CloudFront to cache and serve content from edge locations

---

# S3 Static Website Hosting

Here, we demonstrate how to host a static website in an S3 bucket.

### Steps:
1. **Create a bucket** and attach the necessary policies.
2. **Upload the necessary objects** into the bucket.
3. **Enable static website hosting:**
   - Under the **Properties** section, select **Static Website Hosting**.
   - Click on **Edit**, enable the option, and specify the website path (e.g., `index.html`).

### Screenshots:
![Create Bucket](https://github.com/user-attachments/assets/9e4ed555-11ff-4f75-8a75-222dc6dbf281)
![Upload Objects](https://github.com/user-attachments/assets/d46781c9-9d33-44ee-ba64-6054c60e13a9)
![Attach Policy](https://github.com/user-attachments/assets/b61ae216-282d-4446-b5d9-c07e9fcd2c91)
![Enable Static Website](https://github.com/user-attachments/assets/fb9c9a7d-09bf-4a54-9327-9d4e3940afae)
![Static Website Path](https://github.com/user-attachments/assets/3f541b6d-d692-4aa6-9d96-c7ddad0b8ccc)
![Website Link](https://github.com/user-attachments/assets/106adb90-af21-416a-a7ed-3328683f43a5)
![Access Website](https://github.com/user-attachments/assets/16cc35f6-b356-49f6-bfc2-562839ce2e4d)
![Final Webpage](https://github.com/user-attachments/assets/b42e29da-44a1-4979-b686-2f63805d12b7)

Once completed, you will receive a website link, which can be copied and pasted into a browser to access your webpage.

---

# CloudFront Distribution as S3 Origin

### Steps:
1. **Go to AWS Services** and select **CloudFront Distributions**.
2. **Select an Origin** (S3 Bucket).
3. **Enable public access** and choose HTTP & HTTPS.
4. **Disable security protections** (optional for testing).
5. **Complete distribution creation**.
6. **Copy the DNS name** and paste it into a browser to access the webpage via CloudFront.

### Screenshots:
![Select CloudFront](https://github.com/user-attachments/assets/8c2cdcb1-33c5-461e-a6b8-c740c594086b)
![Choose Origin](https://github.com/user-attachments/assets/f951938b-d7d0-4324-8c5c-2eac62d2957f)
![Configure Public Access](https://github.com/user-attachments/assets/1963cf18-3456-4d3a-bda2-0159b3920151)
![HTTP & HTTPS](https://github.com/user-attachments/assets/3255f00a-b7c5-4754-9f84-b6dac59486e3)
![Disable Security](https://github.com/user-attachments/assets/6d4405cf-f30b-42bf-91d1-4014d4da0a1e)
![CloudFront Created](https://github.com/user-attachments/assets/b6e492ea-1d67-4d8e-8b3e-10e36463342a)
![CloudFront Dashboard](https://github.com/user-attachments/assets/3486749e-63cf-49a1-bcef-7b3b58eb3c2f)
![CloudFront Access](https://github.com/user-attachments/assets/58437f1f-380e-4d12-bbe0-79b378b90603)
![Final CloudFront Page](https://github.com/user-attachments/assets/7f6dc918-9675-48d9-bd77-be12bfa8a7a3)
![Index.html Access](https://github.com/user-attachments/assets/2465ac3b-e12a-4e54-9abb-5ef46da1b1b0)

Using **CloudFront**, the webpage can be accessed globally with improved speed and reliability.

