**Relational database service**
AWS RDS, which stands for Amazon Web Services Relational Database Service, is a cloud-based service that makes it easy to set up, operate, and scale a relational database. Here’s a simple way to understand it:
1.	Managed Databases: AWS RDS handles routine database tasks like backups, software patching, monitoring, and hardware provisioning, so you don't have to.
2.	Multiple Database Engines: You can choose from several popular database engines like MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server, or Amazon's own Aurora.
3.	Scalability: It allows you to easily scale your database's compute and storage resources to meet your needs.
4.	High Availability: AWS RDS provides automated backups, snapshots, and replication across multiple availability zones for high availability and durability.
5.	Cost-Effective: You pay only for what you use, with options for on-demand or reserved pricing, helping to manage costs effectively.
In short, AWS RDS takes care of the heavy lifting involved in managing a relational database, so you can focus more on your application and less on database administration.
  ![image](https://github.com/user-attachments/assets/4fb289ad-ae71-4c13-a8ff-1487071a604b)

create an rds instance and link it to MySQL workbench 
we will go to services> rds and create database and give the name of the database and choose the engine as sql  
choose the version and template as free tier
 ![image](https://github.com/user-attachments/assets/27aa58ab-aefe-4dab-b68e-0578d7cfdb38)
![image](https://github.com/user-attachments/assets/f8af60bb-1fcf-48d9-9353-c31ad28481ee)

 ![image](https://github.com/user-attachments/assets/bec1c3f3-443c-4daf-b073-408532e936de)

give the name and the credentials as username and password and choose the default vpc with subnet and public access option enabled 
 ![image](https://github.com/user-attachments/assets/37a866db-94d0-4ff4-ad37-f4b8f0ccdda5)
![image](https://github.com/user-attachments/assets/56f5b2cd-fac2-4b34-8844-c0cdc232604e)

 
then create a database this takes 5-10 minutes to see as available 
 ![image](https://github.com/user-attachments/assets/b25fa374-1e23-44d6-b57c-f2d5afacefe5)
![image](https://github.com/user-attachments/assets/963df2a0-e3c8-40d5-9421-130dab446877)

 
we will go to sg and edit the inbound rules add the tcp as 3306 for  accessing the sql and now go to the sql workspace and connect to the dsatabse using the endpoint and username and password 
 ![image](https://github.com/user-attachments/assets/d0509c70-002e-42c8-8eb8-8823ea3d54a4)
![image](https://github.com/user-attachments/assets/22c0e10d-051d-4e06-8b3f-eb08d02d5b0e)

 
we will generate one wuery and create one dabase and give it a name as shedb 
 ![image](https://github.com/user-attachments/assets/ad86784c-57a0-441a-bd59-8e5370a7c989)

same way we can create a table as well as shown below .
![image](https://github.com/user-attachments/assets/3e970508-860b-4ced-aab1-22530abd2306)

 


