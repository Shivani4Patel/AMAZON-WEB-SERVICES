This project involves building and deploying a simple yet functional web application using AWS services. The frontend, hosted on AWS Amplify, allows users to input numbers for mathematical calculations. The backend logic, written in Python and running on AWS Lambda, performs these calculations and stores the results in an AWS DynamoDB table. AWS API Gateway provides the public endpoint for the frontend to trigger the backend calculations. The project demonstrates the seamless integration of these services to create a scalable and maintainable web application, with detailed documentation and a cleanup guide included.
Workflow:
1.	Web Page Creation and Deployment:
o	Develop a simple HTML page with a form for user input.
o	Deploy this page using AWS Amplify.
2.	Lambda Function Development:
o	Write a Python function that takes two numbers as input, calculates the result, and saves it to DynamoDB.
o	Deploy this function using AWS Lambda.
3.	API Gateway Configuration:
o	Set up API Gateway to create a RESTful API endpoint that invokes the lambda function.
o	Enable CORS (Cross-Origin Resource Sharing) to allow the frontend to interact with the backend service.
4.	Database Integration:
o	Create a DynamoDB table to store the results.
o	Update the lambda function to write results to this table.
5.	Final Integration and Testing:
o	Update the frontend to make AJAX calls to the API Gateway endpoint.
o	Test the entire application to ensure all components are working seamlessly together.
6.	Cleanup:
o	Guide on how to delete all created resources to avoid unnecessary charges, ensuring best practices for resource management. 
AMPLIFY 
To get started with building and hosting your web application, we will use AWS Amplify. Amplify makes it easy to build, deploy, and host web applications, particularly if you’re a front-end developer.
Create and Host a Web Page:
•	Open your favorite text editor, such as Notepad++.
•	Create a simple HTML file named index.html:
Zip the HTML File:
•	Save and zip the index.html file:
Right-click the file -> Send to -> Compressed (zipped) folder.


![image](https://github.com/user-attachments/assets/918cfed4-7874-4c07-955d-e3abf814ba8f)

![image](https://github.com/user-attachments/assets/14902c77-6480-40ef-95d5-eeae87fa46a9)

Deploy Using Amplify:
•	Navigate to the AWS Management Console -> AWS Amplify.
•	Click "Get Started" under the "Deploy" section.
•	Select "Host web app" and continue without a Git provider.
•	Name your app, e.g., "math app" and environment".
•	Drag and drop your zipped file into the deployment area.
•	Wait for the deployment to complete and note the provided URL for your web page.


![image](https://github.com/user-attachments/assets/2c926ba1-3b1a-436c-bf7d-0fb5b694c84a)
![image](https://github.com/user-attachments/assets/9e53cfea-ebd0-46a1-9837-faf7bf3abf39)
![image](https://github.com/user-attachments/assets/d01275a1-7c01-4303-8240-231bb8f5476d)

LAMBDA 
AWS Lambda lets you run code without provisioning or managing servers. You can set up functions that are triggered by events, such as changes in data, system state, or user actions.
Create a Lambda Function:
•	Navigate to the AWS Management Console -> AWS Lambda.
•	Click "Create function".
•	Select "Author from scratch".
•	Function name: power-of-math-function.
•	Runtime: Python latest version
  Add the Lambda Code:
•	
Test the Lambda Function:
•	Click "Deploy" to save the function.
•	Click "Test", create a new test event with the following JSON

![image](https://github.com/user-attachments/assets/ed132c02-cab1-47a6-86b9-f88e3625380c)
![image](https://github.com/user-attachments/assets/cb5e2443-fa5e-4939-a75f-d9e542ad18cd)
![image](https://github.com/user-attachments/assets/405076e1-b7ca-4e56-be97-3b6e9936fbc8)
![image](https://github.com/user-attachments/assets/c8afeda6-6341-4ab9-b245-1fcdebe3a3d9)
![image](https://github.com/user-attachments/assets/7701fadf-6085-4417-84c7-f271329c3303)
![image](https://github.com/user-attachments/assets/efd4028f-b7c1-47f5-b597-cfef290cb52b)

API
API Gateway
[Introduction to API Gateway]
AWS API Gateway allows you to create, publish, maintain, monitor, and secure APIs at any scale. It provides a simple way to expose your Lambda functions to the internet.
[Step-by-Step Guide for API Gateway]
1.	Create an API:
o	Navigate to the AWS Management Console -> Amazon API Gateway.
o	Click "Create API" and select "HTTP API".
o	Click "Build".
2.	Set Up Routes:
o	Click "Add integration" and choose "Lambda Function".
o	Select your Lambda function (power-of-math-function) and click "Create".
o	Under Routes, click "Add route".
o	Method: POST.
o	Click "Attach integration" and select your Lambda function.
3.	Deploy the API:
o	Click "Deploy" and create a new stage (e.g., dev).
o	Copy the provided API URL for use in your web application.

![image](https://github.com/user-attachments/assets/0bfe0473-9cd0-49e3-b336-42aa9172e653)
![image](https://github.com/user-attachments/assets/8acd0a65-8f0d-4148-a4a9-7392995b1f08)
![image](https://github.com/user-attachments/assets/b25488f3-eb7c-44f5-8aa3-fe0457c894a3)
![image](https://github.com/user-attachments/assets/fc95fb3d-4caf-4c51-8079-13d46fa9a11f)
![image](https://github.com/user-attachments/assets/8a24d2ae-1be9-4c0d-8e77-770590f223c0)
![image](https://github.com/user-attachments/assets/7f51ff4a-50f3-4043-918d-68ff40b7ea2c)
![image](https://github.com/user-attachments/assets/fb1563f4-7a67-46db-986d-a125b5b8678b)
![image](https://github.com/user-attachments/assets/9f5f0115-ca8d-4de4-abb8-d513663cbb93)
![image](https://github.com/user-attachments/assets/b81ee0bb-1645-44bc-a728-a65236bf0e4e)
![image](https://github.com/user-attachments/assets/14f348ce-ec8f-4d93-a245-11fd941b135a)
![image](https://github.com/user-attachments/assets/c8eff1ed-6e99-479b-861a-e2da615f7032)
![image](https://github.com/user-attachments/assets/7f38e24a-0076-46fd-896f-228b362c431d)
![image](https://github.com/user-attachments/assets/f2d8f6ca-404c-4e2c-a66d-a3d6565dc400)
![image](https://github.com/user-attachments/assets/3b06c8d6-b34e-4cde-94a5-4416f608c0a6)
![image](https://github.com/user-attachments/assets/bedc226c-cd14-4d35-be63-e0e87bdc9e4c)
AMAZON DYNAMODB
Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It’s great for storing results of calculations or any other data.
[Step-by-Step Guide for DynamoDB]
1.	Create a DynamoDB Table:
o	Navigate to the AWS Management Console -> Amazon DynamoDB.
o	Click "Create table".
o	Table name: power-of-math-results.
o	Partition key: id (String).
2.	Update Lambda to Use DynamoDB:
o	Modify your Lambda function to store the result in DynamoDB:
![image](https://github.com/user-attachments/assets/4b35d8a7-24fb-4d81-a9f5-0bbf0630168e)
![image](https://github.com/user-attachments/assets/53715ba4-daf1-4b8f-8975-5be5991d764c)
![image](https://github.com/user-attachments/assets/5789af7b-7305-4d6d-bb14-2efaa5291868)
![image](https://github.com/user-attachments/assets/d658a60d-05b9-4cdd-ac97-ca7904ae6819)
![image](https://github.com/user-attachments/assets/be232fee-f5ef-4c7a-b883-6273179718be)
![image](https://github.com/user-attachments/assets/50af2815-2bac-4a9e-8a37-de8c6859d1a9)
IAM 
AWS Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. You need to grant your Lambda function permissions to write to DynamoDB.
[Step-by-Step Guide for IAM]
1.	Attach a Policy to the Lambda Execution Role:
o	Navigate to the AWS Management Console -> AWS Lambda.
o	Select your Lambda function -> Configuration tab -> Permissions.
o	Click the Role name to open the IAM console.
o	Click "Add permissions" -> "Attach policies".
o	Click "Create inline policy".
o	Switch to the "JSON" tab and paste the following policy
2.	•  Replace the Resource value with your actual DynamoDB table ARN.
3.	•  Review and create the policy.
![image](https://github.com/user-attachments/assets/8fb3e791-1f22-4802-baeb-595f8f73af52)
![image](https://github.com/user-attachments/assets/04458200-02ec-4d63-b09a-abd0f780c576)
![image](https://github.com/user-attachments/assets/29974739-9ee3-4018-a4c2-5ccb2965e214)
![image](https://github.com/user-attachments/assets/7afebec6-6ebd-4d0f-916b-a0614b0b3928)
![image](https://github.com/user-attachments/assets/98f98f1c-b519-4fbe-9af9-8e99affce9ea)
![image](https://github.com/user-attachments/assets/17328a33-7a24-4da4-b265-115082b76777)
![image](https://github.com/user-attachments/assets/d8586c47-409f-408d-9bff-bcb8dffe3ad7)
![image](https://github.com/user-attachments/assets/8c0bc3e6-497f-4485-87e5-e6d437885236)
UPDATE DEPLOYMENT 
Update index.html to Call API Gateway:
•	Open index.html in your text editor and update the script
•	Replace YOUR_API_GATEWAY_URL with the URL from API Gateway.
 Zip and Redeploy the Updated HTML File:
•	Zip the updated index.html file.
•	Navigate back to AWS Amplify in the AWS Management Console.
•	Click "Deploy" and drag the updated zip file to redeploy.
•	Wait for deployment to complete and verify your changes.

![image](https://github.com/user-attachments/assets/4e068130-bb69-4974-aceb-e1e5dbc19d81)
![image](https://github.com/user-attachments/assets/6cbe48e1-8ca0-460e-b6e2-798771665533)
You have now successfully built and deployed an end-to-end web application using AWS services including Amplify, Lambda, API Gateway, DynamoDB, and IAM. Make sure to clean up your resources to avoid any unnecessary charges by deleting the Amplify app, DynamoDB table, Lambda function, and API Gateway
![image](https://github.com/user-attachments/assets/4cee7d90-670c-46e6-afed-d1c3319fd65b)
![image](https://github.com/user-attachments/assets/f41ea01e-f80b-40f0-b1b8-b8f190e46d9d)
![image](https://github.com/user-attachments/assets/c504a331-29cb-484c-9811-87cb4e252029)
![image](https://github.com/user-attachments/assets/5033bc4e-c7ff-4cf9-926f-6b4040d68730)
![image](https://github.com/user-attachments/assets/3a530c20-bf70-47b1-a5cc-89b32e3792ea)


The goal of this project is to build and deploy a simple yet fully functional web application using various AWS services. The application will perform mathematical calculations and save the results to a database, demonstrating the integration of multiple AWS components to create a cohesive, scalable solution.
Project Components:
1.	Frontend:
o	AWS Amplify: Used to host and deploy the web application's frontend. This service simplifies the process of building and hosting web applications by providing an easy-to-use platform for deployment.
o	HTML/CSS: The user interface is built using HTML for structure and CSS for styling. The interface includes a simple form where users can input two numbers to calculate the power of the base number to the exponent.
2.	Backend:
o	AWS Lambda: This service runs the backend code in response to HTTP requests via API Gateway. The lambda function performs the mathematical calculation and returns the result.
o	Python: The backend logic is written in Python, leveraging the math library to perform exponentiation.
3.	API Integration:
o	AWS API Gateway: This service provides a public endpoint for the frontend to invoke the lambda function. It handles the HTTP POST requests from the web application and triggers the lambda function to execute.
4.	Database:
o	AWS DynamoDB: A NoSQL database is used to store the results of the mathematical calculations along with a timestamp. This demonstrates how to persist data in a database for future retrieval or analysis.
5.	Security and Permissions:
o	IAM Roles and Policies: Proper permissions are set up using AWS IAM to ensure that the lambda function has the necessary access to write data to the DynamoDB table. This includes creating and attaching policies to the lambda execution role.
Deliverables:
•	A fully functional web application hosted on AWS Amplify.
•	Backend logic deployed using AWS Lambda.
•	An API endpoint created using AWS API Gateway.
•	Data persistence implemented with AWS DynamoDB.
•	Comprehensive documentation detailing the setup and integration of each component.
•	A cleanup guide to help manage and delete AWS resources post-project.
This project not only showcases the use of AWS services to build a web application but also serves as a practical guide to integrating these services to create scalable and maintainable solutions.





















