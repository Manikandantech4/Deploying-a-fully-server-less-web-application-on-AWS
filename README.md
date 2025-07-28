# Deploying-a-fully-server-less-web-application-on-AWS
Developed and deployed a fully server less web application using Lambda for backend logic, API Gateway for HTTP request handling and DynamoDB for scalable NoSQL data storage.

Short workflow
1. Designed a serverless web application architecture using AWS services to eliminate the need for traditional server management.
2. Implemented backend logic using AWS Lambda, enabling event-driven, scalable, and cost-effective compute functions.
3. Used Amazon API Gateway to create and manage RESTful endpoints that securely trigger Lambda functions over HTTP.
4. Integrated Amazon DynamoDB to store and retrieve application data with low latency and high availability.
   
<img width="804" height="365" alt="Screenshot 2025-07-28 at 4 13 52 PM" src="https://github.com/user-attachments/assets/599786f0-00f2-40bd-8e07-a2e64d0ef0da" />

Tools:
1. Dynamodb - for backend database storage
2. lambda - acts as a web server
3. api gateway - acts as a frontend

Steps:
Create a IAM role for lambda to access dynamobd. Select LambdaBasicExecutionRole and DynamodbFullAccess. 

Create a lambda funciton: Go to lambda, set any function name, select runtime python latest version. Under change default execution role, select the created IAM role, then click create. Upload the functioncode zip file.

<img width="1154" height="609" alt="Screenshot 2025-07-28 at 6 59 56 PM" src="https://github.com/user-attachments/assets/4490d32a-0dff-4d7c-955b-304b8db3d603" />

Create dynamodb table. Go to dynamodb and create a table, set tablename as mentioned in function code table, set partition key as email, then click create table.

Configure API gateway: Go to API gateway, click REST api, click build. Set any name in api name, then click create api. Click create method, out method type is GET and select lambda proxy integration icon on and select the lambda function we created. Then create POST method sameway. Then click Deploy API, under it, select stage as New stage and set dev as stage name. You will get the invoke url.

<img width="1110" height="317" alt="Screenshot 2025-07-28 at 6 58 55 PM" src="https://github.com/user-attachments/assets/30143d2b-533d-4437-aef6-514d1641f2f3" />

By using that invoke url, we can populate the dynamodb table whenever user enter details in contact form.

<img width="528" height="547" alt="Screenshot 2025-07-28 at 6 57 10 PM" src="https://github.com/user-attachments/assets/c2f2e4fd-d662-4620-9575-35d653aad6ce" />

<img width="912" height="231" alt="Screenshot 2025-07-28 at 6 57 46 PM" src="https://github.com/user-attachments/assets/6e43df70-9651-48c1-8402-34efac905d5a" />

<img width="1125" height="580" alt="Screenshot 2025-07-28 at 6 58 20 PM" src="https://github.com/user-attachments/assets/daa7f760-294c-4460-921a-d0a72d43e78b" />
