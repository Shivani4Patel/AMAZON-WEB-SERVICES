## AWS DynamoDB
DynamoDB: It's a fully managed NoSQL database service provided by AWS. It allows you to store and retrieve any amount of data and serves any level of request traffic. DynamoDB is known for its high performance and scalability.
Indexes in DynamoDB
Indexes help you efficiently query data by providing alternative ways to retrieve items from your tables. There are two main types of indexes in DynamoDB:
1.	Primary Index (Primary Key):
o	Primary Key: This is the main way to uniquely identify items in your DynamoDB table. It's like a unique identifier for each record. You define it when you create the table.
- Partition Key: A single attribute that uniquely identifies an item (like a unique ID).
- Composite Key: Combines a partition key and a sort key, allowing multiple items with the same 
  partition key but different sort keys.
2.	Secondary Indexes:
- These are additional ways to query your data, not tied to the primary key. They allow you to 
  query the table using different attributes.
- Global Secondary Index (GSI): Lets you query data based on non-primary key attributes. It can 
  have a different partition key and sort key than the primary index.
- Local Secondary Index (LSI): Allows querying using an alternative sort key but must use the 
  same partition key as the primary index. It is defined at table creation.
## Projections in DynamoDB
Projections determine which attributes are copied (or "projected") from the main table to the index. When you query an index, you're querying the projected attributes.
* Types of Projections:
o	Keys Only: Only the primary key attributes of the table and index are projected. This is the smallest and most efficient projection.
o	Include: Specifies additional non-key attributes to project.
o	All: Projects all of the table's attributes into the index. This can be less efficient because it duplicates the data, but it makes all attributes available for queries.

Primary Key: Your main way of identifying items in the table.
      Indexes: Alternative ways to look up items based on other attributes.
o	Global Secondary Index: Allows querying on non-primary key attributes.
o	Local Secondary Index: Uses the same partition key as the primary key but allows a different sort key.
     Projections: Determine which attributes from the table are available in the index.
By using indexes and projections, you can optimize how you query and access your data in DynamoDB, making your database operations faster and more efficient.
 
## DynamoDB practical 
first we create a table in dynamodb add an items
 
 ![image](https://github.com/user-attachments/assets/0e417a10-dba6-4c16-96d4-89f2f0389c76)
![image](https://github.com/user-attachments/assets/474d1045-0b56-4675-b6c5-4dbe70a1071a)

then we will create an index give the partition key and sort key and most important choose projections for all.and create an index.
 
![image](https://github.com/user-attachments/assets/8a67bf05-8a16-4552-b761-b11c7db3288d)
![image](https://github.com/user-attachments/assets/9c87b4fa-bb0c-4364-abae-a0a19c214f2b)
 ![image](https://github.com/user-attachments/assets/d24bf243-a36f-42c4-8c81-792f47b82e0b)

 
now we will go to query item and under that will filter that to firstname and we can see the filtered output.
 
![image](https://github.com/user-attachments/assets/59674437-3b4b-4dc8-871d-7e9628ec61f3)
![image](https://github.com/user-attachments/assets/509944bd-6acf-4cd6-9772-9e715d64dd12)
![image](https://github.com/user-attachments/assets/05556499-b247-4c4a-b6a6-a9a235b4a17b)

 
 


