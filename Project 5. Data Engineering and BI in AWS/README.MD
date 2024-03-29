<!-- PROJECT LOGO -->
<br />

<p align="center">
  <img src="./images/now.png" alt="Logo" width="600" height="600">
</p>


> AWS, RDS, MySQL, DBeaver, AWS Data Pipeline, AWS S3, AWS Quicksight
<!-- ABOUT THE PROJECT -->

# Data Engineering and Business Intelligence in AWS

## Project Description
This is full end project where we try to simulate real cloud migration scenario. We will migrate our transactional data from On-Premise to AWS using AWS RDS MySQL. We also need to get insights from our data to make business decisions. We will use AWS Data Pipeline to convert the OLTP data to OLAP data for analytical purposes. The AWS Data Pipeline will fetch data from our RDS and convert it to our desired schema and push it to AWS S3. Here we will use AWS S3 as Data Lake and the AWS Data Pipeline will run automatically in certain intervals to push incremental updates in the S3. We will integrate AWS Quicksight for our Business Intelligence needs which will fetch datasets from our S3 and produce dashboards to get business insights, reports and KPIs.

## Follow Along:

### Part 1: AWS RDS and DBeaver

Head over to the AWS Management Console and search "RDS" in services. Choose "Create Database" and from all the options of various SQL Engines, we will opt for MySQL. Make sure to choose "Free Tier" and proceed by keeping everything default :

![APT](./images/1.PNG)

In "Connectivity" have "Public Access":

![APT](./images/2.PNG)

After successfully creating the database:

![APT](./images/3.PNG)

Install a tool called DBeaver in our local machine. DBeaver is a SQL client software application and a database administration tool. For relational databases it uses the JDBC application programming interface to interact with databases via a JDBC driver. Assuming that we have completed the installation process, we will create a new database connection to our AWS RDS MySQL Instance:

![APT](./images/4.PNG)

![APT](./images/5.png)

![APT](./images/6.PNG)

We need to edit our security group in the VPC section that we used for the AWS RDS. We will add a new inbound rule which will allow our RDS Instance to be accessible remotely by our IP Address. Few Screenshots are attached to explain this procedure:

![APT](./images/7.PNG)

![APT](./images/8.PNG)

![APT](./images/9.PNG)

![APT](./images/10.PNG)

Now we will go back to AWS RDS. Select the instance that have initially created and copy the "Endpoint" detail:

![APT](./images/11.PNG)

Now come back to our DBeaver application, enter the endpoint and the RDS Database Credentials that we have used while creating it initially. Test out the connection and if it is successful then proceed further:

![APT](./images/12.PNG)

![APT](./images/13.PNG)

I have provided the SQL Script for creating the necessary database, tables and populating the tables. The Script can be found on this link [Click Me](https://github.com/PritomDas/Cloud-Computing-Projects/blob/main/Project%205.%20Data%20Engineering%20and%20BI%20in%20AWS/SQL%20Script%20for%20MySQL%20Database/full_db_dump.rar)

If the script was run successfully then we should get a database along with the following tables :

![APT](./images/15.PNG)

The schema of our database is like the following:

![APT](./images/16.PNG)

### Part 2: AWS S3 and AWS Data Pipeline

Go to AWS Management Console and search for S3 in services. We will create a bucket which will hold the transformed data from AWS Data Pipeline. The data stored in this bucket will be used by our AWS Quicksight to create reports and dashboards.

![APT](./images/32.PNG)

After successfully creating a S3 Bucket:

![APT](./images/33.PNG)


Now, let's move over to AWS Data Pipeline and create a Pipeline. The Pipeline will fetch data from our RDS MySQL Instance and transform it based on our provided script and after completing the transformation will load it to the S3 Bucket. The whole process will run in automated manner, which is pretty cool.

![APT](./images/34.PNG)

Enter the following details while creating the Data Pipeline:

![APT](./images/35.PNG)

After successful creation we will get a visual UI as a flow chart:

![APT](./images/36.PNG)

We will add the following custom query, where we join two tables and then discard unimportant columns from the two tables:

![APT](./images/37.PNG)

Give the database name that we have created in the DBeaver:

![APT](./images/38.PNG)

Run the Data Pipeline, the Data Pipeline automatically fires up an EC2 Instance and runs our query for transformation. The transformed data will get loaded in the S3 bucket that we have created:


![APT](./images/39.PNG)


![APT](./images/40.PNG)

### Part 3: AWS Quicksight 

Amazon QuickSight, a component of Amazon Web Services (AWS), is a cloud-based serverless business intelligence platform that allows users to create visualizations and dashboards. Amazon powers the QuickSight SPICE, a fast, parallel, in-memory calculation engine. We will integrate AWS Quicksight with our AWS S3 Bucket and produce reports and dashboard. Go to AWS Quicksight and then select "New Dataset":

![APT](./images/41.PNG)

Choose "S3" from the Data Sources Type:

![APT](./images/42.PNG)

We will need two more details to proceed further. We need "S3 Object URL" and a manifest file in JSON format. Go back to S3 and choose the required bucket. Fetch the "Object URL" from that Bucket:

![APT](./images/43.PNG)

For the manifest file, I have written a sample script for my configurations. Download the script file and change the details inside the script based on your configurations. The sample "manifest file" can be found on this link [Click Me](https://github.com/PritomDas/Cloud-Computing-Projects/blob/main/Project%205.%20Data%20Engineering%20and%20BI%20in%20AWS/AWS%20Quicksight%20Manifest%20File/manifest)

After getting both these details, we will proceed like the following:

![APT](./images/44.PNG)

We will import the dataset and visualize:

![APT](./images/45.PNG)


An AWS user can select the data fields to be analyzed and then either drag it onto the visual canvas or allow QuickSight to determine the appropriate visualization based on the selection using its AutoGraph feature. A user can create a dashboard, which includes visualizations, tables and other data displays. We have created a sample dashboard that shows a donut chart about sales in various states:

![APT](./images/46.PNG)

### Part 4: Future Scope

This project can be enhanced further by integrating AWS Redshift, AWS Glue and AWS Lambda services. In this project we import in one shot the complete historical data from On-Premise Database to AWS. Whenever new data is loaded in our S3 bucket we can trigger Lambda and use AWS Glue to load the data to AWS Redshift. The AWS Quicksight can be redirected to Redshift and we can create reports and dashboards.

![APT](./images/future.png)

<!-- CONTACT -->

## Contact

Pritom Das Radheshyam - [Portfolio Website](https://pritom.uwu.ai/)
[![LinkedIn][linkedin-shield]][linkedin-url]  





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/you-found-pritom
[product-screenshot]: images/screenshot.jpg

