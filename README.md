# Serverless REST API using AWS Lambda and Amazon API Gateway

---

| &nbsp; | &nbsp; |
| --- | ----------- |
| **Objective** | - Create Serverless REST API using AWS Lambda and Amazon API Gateway <br>- Perform API CRUD operations without having to manage infrastructure with efficient code snippets known as ‘Functions’ in AWS lambda |
| **Approach** | - Setup a Lambda by creating function and testing the function <br>- API Integration of lambda function with Amazon API Gateway and test using Postman<br>- Add trigger for Lambda function |
| **Impact** | - Successfully created a serverless REST API using AWS Lambda and Amazon API Gateway that is inherently scalable</br>- Operational efficiency of CRUD operations is increased effectively |
<br>

**Primary Technology:** AWS Lambda Service, Amazon API gateway, Postman
<br><br>


<br><br>
---
![Design Thinking Whiteboard in Yellow Blue Basic Style (1)](https://user-images.githubusercontent.com/102405945/212118230-1dda627e-357d-49e1-820e-35ff6cc504f2.png)
<br> <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/102405945/212111980-8f463fe9-3155-4aba-a04a-b81b96abd778.png" />
</p>

---

## 1. Creating and testing Lambda function

### 1.1 Creating Lambda function
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


### 1.2 Calling API
Go to **JSON placeholder** to get sample API
![11](https://user-images.githubusercontent.com/102405945/212031105-42925487-a775-4409-89af-5f1836d54d5d.png)
![12](https://user-images.githubusercontent.com/102405945/212031116-a38be6eb-c1e8-43a5-96fc-4e59f7191157.png)

On aws console, create new file named **config.py** and add base-url in config.py file
![13](https://user-images.githubusercontent.com/102405945/212031144-12efc6e1-1474-42d1-82db-bc17fad1945b.png)
![14](https://user-images.githubusercontent.com/102405945/212031157-ceaaa10c-cb6f-4eb7-b888-15a480f3c69f.png)

Import config.py file and requests library in lambda_function. Finally, deploy the function by clicking **Deploy**
![16](https://user-images.githubusercontent.com/102405945/212031185-fdc85aba-dac1-47a8-ade3-329799dec9fd.png)

### 1.3 Creating Layers
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


### 1.4 Add layer
Go to aws console, click on function name
![31](https://user-images.githubusercontent.com/102405945/212106140-58936aa7-5a1b-4167-8da1-73c643b6866d.png)

Click on **Layers**
![32](https://user-images.githubusercontent.com/102405945/212106186-1685546f-5de8-49cb-b332-9fbbe7378958.png)

Click **Add a layer**
![33](https://user-images.githubusercontent.com/102405945/212106227-f99032f4-5145-4c63-9bba-08adddd487b8.png)

Select **Custom layers** and choose the created layer. Click **Add**
![35](https://user-images.githubusercontent.com/102405945/212106336-a4193a82-de4a-473d-996b-c88966e68ecc.png)
![36](https://user-images.githubusercontent.com/102405945/212106350-d3b8a52a-b17c-4892-b286-d8c62510dc30.png)


### 1.5 Testing
Click on **Test** button
![37](https://user-images.githubusercontent.com/102405945/212106416-b805f59a-eca2-43f5-a70f-e43df9f3d5eb.png)
![38](https://user-images.githubusercontent.com/102405945/212106437-1dc49b73-cbc6-40fe-9ba3-6b5389454f14.png)



## 2. Integration of lambda function with Amazon API gateway

### 2.1 Creating Rest API
Go to aws console. Search and select **API Gateway** from the service category
![39](https://user-images.githubusercontent.com/102405945/212111149-c8d3ccc9-6a05-4cbc-85f4-4192c2e8693e.png)

Select **REST API** and click on **Build** button
![40](https://user-images.githubusercontent.com/102405945/212111169-104f2097-ea75-45d2-be6d-f1821cbec75d.png)
![41](https://user-images.githubusercontent.com/102405945/212111185-ef69446a-beec-4d82-95b2-13f04493f8c8.png)

Choose the protocol. Select **REST** as protocol. Select **New API** to create a new API and enter API name, description and Endpoint type. Click **Create API** to create API
![42](https://user-images.githubusercontent.com/102405945/212111221-7b4abf6e-ddf0-442a-ba8b-3626bba14ef9.png)
![43](https://user-images.githubusercontent.com/102405945/212111234-9d89d285-c6fd-4918-a1ed-2db75e96dac8.png)


### 2.2 Designing API

Click on **Actions** and select **Create Method** from the drop-down menu
![44](https://user-images.githubusercontent.com/102405945/212111275-6c8900f0-8e69-4b8a-80f2-4b7e350bbc56.png)

Select GET and setup GET. Select **Lambda Function** as Integration type and select Lambda function created earlier. Click **Save**
![45](https://user-images.githubusercontent.com/102405945/212111302-26002f14-2d92-43b9-b878-1d427a77eccc.png)
![46](https://user-images.githubusercontent.com/102405945/212111322-2555a151-67dc-4f21-b11c-f08228fc6e1d.png)


### 2.3 Testing API
click on **TEST**
![47](https://user-images.githubusercontent.com/102405945/212111344-46caf5f4-d6b7-429c-9caa-2a7dfab158b2.png)
![48](https://user-images.githubusercontent.com/102405945/212111358-f2bc3ed2-378a-41b1-80a7-14dbcf56de64.png)
![49](https://user-images.githubusercontent.com/102405945/212111378-9d7cf008-3dea-4119-8b84-de970faa6bc9.png)


### 2.4 Deploying API
Click on **Actions** and select **Enable CORS** from the drop-down menu
![50](https://user-images.githubusercontent.com/102405945/212111407-4fc4f663-173c-47a0-b676-e486ffb2a7bf.png)

Click on **Enable CORS and replace existing CORS headers** button
![51](https://user-images.githubusercontent.com/102405945/212111439-12a1f560-734b-4d91-abd5-a332200ae432.png)
![52](https://user-images.githubusercontent.com/102405945/212111457-2e1a9389-6d7b-43ba-8f19-26dd727a8388.png)
![53](https://user-images.githubusercontent.com/102405945/212111466-7b3da499-26fa-4be6-b808-825b88444d18.png)

Click on **Actions** and select **Deploy API** from the drop-down menu
![54](https://user-images.githubusercontent.com/102405945/212111501-014b305d-86b0-4f4c-bbed-053b4c81b9af.png)

Select Deployement stage as **New Stage** and click **Deploy**
![55](https://user-images.githubusercontent.com/102405945/212111540-ea053955-8780-4b9b-99c7-a8dc79bf2cb6.png)



## 3. Testing using Postman

Copy the Invoke URL
![56](https://user-images.githubusercontent.com/102405945/212111571-d92daafd-a274-4a81-88b4-1150b89a2805.png)

Paste the copied URL on Postman and select **GET**. Click **Send**
![57](https://user-images.githubusercontent.com/102405945/212111615-8fe53335-e170-47f0-9463-2576b83da2b1.png)



## 4. Adding Trigger in Lambda function

Go to aws console and click **Add trigger** button
![58](https://user-images.githubusercontent.com/102405945/212111675-5bc8d724-74ac-43b3-96ac-089fed4cedac.png)

Select **API Gateway** and select **Use existing API. Select security as **Open** and click **Add**
![59](https://user-images.githubusercontent.com/102405945/212111724-39e4fe4c-4e9a-401c-9632-4625529f2237.png)
![60](https://user-images.githubusercontent.com/102405945/212111739-b5688e18-1aea-4d72-a950-8fc11ecfe183.png)



## 5. Testing on Browser

Enter the URL on web browser
![61](https://user-images.githubusercontent.com/102405945/212111767-62eae4ec-0db6-4fbc-9ebd-595f6724e141.png)
