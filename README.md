# Serverless REST API using AWS Lambda and Amazon API Gateway

---

| &nbsp; | &nbsp; |
| --- | ----------- |
| **Objective** | - Create Serverless REST API using AWS Lambda and Amazon API Gateway <br>- Perform API CRUD operations without having to manage infrastructure with efficient code snippets known as ‘Functions’ in AWS lambda |
| **Approach** | - Setup a Lambda by creating function and testing the function <br>- API Integration of lambda function with Amazon API Gateway and test using Postman<br>- Add trigger for Lambda function |
| **Impact** | - Serverless REST API using AWS Lambda and Amazon API Gateway that is inherently scalable</br>- Increase operational efficiency of CRUD operations |
<br>

**Primary Technology:** AWS Lambda Service, Amazon API gateway, Postman
<br><br>


<br><br>
---

## 1. Creating and testing Lambda function

## 1.1 Creating Lambda function
On the aws console, search and select **Lambda** from the Services category
![1](https://user-images.githubusercontent.com/102405945/212030642-64ff7892-6d56-47ca-abf3-466494d23c08.png)

Click **Create a function** to create a Lambda function
![2](https://user-images.githubusercontent.com/102405945/212030685-41f29c25-44b0-4620-91b6-a5f4cec45c82.png)

Select **Author from scratch** and give the function a name
![3](https://user-images.githubusercontent.com/102405945/212030781-6186a480-387d-44d2-8d44-8fa04f6a9328.png)

Select Runtime as **Python 3.9** and **x86_64** Architecture. Select **Create a new role with basic Lambda permissions** as Excution role
![4](https://user-images.githubusercontent.com/102405945/212030934-5a646cd9-970a-4891-85ba-3ac1382d19d5.png)

Click **Create function**
![5](https://user-images.githubusercontent.com/102405945/212030960-2c592c9a-dba2-47ca-a9d3-470ed47b8698.png)

Click **Test** for testing Lambda function
![6](https://user-images.githubusercontent.com/102405945/212030979-f28863ad-498c-47ae-a26d-acdc09c6bb81.png)

Configure test event and click **Save**
![7](https://user-images.githubusercontent.com/102405945/212030998-13b64cc0-3b42-4cd6-a43f-c79980add545.png)
![8](https://user-images.githubusercontent.com/102405945/212031021-8a0b3ce2-cf6e-47e0-b144-26c0893a3555.png)

Click **Test**
![9](https://user-images.githubusercontent.com/102405945/212031060-67a58343-ec2a-4e83-a750-f74c24abe8d7.png)
![10](https://user-images.githubusercontent.com/102405945/212031078-5a32e9bd-bb82-4d4c-b389-9c1b38bfe6f1.png)


## 1.2 Calling API
Go to **JSON placeholder** to get sample API
![11](https://user-images.githubusercontent.com/102405945/212031105-42925487-a775-4409-89af-5f1836d54d5d.png)
![12](https://user-images.githubusercontent.com/102405945/212031116-a38be6eb-c1e8-43a5-96fc-4e59f7191157.png)

On aws console, create new file named **config.py** and add base-url in config.py file
![13](https://user-images.githubusercontent.com/102405945/212031144-12efc6e1-1474-42d1-82db-bc17fad1945b.png)
![14](https://user-images.githubusercontent.com/102405945/212031157-ceaaa10c-cb6f-4eb7-b888-15a480f3c69f.png)

Import config.py file and requests library in lambda_function. Finally, deploy the function by clicking **Deploy**
![16](https://user-images.githubusercontent.com/102405945/212031185-fdc85aba-dac1-47a8-ade3-329799dec9fd.png)

## 1.3 Creating Layers
Go to aws console and click on **Layers**. Click **Add a layer**. Finally, click **Create layer** to create a layer
![17](https://user-images.githubusercontent.com/102405945/212031218-e2589f4e-0240-4d78-8729-e4ad25e8d3bb.png)
![18](https://user-images.githubusercontent.com/102405945/212031234-87cc1474-7a5b-4361-b2e4-4934c5844001.png)
![19](https://user-images.githubusercontent.com/102405945/212031247-c63981e7-d46a-4ce4-9223-b0dfebfdc890.png)

Create a layer by configuring name, description.
![20](https://user-images.githubusercontent.com/102405945/212031267-21ad35b0-7c8c-4c00-a36d-35754f054358.png)

Enter the following commands to create a .zip file using terminal: <br>
**mkdir pypackages** <br>
**cd .\pypackages** <br>
**pwd** <br>
Copy the path <br>
**pip3 install requests -t <path>** <br>
**ls** <br>
![21](https://user-images.githubusercontent.com/102405945/212031296-07616afd-d489-4038-a1de-b16bf6ea299c.png)
![22](https://user-images.githubusercontent.com/102405945/212031307-cd8ab94e-88c1-4564-a9d6-f32d11b837ec.png)
![23](https://user-images.githubusercontent.com/102405945/212031315-1a366a74-15b6-461e-9cd7-933db8826e10.png)
![24](https://user-images.githubusercontent.com/102405945/212031322-8848e12f-1721-4baf-ac4a-c3a23797565b.png)
![25](https://user-images.githubusercontent.com/102405945/212031331-baae1f51-4252-48f8-abc9-aa92227c76bd.png)

Create .zip file
![26](https://user-images.githubusercontent.com/102405945/212031372-6a9490ba-25f3-464a-8725-98b4931713b3.png)
![27](https://user-images.githubusercontent.com/102405945/212031459-b6f685c8-b16b-4209-b306-8b2d52f21374.png)

Upload .zip file enter other details and click **Create**
![28](https://user-images.githubusercontent.com/102405945/212031479-84803054-e722-49b8-b2b8-bbefa874ace0.png)
![29](https://user-images.githubusercontent.com/102405945/212031488-4e50baf5-e93b-4c79-8ac1-00d0e66eab76.png)
![30](https://user-images.githubusercontent.com/102405945/212031501-dd0367dc-101c-4c02-82e1-9b606f15f82b.png)
