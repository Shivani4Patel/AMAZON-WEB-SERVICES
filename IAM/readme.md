**IDENTITY AND ACCESS MANAGMENT** 

•	Identity Management: IAM helps you manage who can access your AWS resources. Just like you have usernames and passwords for different accounts, IAM gives each person or system trying to access your AWS stuff a unique identity.
•	Access Control: Once you have identities set up, IAM lets you control what each identity can and can't do. You can decide which AWS services someone can use, what actions they can perform within those services, and even which specific resources they can access.
•	Security: IAM helps keep your AWS account safe and secure. By setting up permissions correctly, you can make sure that only the right people have access to your sensitive data or can make changes to your infrastructure.
 ![image](https://github.com/user-attachments/assets/91f1f0a7-0ea2-49a9-ba3c-df524b14d6f8)


So, think of IAM as the tool that lets you manage who can do what in your AWS account, helping you keep everything organized, secure, and under control.
 
CREATE IAM USER 
navigate to use page and click on add user and give user name, password and click on next 
 ![image](https://github.com/user-attachments/assets/f9e96204-efec-4921-b4b5-526337950a96)
![image](https://github.com/user-attachments/assets/b7fa2ea4-775b-4a8d-be55-77755756c846)

 
will attach policies directly and select the permission we want to give this user , I chose ec2 full access for now . 
 
 ![image](https://github.com/user-attachments/assets/112da3ec-dd46-4513-8179-c62356af6d3a)
 ![image](https://github.com/user-attachments/assets/95079d25-f46e-48c8-8a69-9e64eb8baf2c)


I have download the file and created user.
 ![image](https://github.com/user-attachments/assets/c07bc4a5-0835-4fe8-b894-f28550ffb689)

 
CREATING MFA 
Users have access to your account and can possibly change configurations or delete resources in your AWS account so that  You can protect your Root Accounts and IAM users
will now select that user and under security we have MFa > assign Mfa device 
 ![image](https://github.com/user-attachments/assets/ce481e15-c230-4403-b1c1-fa876b73cbb2)

give the name of device and the MFA device here I have choose app , 
 
 ![image](https://github.com/user-attachments/assets/08a68070-c2bb-481e-8674-50f551b58b1e)
 ![image](https://github.com/user-attachments/assets/7a5e1aae-089f-4476-be46-f676c8857786)


it will show the qr code will open our app (I choose Microsoft authenticator )and give two codes 
	 
 

![image](https://github.com/user-attachments/assets/f319397d-52e0-4101-87bc-7d0fb6bfb9c8)

![image](https://github.com/user-attachments/assets/f64f9253-d850-4e99-9538-c2143c32779c)
![image](https://github.com/user-attachments/assets/3ebe7f8d-9ed4-4574-939b-6103b7383d32)
![image](https://github.com/user-attachments/assets/741804ee-ef9e-46eb-b62d-71476bd54cb7)
![image](https://github.com/user-attachments/assets/eec0ce22-7d22-441b-acb8-5282b10ce1ce)


and you have successfully assigned mfa.
 ![image](https://github.com/user-attachments/assets/317b4844-2063-4301-9627-d8916c10f751)

 
LOGIN USING IAM USER
will login using the iam user will give the account id and password along with MFA.
 
 ![image](https://github.com/user-attachments/assets/85aff021-ce4d-4753-99a0-74b9a680dfb6)

 ![image](https://github.com/user-attachments/assets/4482a19b-7528-422a-a412-50059a285764)
![image](https://github.com/user-attachments/assets/0c5d2e9a-2cc9-49be-b1d7-74d109c42bee)
![image](https://github.com/user-attachments/assets/a4f21495-b282-4f7a-8269-1008700c2818)

 

as we have previously gave this user permissions for accessing ec2 only so here I tried creating s3 bucket and when I hit on create bucket it shows me the access denied .
 ![image](https://github.com/user-attachments/assets/eaec1676-4fd3-40e4-9a1f-982afddd7ab9)

 
AWS CLI (ACCESS KEY GENRATION ):
here first we have selected users>access key> create access key >use case here is CLI so I chose CLI
 ![image](https://github.com/user-attachments/assets/2ec4c9dd-e1f8-4a24-b62d-8581d431764c)
![image](https://github.com/user-attachments/assets/207771f9-9119-4fcd-b0a3-98907fdf1010)
![image](https://github.com/user-attachments/assets/37c8380b-0380-4127-9a70-7be38033613c) 
download the file and click on done .
 ![image](https://github.com/user-attachments/assets/a2e64805-7897-4b29-a860-1d4215e36d06)
![image](https://github.com/user-attachments/assets/cc134852-ad36-4819-9b88-87e342e5b82f)

 
AWS CLI
A tool that enables you to interact with AWS services using commands in your command-line shell, it is alternative to aws management console.
• Direct access to the public APIs of AWS services and You can develop scripts to manage your resources

so here ,  In order to install CLI on all os will use the aws cli documentation and choose the os here I have used windws so I chose windowsn and copy the installation command from there .

 ![image](https://github.com/user-attachments/assets/bc4caa4e-c080-42ee-b080-6e548d5b89cf)

I go to my windows command prompt and paste the url copied from the documentation in order to check the version will click on aws version which can show the version which has installed 
 ![image](https://github.com/user-attachments/assets/bd5988a0-cfc0-42aa-b3ab-eb798ca30cce)

 ![image](https://github.com/user-attachments/assets/2531961e-9ebf-42b8-a6e0-ae0e1c141bd0)
![image](https://github.com/user-attachments/assets/1ef18468-9b83-4abc-82ec-d9a77f05d4d0)
![image](https://github.com/user-attachments/assets/823bda7f-f82a-40b1-86ee-ba6eaf687d96)
![image](https://github.com/user-attachments/assets/adf99129-5478-43c1-8aa4-29ed1612331f)

 
 
will configure aws cli using aws config and it asks for access key and region name 
then I gave permission to iam user >administrator so when I write s3 ls it shows nothing cz there is no s3 bucket has been created.
 ![image](https://github.com/user-attachments/assets/9cc2e509-8551-418f-8f81-df62a5bd007e)

 
CREATE ROLE
Some AWS service will need to perform actions on your behalf To do so, we will assign
permissions to AWS services with IAM Roles.
now will create a role for that will select entity I chose service then use case I am making role here for ec2 instance so I chose ec2 .
 ![image](https://github.com/user-attachments/assets/6b8d3d9d-998e-4768-a1ea-739e04b9319a)
![image](https://github.com/user-attachments/assets/d4664029-d399-4722-9d8a-b25c60a75ede)

 
click next and then add permission so will add administrator access to this ec2 role.
 ![image](https://github.com/user-attachments/assets/3ac79a86-ca8d-4a61-b370-d0de6b970b68)

give the name to the role 
 ![image](https://github.com/user-attachments/assets/a3427ebd-e304-4410-8d8c-e4aeaaa135c4)

so when we create an ec2 instance during that there is a section called advance details under that I have chose IAM instance profile and we can see from the dropdown the role we have created.
 ![image](https://github.com/user-attachments/assets/409d7874-1949-418c-9b49-f0479cc686be)

in instance details we can see the instance role details.
 ![image](https://github.com/user-attachments/assets/6fc19eaf-7be4-4186-9bf6-374e15527fcc)

 
USER GROUP 
go to IAM Dashboard in your AWS console. Choose user groups >under Access management > click on create group.

 ![image](https://github.com/user-attachments/assets/4dd19495-2f6b-4d78-9622-a8e0e5b4c0b1)
![image](https://github.com/user-attachments/assets/01e49051-47ce-4173-9e3a-45efd20cddeb)
![image](https://github.com/user-attachments/assets/44742c37-ab62-4aa8-a853-b9500c194eda)
![image](https://github.com/user-attachments/assets/3d1c2365-8b92-4395-93fe-072df11b8dd7)

 
 
 


