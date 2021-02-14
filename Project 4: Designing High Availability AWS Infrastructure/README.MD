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

Keep everything default, we will provide the Bootstrap Script in the "User Data" from the "Advanced Settings" :

![APT](./images/4.PNG)

Here is the Bootstrap Script for better view:

![APT](./images/5.PNG)

In the security group we will open another rule for "HTTP" connection:

![APT](./images/6.PNG)

Now let's check if our webserver is serving the desired content properly or not. Grab the Public IPv4 address:

![APT](./images/7.PNG)

If the webserver is working correctly, then it should view this in a new browser :

![APT](./images/8.PNG)

Now, we will create an AMI from this EC2 instance that we have just deployed. Follow the picture given below to create an image:

![APT](./images/9.PNG)

Keep veryhting default and give a name to this image:

![APT](./images/10.PNG)

Now go to "Images" section and click "AMIs". Our new image should show "available" in status:

![APT](./images/11.PNG)

Now we can terminate the EC2 instance that we have created, the main purpose was to create a custom AMI which we have completed:

![APT](./images/12.PNG)


### Part 2: Creating Application Load Balancer

Go to Load Balancer, create a new load balancer and choose Application Load Balancer :

![APT](./images/13.PNG)

Give a name to the Load Balancer and choose two availability zones. Make sure these availability zones are part of public subnet and not private subnet :

![APT](./images/14.PNG)

We will create a new security group and keep the default rule :

![APT](./images/15.PNG)

After successfully creating the load balancer:

![APT](./images/16.PNG)



### Part 3: Creating Launch Configuration and Auto Scaling Group
Select " Create Launch Configuration" :

![APT](./images/17.PNG)

This is an important stage, we will  open another rule in the security group in our launch configuration and this new rule type should be of HTTP and the source should be security group ID of the the one that we created for our Application Load Balancer:


![APT](./images/18.PNG)


Now we will create the auto scaling group and we will select the launch configuration that we have created earlier :

![APT](./images/19.PNG)

Configure the settings for the Auto Scaling Group like this below :

![APT](./images/20.PNG)

Don't forget to attach our existing Application Load Balancer in this Auto Scaling Group:

![APT](./images/21.PNG)


Since the design requires two EC2 Instances, we will custoize the group size based on that:

![APT](./images/22.PNG)

After successful creation of the Auto Scaling Group, it should like this as the picture given below:

![APT](./images/23.PNG)

### Part 4: Accessing our High Availability Infrastrcuture Design :

Let's see if everything is working properly. Goto the created Load Balancer and copy the DNS Name. We will check this DNS name in a separate browser window:

![APT](./images/24.PNG)

It should look like this in the browser:

![APT](./images/25.PNG)

<!-- CONTACT -->

## Contact

Pritom Das Radheshyam - [Portfolio Website](https://pritom.uwu.ai/)
[![LinkedIn][linkedin-shield]][linkedin-url]  





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/you-found-pritom
[product-screenshot]: images/screenshot.jpg

