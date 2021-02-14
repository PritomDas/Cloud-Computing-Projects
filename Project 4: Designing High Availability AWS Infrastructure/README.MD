<!-- PROJECT LOGO -->
<br />

<p align="center">
  <img src="./images/1.PNG" alt="Logo" width="900" height="800">
</p>


> AWS, ELB, ASG, Launch Configuration
<!-- ABOUT THE PROJECT -->

# Designing High Availability AWS Infrastructure

## Project Description
This is a medium difficulty level project. Based on the reference architecture diagram, we will design high available system. We will create AMI for our desired EC2 Instances which will be bootstrapped for starting an Apache Webserver. We will create load balancers, launch configurations and auto scaling groups. We will run 2 EC2 instances in different public subnets and it gets auto provisioned when old EC2 Instances are down.

## Follow Along:

### Part 1: Create AMI from an EC2 Instance

Head over to EC2 in services from AWS Management Console. Then "Launch Instance" :

![APT](./images/2.PNG)

We will create free tier eligible instance :

![APT](./images/3.PNG)

Since we are creating this project for practice, select "Free Tier" in templates:

![APT](./images/3.PNG)

Give desired credentials to create your own RDS instance:

![APT](./images/4.PNG)

Pay close attention to "Connectivity". Let's choose "Public Access" as "Yes". We will also create a new security group instead of the default security group.

![APT](./images/5.PNG)

Rest everything stay as deafault and then create the database:

![APT](./images/6.PNG)

After successful creation the database should be avaialble in the databases dashboard :

![APT](./images/7.PNG)

### Part 2: Download a Local SQL Client

We will download the MySQL Workbench in our local system if it is not installed already. [Click Here](https://dev.mysql.com/downloads/mysql/) to locate the installer. After successful installation, it should be available in your local system. Add a new connection by pressing the  "+" button :

![APT](./images/8.PNG)

Head over to the AWS Management Console again and "View Credential Detail" of the RDS Instance:

![APT](./images/9.PNG)

Enter the following detials as shown on the following pic which I have tried to map from the AWS RDS Credential Detail to the MySQL Workbench Connection :

![APT](./images/10.PNG)

Test the connection, if it is successful then it should look something like this:

![APT](./images/11.PNG)

The connection should also appear in the MySQL Workbench dashboard from now onwards:

![APT](./images/12.PNG)

Double click the connection, whatever query is written here will be reflected in the AWS RDS portal:

![APT](./images/13.PNG)


### Delete the RDS Instance
Don't forget to delete all the RDS Instance as one can be billed after the free tier quota is over.

<!-- CONTACT -->

## Contact

Pritom Das Radheshyam - [Portfolio Website](https://pritom.uwu.ai/)
[![LinkedIn][linkedin-shield]][linkedin-url]  





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/you-found-pritom
[product-screenshot]: images/screenshot.jpg

