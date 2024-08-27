# cbg-aws

 client --> front end --> rest api --> database --> Analytical databases  --> Business Intelligence    /  Storage /   security   / Devops
                            |             |                 |                        |                       |           |           |
                            |             |                 |                        |                       |           |            --> CI/CD -> AWS pipeline, codebuild , codeDeploy
                            |             |                 |                        |                       |           |            --> infrastructure - IaaS
                            |             |                 |                        |                       |           |            --> observability 
                            |             |                 |                        |                       |           |
                            |             |                 |                        |                       |            --> as we are using the shared infrastructure security is important
                            |             |                 |                        |                       |            --> control trafic to application is through -> VPC 
                            |             |                 |                        |                       |            --> access control -> subnet 
                            |             |                 |                        |                       |            --> communiction between datacenter-VPC over the internet -> VPN
                            |             |                 |                        |                       |            --> direct connection/ communication -> Direct connect
                            |             |                 |                        |                       |
                            |             |                 |                        |                        --> when we create EC2 instance / hard disk is created with it tp store the data -> EBS
                            |             |                 |                        |                        --> file share / can be share across instances -> EFS 
                            |             |                 |                        |                        --> object storage(key-value), stores objects/images/video/audio/file etc, which can be identified by key -> S3
                            |             |                 |                        |                                        used for static websites
                            |             |                 |                        |
                            |             |                 |                         --> Quick sight 
                            |             |                 |                         
                            |             |                  --> business relational data analysis like -> Hadoop -> RedShift
                            |             |                  --> huge amount of data is operated like data in bulk up to tera bytes
                            |             |                  --> AWS provide data pipeline to transfer data from transactional DB to Analytical DB
                            |             |
                            |              --> OS -> Databasde runtime -> database
                            |              --> high avaliblility 
                            |              --> operations  
                            |                     transactional operations
                            |                      -> SQL / relational  ->RDS / Aurora
                            |                      -> NoSQL -> DynamoDB
                            |              --> scalable   
                            |              --> recovery
                            |              --> security
                            |             
                              --> load balancer --> distribute the load equally -> ELB
                              --> runs on virtual machine / compute system --> where our application is hosted  -> EC2, ECS, AWS Lambda
                              --> auto scaling --> increase the capacity whenever required -> EBS
                              --> regions and zones  --> keeps the system running if one virtual machine fails we have VM in different regions and zones ->ASG ()
                              --> queue, might have other application listening over the queue -> SQS (asynchronus communication)
                              --> communication -> SNS


 cloud front - used to distribute data across the world, to reducw the latency 
  route53 - domain name service         

Cloud - it represents a vast networs of servers, data storage, and services that are accessible over the internate rather than being localized on a physical device or network

Computing - involves processing and managing information using computers, such as running application, storaing and retrieving data , performing calculations

Platform - is a foundation or environment that supports teh development and operations, includes tools, frameworks, service

AWS -Amazon Web Services - 
 a big collection of computer servers and services that connected to internet and hosted by Amazon
 on demand resource provisioning , relese them back when we dont need them 
 stop geussing capacity, speed and agility, go global, no need to maintain the data centers
 


Amazon EC2 - 
Elastic Compute Cloud - provides virtual servers known as instances in the cloud it allows you to easily create and manage virtual machines to run your applications or host web site

Amazon S3 - simple Storage service  - enables to store and retrieve data such as tetx, binary, backup, archives, file, images, videos over the internate, provide high durability, availablity and security
                                     store large object using key value pair, also called as object storage
                                     provide rest api to access and modify object
                                     unlimited storage, 99.99% - avalibility and 99.99999999999% - durability
                                     objects replicated in single region across multiple avalibility zones

Amazon RDS - Relational Database service - manages database service that simplifies the setup, operation and scaling of ralational datbase such as mysql,oracle or sql server. it takes care of admiistrative task  such as backups and software patching allowing you to focus on application

Amazaon VPC - Virtual Private Cloud - allows us to create private network within the amazon cloud, provides isolation and security for resources and enables us to define subnets , configure routing and controls network access using security groups and network ACLs

Amazon IAM - Identity Access Management - helps to manage access to AWS resources securely. it allows you to create and manage users, groups, and roles and assign fine-grained permissions to control who can access which resource

AWS Lambda - lambda is serverless  computing service that enables you to run your code without provisioning or managing servers. we can upload the code andd lambda automatically handles teh infrastructure and scales it based on incoming request 

Amazon SNS - Simple Notification Service - allows us to send notifications and massages to subscribed endpoints or clients. it supportes various delivery protocols, including emails, SMS, mobile push notifications, and HTTP/HTTPS endpoints

Amazon cloudWatch - is a monitoring and observability service that provides insights into your AWS resources and applications. it collects and tracks metrics, monitors logs files, sets alarms and generates visualizations to help you monitor and troubleshoot your infrastucture 




Deployment models for cloud computing
--
When selecting a cloud strategy, a company must consider factors such as required cloud application components, preferred resource management tools, and any legacy IT infrastructure requirements.

Q- Describe the three major categories of cloud services and the AWS products that are based on them ? 
--
The three cloud computing deployment models are public/cloud-based, private/on-premises, and hybrid. 
public - build by service provider, not own by End user
private - used by one individual 
hybride - combination of public + private 

services -
Infrastucute as service IaaS - cloud service provider manages infrastucture for you, user has access through API or dashboard , provider takes care of hardware , netwirking hard divices and data storage and service
Platform as Service PaaS - hardware and application software platform these are provided and manage by outside cloud service providers
Software as Service SaaS - delivers software as a service, apps are web or mobile applications 

Q - How do availability zone and region relayed to one anather ?
--
each region has multiple isolated zone known as availability zone 

Q -geo-targeting in cloudfront?
--
we can detect the country from where end users are requesting ourcontnt this information can be pass to an origin server by the Amazon cloudFront it is sent to new HTTP header based on different countries  we can genrate different content from the different version of same contnent 
these versions can be cached at diff locations that are closer to the end user

Q - What services can be used for developing centralize logging solution?
--
amazon cloud watch logs which can store them in the amazon S3 and then we can use amazon elastic search to visualize them , also we can use amazon kinesis fire hose to move the data from Amazon S3 to Amazon elastic search

Q - various form of virtualization offered by AWS what distinguses them from one another?
--
Hardware Virtual Machine (HVM) - all the virtual machine acts seperate from each other
Paravirtualization (PV) - 
Paravirtualization (HVM) - 

Amazon Elastic Compute Cloud (Amazon EC2)
--
Amazon Elastic Compute Cloud (Amazon EC2)(opens in a new tab) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances. 

Imagine you are responsible for the architecture of your company's resources and need to support new websites. With traditional on-premises resources, you have to do the following:

Spend money upfront to purchase hardware.
Wait for the servers to be delivered to you.
Install the servers in your physical data center.
Make all the necessary configurations.
By comparison, with an Amazon EC2 instance you can use a virtual server to run applications in the AWS Cloud.

You can provision and launch an Amazon EC2 instance within minutes.
You can stop using it when you have finished running a workload.
You pay only for the compute time you use when an instance is running, not when it is stopped or terminated.
You can save costs by paying only for server capacity that you need or want.

service that lets you rent virtual computers in the cloud not physical machine 
run our software and website or do computer related tasks without needing to own and maintain a physical server
EC2 is fundamental service for building and running apllication in the cloud 

key-pair
--
password protected login credentials for the virtual machines that are used to prove our identity while connecting to EC2 instances 
EC2 use s public key cryptography which is used to encrypt and decrypt the login information
EC2 instance uses public key cryptograpy to protect login credentials
key pair - public key and private key , public key is stored in EC2 instance
 
    

Pricing of EC2 - 
--
On demand Instance -
 what it is - renting a computer on go
 how it works -quickly get a virtual server whenever we need it. just pay for hours nad seconds you use.
Reserved Instance -
 what it is - getting a subsription for a specific type of computer
 how it works - we commit to use certain type of computer for 1 or 3 years,  we pay upfront in return we get big discount 
Spot Instance -
 what it is - its a bidding system for extra computers
 how it works - you can bid for extra computers that are availble at a discount, if you bid them highest you get to use untile someone else bid higher
Dedicated Host -
 what it is - its like having own personal computer in cloud 
 how it works - you get physical computer just for yourself. you decide what to put on it and have more control

 
 
Amazon EC2 instance types
--
Amazon EC2 instance types(opens in a new tab) are optimized for different tasks. When selecting an instance type, consider the specific needs of your workloads and applications. This might include requirements for compute, memory, or storage capabilities.

General purpose instances
-
General purpose instances provide a balance of compute, memory, and networking resources. You can use them for a variety of workloads, such as:

application servers
gaming servers
backend servers for enterprise applications
small and medium databases
Suppose that you have an application in which the resource needs for compute, memory, and networking are roughly equivalent. You might consider running it on a general purpose instance because the application does not require optimization in any single resource area.

Compute optimized instances
-
Compute optimized instances are ideal for compute-bound applications that benefit from high-performance processors. Like general purpose instances, you can use compute optimized instances for workloads such as web, application, and gaming servers.
However, the difference is compute optimized applications are ideal for high-performance web servers, compute-intensive applications servers, and dedicated gaming servers. You can also use compute optimized instances for batch processing workloads that require processing many transactions in a single group.

Memory optimized instances
-
Memory optimized instances are designed to deliver fast performance for workloads that process large datasets in memory. In computing, memory is a temporary storage area. It holds all the data and instructions that a central processing unit (CPU) needs to be able to complete actions. Before a computer program or application is able to run, it is loaded from storage into memory. This preloading process gives the CPU direct access to the computer program.
Suppose that you have a workload that requires large amounts of data to be preloaded before running an application. This scenario might be a high-performance database or a workload that involves performing real-time processing of a large amount of unstructured data. In these types of use cases, consider using a memory optimized instance. Memory optimized instances enable you to run workloads with high memory needs and receive great performance.

Accelerated computing instances
-
Accelerated computing instances use hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs. Examples of these functions include floating-point number calculations, graphics processing, and data pattern matching.
In computing, a hardware accelerator is a component that can expedite data processing. Accelerated computing instances are ideal for workloads such as graphics applications, game streaming, and application streaming.

Storage optimized instances
-
Storage optimized instances are designed for workloads that require high, sequential read and write access to large datasets on local storage. Examples of workloads suitable for storage optimized instances include distributed file systems, data warehousing applications, and high-frequency online transaction processing (OLTP) systems.
In computing, the term input/output operations per second (IOPS) is a metric that measures the performance of a storage device. It indicates how many different input or output operations a device can perform in one second. Storage optimized instances are designed to deliver tens of thousands of low-latency, random IOPS to applications. 
You can think of input operations as data put into a system, such as records entered into a database. An output operation is data generated by a server. An example of output might be the analytics performed on the records in a database. If you have an application that has a high IOPS requirement, a storage optimized instance can provide better performance over other instance types not optimized for this kind of use case.

Amazon EC2 pricing
--
With Amazon EC2, you pay only for the compute time that you use. Amazon EC2 offers a variety of pricing options for different use cases. For example, if your use case can withstand interruptions, you can save with Spot Instances. You can also save by committing early and locking in a minimum level of use with Reserved Instances.

On-Demand
-
On-Demand Instances are ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use.

Sample use cases for On-Demand Instances include developing and testing applications and running applications that have unpredictable usage patterns. On-Demand Instances are not recommended for workloads that last a year or longer because these workloads can experience greater cost savings using Reserved Instances.

Reserved Instances
-
Reserved Instances are a billing discount applied to the use of On-Demand Instances in your account. There are two available types of Reserved Instances:
Standard Reserved Instances
Convertible Reserved Instances
You can purchase Standard Reserved and Convertible Reserved Instances for a 1-year or 3-year term. You realize greater cost savings with the 3-year option. 

Standard Reserved Instances: This option is a good fit if you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them. Reserved Instances require you to state the following qualifications:

Instance type and size: For example, m5.xlarge
Platform description (operating system): For example, Microsoft Windows Server or Red Hat Enterprise Linux
Tenancy: Default tenancy or dedicated tenancy
You have the option to specify an Availability Zone for your EC2 Reserved Instances. If you make this specification, you get EC2 capacity reservation. This ensures that your desired amount of EC2 instances will be available when you need them. 

Convertible Reserved Instances: If you need to run your EC2 instances in different Availability Zones or different instance types, then Convertible Reserved Instances might be right for you. Note: You trade in a deeper discount when you require flexibility to run your EC2 instances.

At the end of a Reserved Instance term, you can continue using the Amazon EC2 instance without interruption. However, you are charged On-Demand rates until you do one of the following:

Terminate the instance.
Purchase a new Reserved Instance that matches the instance attributes (instance family and size, Region, platform, and tenancy).

EC2 Instance Savings Plans
-
AWS offers Savings Plans for a few compute services, including Amazon EC2. EC2 Instance Savings Plans reduce your EC2 instance costs when you make an hourly spend commitment to an instance family and Region for a 1-year or 3-year term. This term commitment results in savings of up to 72 percent compared to On-Demand rates. Any usage up to the commitment is charged at the discounted Savings Plans rate (for example, $10 per hour). Any usage beyond the commitment is charged at regular On-Demand rates.

The EC2 Instance Savings Plans are a good option if you need flexibility in your Amazon EC2 usage over the duration of the commitment term. You have the benefit of saving costs on running any EC2 instance within an EC2 instance family in a chosen Region (for example, M5 usage in N. Virginia) regardless of Availability Zone, instance size, OS, or tenancy. The savings with EC2 Instance Savings Plans are similar to the savings provided by Standard Reserved Instances.

Unlike Reserved Instances, however, you don't need to specify up front what EC2 instance type and size (for example, m5.xlarge), OS, and tenancy to get a discount. Further, you don't need to commit to a certain number of EC2 instances over a 1-year or 3-year term. Additionally, the EC2 Instance Savings Plans don't include an EC2 capacity reservation option.

Later in this course, you'll review AWS Cost Explorer, which you can use to visualize, understand, and manage your AWS costs and usage over time. If you're considering your options for Savings Plans, you can use AWS Cost Explorer to analyze your Amazon EC2 usage over the past 7, 30, or 60 days. AWS Cost Explorer also provides customized recommendations for Savings Plans. These recommendations estimate how much you could save on your monthly Amazon EC2 costs, based on previous Amazon EC2 usage and the hourly commitment amount in a 1-year or 3-year Savings Plan.

Spot Instances
-
Spot Instances are ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.

Suppose that you have a background processing job that can start and stop as needed (such as the data processing job for a customer survey). You want to start and stop the processing job without affecting the overall operations of your business. If you make a Spot request and Amazon EC2 capacity is available, your Spot Instance launches. However, if you make a Spot request and Amazon EC2 capacity is unavailable, the request is not successful until capacity becomes available. The unavailable capacity might delay the launch of your background processing job.

After you have launched a Spot Instance, if capacity is no longer available or demand for Spot Instances increases, your instance may be interrupted. This might not pose any issues for your background processing job. However, in the earlier example of developing and testing applications, you would most likely want to avoid unexpected interruptions. Therefore, choose a different EC2 instance type that is ideal for those tasks.

Dedicated Hosts
-
Dedicated Hosts are physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. 

You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance. You can purchase On-Demand Dedicated Hosts and Dedicated Hosts Reservations. Of all the Amazon EC2 options that were covered, Dedicated Hosts are the most expensive.

Scalability
--
Scalability involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. As a result, you pay for only the resources you use. You don’t have to worry about a lack of computing capacity to meet your customers’ needs.

If you wanted the scaling process to happen automatically, which AWS service would you use? The AWS service that provides this functionality for Amazon EC2 instances is Amazon EC2 Auto Scaling.

 EC2 instance type - choose hardware
     optimized combination of compute(CPU,GPU) , memory, disk(storage) and networking for specific workload
     m(m4,m5,m6) - general purpose. balance of computer, memory and networking
     t(t2,t3,t3a) - Brustable performance instance (accumulate CPU credits when inactive) workloads with spikes: web servers, ddeveloper environments and small databases
     c(c4,c5,c5n) - compute optimized, batch processing high performance computing
     r(r4,r5,r5a,r5n) - Memory (RAM) optimized, memory caches and in-memory databases
     i(i3,i2) - storage(I/O) optimized, NoSQL database and data warehousing
     g(g3,g4) GPU Optimized, FP calculaation, graphics processig or video compression
     t2.micro
         t - instance family
         2 - generation
         micro - size  eg nono , micro , small
     
Amazon EC2 Auto Scaling
--
If you’ve tried to access a website that wouldn’t load and frequently timed out, the website might have received more requests than it was able to handle. This situation is similar to waiting in a long line at a coffee shop, when there is only one barista present to take orders from customers.

Bar graph depicting demand and unused capacity over a 7-day period.
Amazon EC2 Auto Scaling enables you to automatically add or remove Amazon EC2 instances in response to changing application demand. By automatically scaling your instances in and out as needed, you can maintain a greater sense of application availability.

Within Amazon EC2 Auto Scaling, you can use two approaches: dynamic scaling and predictive scaling.

Dynamic scaling responds to changing demand. 
Predictive scaling automatically schedules the right number of Amazon EC2 instances based on predicted demand.


To scale faster, you can use dynamic scaling and predictive scaling together.

Example: Amazon EC2 Auto Scaling

In the cloud, computing power is a programmatic resource, so you can take a more flexible approach to the issue of scaling. By adding Amazon EC2 Auto Scaling to an application, you can add new instances to the application when necessary and terminate them when no longer needed.

Suppose that you are preparing to launch an application on Amazon EC2 instances. When configuring the size of your Auto Scaling group, you might set the minimum number of Amazon EC2 instances at one. This means that at all times, there must be at least one Amazon EC2 instance running.

Amazon EC2 instances scaling in and out as part of an Auto Scaling group.
--
When you create an Auto Scaling group, you can set the minimum number of Amazon EC2 instances. The minimum capacity is the number of Amazon EC2 instances that launch immediately after you have created the Auto Scaling group. In this example, the Auto Scaling group has a minimum capacity of one Amazon EC2 instance.

Next, you can set the desired capacity at two Amazon EC2 instances even though your application needs a minimum of a single Amazon EC2 instance to run.

If you do not specify the desired number of Amazon EC2 instances in an Auto Scaling group, the desired capacity defaults to your minimum capacity.

The third configuration that you can set in an Auto Scaling group is the maximum capacity. For example, you might configure the Auto Scaling group to scale out in response to increased demand, but only to a maximum of four Amazon EC2 instances.

Because Amazon EC2 Auto Scaling uses Amazon EC2 instances, you pay for only the instances you use, when you use them. You now have a cost-effective architecture that provides the best customer experience while reducing expenses.


Elastic Load Balancing
--
Elastic Load Balancing is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances. 

A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group. This means that as you add or remove Amazon EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first. Then, the requests spread across multiple resources that will handle them. For example, if you have multiple Amazon EC2 instances, Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it. 

Although Elastic Load Balancing and Amazon EC2 Auto Scaling are separate services, they work together to help ensure that applications running in Amazon EC2 can provide high performance and availability. 

Example: Elastic Load Balancing

ELB pointing to two EC2 instances in an Auto Scaling group.
Low-demand period

Here’s an example of how Elastic Load Balancing works. Suppose that a few customers have come to the coffee shop and are ready to place their orders. 

If only a few registers are open, this matches the demand of customers who need service. The coffee shop is less likely to have open registers with no customers. In this example, you can think of the registers as Amazon EC2 instances.

High-demand period

Throughout the day, as the number of customers increases, the coffee shop opens more registers to accommodate them. 

Additionally, a coffee shop employee directs customers to the most appropriate register so that the number of requests can evenly distribute across the open registers. You can think of this coffee shop employee as a load balancer. 

Auto-Scaling
--
as per the trafic increase the capacity 

AMI Amazon Machine Image -
--
its a virtual image used to create a virtual machine within an EC2 instance.
AMI in EC2 is like snapshot or template of a virtual server.
it include operating system, application and configuration
we use AMI to create and launch new instances in the cloud with the same setup as the original snapshot
it is convenient way to replicate and share a pre-configured environment
AMI has to created manually we can capture the current state(OS, application, configuration) of running EC2 instance and we manually create a private AMI
AMI resources
  Provided by AWS
  Aws Market Place - online store for customized AMIs, per hour billing
  Customized AMIs - created by you
AMIs are stored in Amazon S3(region specific)
an AMI can be shared
 -- choose the AMI you want to  share
    modifiy permissions of AMI to make it shareable, you can modify these permissions through the AWS management console, AWS command Line Interface or AWS sdk
    provide the AWS account IDs of AWS accounts with whom you want to share the AMI
    if you are sharing the AMI with another AWS account, teh owner of that account must accept the sharing invitation

EC2 IP Address
--
   public ip address - are internate addressable
   private ip address are internal to corporate networs
   can not have two resources with same ip address
   public ip address can be enable for EC2 instances in public subnet 
   when we stop instance public address is lost 
   
Elastic IP - EIP
--
service provided by EC2 instance 
it is basically a static IP address attached to an EC2 instance, this address is associated with your AWS account not with an EC2 instance 
when EC2 is restared new dynamic IP address get genrated due this the original link is not available between the website and EC2 instance  - to overcome such situation an EIP or static IP address is used which does not change
we can create 5 EIPs 

Stopping EC2  - means shutting down the instance, it corresponding EBS volume is still attached to an EC2 instance, so you can restart the instance anytime
terminating EC2 - means removing the instance from the AWS acconut 


Monolithic applications and microservices
--
Four rectangles close together in a larger square to indicate tightly coupled components as seen in monolithic applications.
Applications are made of multiple components. The components communicate with each other to transmit data, fulfill requests, and keep the application running. 

Suppose that you have an application with tightly coupled components. These components might include databases, servers, the user interface, business logic, and so on. This type of architecture can be considered a monolithic application. 

In this approach to application architecture, if a single component fails, other components fail, and possibly the entire application fails.

To help maintain application availability when a single component fails, you can design your application through a microservices approach.

Four rectangles with distance between them connected by lines in a rectangle pattern to indicate loosely coupled components.
In a microservices approach, application components are loosely coupled. In this case, if a single component fails, the other components continue to work because they are communicating with each other. The loose coupling prevents the entire application from failing. 

When designing applications on AWS, you can take a microservices approach with services and components that fulfill different functions. Two services facilitate application integration: Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS).

Amazon Simple Notification Service (Amazon SNS)
--
Amazon Simple Notification Service (Amazon SNS) is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers. This is similar to the coffee shop; the cashier provides coffee orders to the barista who makes the drinks.

In Amazon SNS, subscribers can be web servers, email addresses, AWS Lambda functions, or several other options. 

In the next lesson, you will learn more about AWS Lambda.

To review two examples of how to use Amazon SNS, choose the arrow buttons to display each one.


Step 1

Publishing updates from a single topic
A single topic being published to subscribers.
Suppose that the coffee shop has a single newsletter that includes updates from all areas of its business. It includes topics such as coupons, coffee trivia, and new products. All of these topics are grouped because this is a single newsletter. All customers who subscribe to the newsletter receive updates about coupons, coffee trivia, and new products.

After a while, some customers express that they would prefer to receive separate newsletters for only the specific topics that interest them. The coffee shop owners decide to try this approach.


Publishing updates from multiple topics
Multiple topics being published to subscribers.
Now, instead of having a single newsletter for all topics, the coffee shop has broken it up into three separate newsletters. Each newsletter is devoted to a specific topic: coupons, coffee trivia, and new products.

Subscribers will now receive updates immediately for only the specific topics to which they have subscribed.

It is possible for subscribers to subscribe to a single topic or to multiple topics. For example, the first customer subscribes to only the coupons topic, and the second subscriber subscribes to only the coffee trivia topic. The third customer subscribes to both the coffee trivia and new products topics.

Summary
Although these examples from the coffee shop involve subscribers who are people, in Amazon SNS, subscribers can be web servers, email addresses, AWS Lambda functions, or several other options.



Amazon Simple Queue Service (Amazon SQS)    

Amazon Simple Queue Service (Amazon SQS) is a message queuing service. 

Using Amazon SQS, you can send, store, and receive messages between software components, without losing messages or requiring other services to be available. In Amazon SQS, an application sends messages into a queue. A user or service retrieves a message from the queue, processes it, and then deletes it from the queue.


Serverless computing
--
Earlier in this module, you learned about Amazon EC2, a service that lets you run virtual servers in the cloud. If you have applications that you want to run in Amazon EC2, you must do the following:

The term “serverless” means that your code runs on servers, but you do not need to provision or manage these servers. With serverless computing, you can focus more on innovating new products and features instead of maintaining servers.

Another benefit of serverless computing is the flexibility to scale serverless applications automatically. Serverless computing can adjust the applications' capacity by modifying the units of consumptions, such as throughput and memory. 

An AWS service for serverless computing is AWS Lambda.

AWS Lambda
--
AWS Lambda is a service that lets you run code without needing to provision or manage servers. 

While using AWS Lambda, you pay only for the compute time that you consume. Charges apply only when your code is running. You can also run code for virtually any type of application or backend service, all with zero administration. 

For example, a simple Lambda function might involve automatically resizing uploaded images to the AWS Cloud. In this case, the function triggers when uploading a new image. 


You pay only for the compute time that you use. In the previous example of resizing images, you would pay only for the compute time that you use when uploading new images. Uploading the images triggers Lambda to run code for the image resizing function.

In AWS, you can also build and run containerized applications.

Containers
--
Containers provide you with a standard way to package your application's code and dependencies into a single object. You can also use containers for processes and workflows in which there are essential requirements for security, reliability, and scalability.

To review an example on how containers work, choose the arrow buttons.


Step 1

One host with multiple containers
Example of a container that includes apps, bins/libs, an operating system, and a server.
Suppose that a company’s application developer has an environment on their computer that is different from the environment on the computers used by the IT operations staff. The developer wants to ensure that the application’s environment remains consistent regardless of deployment, so they use a containerized approach. This helps to reduce time spent debugging applications and diagnosing differences in computing environments.


Tens of hosts with hundreds of containers
Example of scaling up to tens of hosts with hundreds of containers.
When running containerized applications, it’s important to consider scalability. Suppose that instead of a single host with multiple containers, you have to manage tens of hosts with hundreds of containers. Alternatively, you have to manage possibly hundreds of hosts with thousands of containers. At a large scale, imagine how much time it might take for you to monitor memory usage, security, logging, and so on.

Summary
Container orchestration services help you to deploy, manage, and scale your containerized applications. Next, you will learn about two services that provide container orchestration: Amazon Elastic Container Service and Amazon Elastic Kubernetes Service.


Amazon Elastic Container Service (Amazon ECS)
--
  normal application deployment process -->  virtual machine VM -> OS -> application runtime, eg java runtime -> code, configure env variables -->deployable unit (app code)

  docker does all of it in easy way 
Amazon Elastic Container Service (Amazon ECS) is a highly scalable, high-performance container management system that enables you to run and scale containerized applications on AWS. 

Amazon ECS supports Docker containers. Docker is a software platform that enables you to build, test, and deploy applications quickly. AWS supports the use of open-source Docker Community Edition and subscription-based Docker Enterprise Edition. With Amazon ECS, you can use API calls to launch and stop Docker-enabled applications.

Amazon Elastic Kubernetes Service (Amazon EKS)
--
Amazon Elastic Kubernetes Service (Amazon EKS)(opens in a new tab) is a fully managed service that you can use to run Kubernetes on AWS. 

Kubernetes(opens in a new tab) is open-source software that enables you to deploy and manage containerized applications at scale. A large community of volunteers maintains Kubernetes, and AWS actively works together with the Kubernetes community. As new features and functionalities release for Kubernetes applications, you can easily apply these updates to your applications managed by Amazon EKS.
here we have to maintain the cluster - where we have the nodes conatining the microservices.

AWS Fargate
--
AWS Fargate is a serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS. 

When using AWS Fargate, you do not need to provision or manage servers. AWS Fargate manages your server infrastructure for you. You can focus more on innovating and developing your applications, and you pay only for the resources that are required to run your containers.

Selecting a Region
--

Compliance with data governance and legal requirements
-
Depending on your company and location, you might need to run your data out of specific areas. For example, if your company requires all of its data to reside within the boundaries of the UK, you would choose the London Region. 

Proximity to your customers
-
Selecting a Region that is close to your customers will help you to get content to them faster. For example, your company is based in Washington, DC, and many of your customers live in Singapore. You might consider running your infrastructure in the Northern Virginia Region to be close to company headquarters, and run your applications from the Singapore Region.

Not all companies have location-specific data regulations, so you might need to focus more on the other three factors.
When determining the right Region for your services, data, and applications, consider the following four business factors. 

Available services within a Region
-
Sometimes, the closest Region might not have all the features that you want to offer to customers. AWS is frequently innovating by creating new services and expanding on features within existing services. However, making new services available around the world sometimes requires AWS to build out physical hardware one Region at a time. 

Suppose that your developers want to build an application that uses Amazon Braket (AWS quantum computing platform). As of this course, Amazon Braket is not yet available in every AWS Region around the world, so your developers would have to run it in one of the Regions that already offers it.

Pricing
-
Suppose that you are considering running applications in both the United States and Brazil. The way Brazil’s tax structure is set up, it might cost 50% more to run the same workload out of the São Paulo Region compared to the Oregon Region. You will learn in more detail that several factors determine pricing, but for now know that the cost of services can vary from Region to Region.

An Availability Zone
-
is a single data center or a group of data centers within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency (the time between when content requested and received) between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

Amazon CloudFront - Content Delivery Network
--
   deliver content to global audience
   AWS provide 200+ edge locations
   provide high  availability and low latency
   serve users from nearest edge location
   if content is not available at edge location, it is retrieve from the origin server and cached

   content sources- S3, EC2, ELB or external websites
   use cases -  static web apps, 

Edge locations
-
An edge location is a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.


Ways to interact with AWS services
-

The AWS Management Console
-
is a web-based interface for accessing and managing AWS services. You can quickly access recently used services and search for other services by name, keyword, or acronym. The console includes wizards and automated workflows that can simplify the process of completing tasks.

You can also use the AWS Console mobile application to perform tasks such as monitoring resources, viewing alarms, and accessing billing information. Multiple identities can stay logged into the AWS Console mobile app at the same time.


 AWS Command Line Interface (AWS CLI)
 -
To save time when making API requests, you can use the AWS Command Line Interface (AWS CLI). AWS CLI enables you to control multiple AWS services directly from the command line within one tool. AWS CLI is available for users on Windows, macOS, and Linux. 
By using AWS CLI, you can automate the actions that your services and applications perform through scripts. For example, you can use commands to launch an Amazon EC2 instance, connect an Amazon EC2 instance to a specific Auto Scaling group, and more.

software development kits (SDKs)
-
Another option for accessing and managing AWS services is the software development kits (SDKs). SDKs make it easier for you to use AWS services through an API designed for your programming language or platform. SDKs enable you to use AWS services with your existing applications or create entirely new applications that will run on AWS.
To help you get started with using SDKs, AWS provides documentation and sample code for each supported programming language. Supported programming languages include C++, Java, .NET, and more.


AWS Elastic Beanstalk
-
With AWS Elastic Beanstalk, you provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:

Adjust capacity
Load balancing
Automatic scaling
Application health monitoring

AWS CloudFormation
-
With AWS CloudFormation, you can treat your infrastructure as code. This means that you can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.

AWS CloudFormation provisions your resources in a safe, repeatable manner, enabling you to frequently build your infrastructure and applications without having to perform manual actions. It determines the right operations to perform when managing your stack and rolls back changes automatically if it detects errors.

***
Amazon Virtual Private Cloud (Amazon VPC)
-
our own isolated network in AWS cloud 
network traffic within a VPC is isolated from from all the other AMAZON VPCs
we can control all the traffic coming in and going out from a VPC
it helps in -secure resource from unauthorized access
              enables secure communication between resources
              each VPC is created in a region
Imagine the millions of customers who use AWS services. Also, imagine the millions of resources that these customers have created, such as Amazon EC2 instances. Without boundaries around all of these resources, network traffic would be able to flow between them unrestricted. 

A networking service that you can use to establish boundaries around your AWS resources is Amazon Virtual Private Cloud (Amazon VPC).

Amazon VPC enables you to provision an isolated section of the AWS Cloud. In this isolated section, you can launch resources in a virtual network that you define. Within a virtual private cloud (VPC), you can organize your resources into subnets. A subnet is a section of a VPC that can contain resources such as Amazon EC2 instances.

Internet gateway
-
To allow public traffic from the internet to access your VPC, you attach an internet gateway to the VPC

An internet gateway is a connection between a VPC and the internet. You can think of an internet gateway as being similar to a doorway that customers use to enter the coffee shop. Without an internet gateway, no one can access the resources within your VPC.

What if you have a VPC that includes only private resources?

Virtual private gateway
--
To access private resources in a VPC, you can use a virtual private gateway. 

Here’s an example of how a virtual private gateway works. You can think of the internet as the road between your home and the coffee shop. Suppose that you are traveling on this road with a bodyguard to protect you. You are still using the same road as other customers, but with an extra layer of protection. 

The bodyguard is like a virtual private network (VPN) connection that encrypts (or protects) your internet traffic from all the other requests around it. 

The virtual private gateway is the component that allows protected internet traffic to enter into the VPC. Even though your connection to the coffee shop has extra protection, traffic jams are possible because you’re using the same road as other customers. 

A corporate data center routes network traffic over a VPN connection to a virtual private gateway, which is attached to a VPC
A virtual private gateway enables you to establish a virtual private network (VPN) connection between your VPC and a private network, such as an on-premises data center or internal corporate network. A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.

AWS Direct Connect
--
AWS Direct Connect(opens in a new tab) is a service that lets you to establish a dedicated private connection between your data center and a VPC.  

Suppose that there is an apartment building with a hallway directly linking the building to the coffee shop. Only the residents of the apartment building can travel through this hallway. 

This private hallway provides the same type of dedicated connection as AWS Direct Connect. Residents are able to get into the coffee shop without needing to use the public road shared with other customers. 


A corporate data center routes network traffic to an AWS Direct Connect location. That traffic is then routed to a VPC through a virtual private gateway. All network traffic between the corporate data center and VPC flows through this dedicated private connection.

The private connection that AWS Direct Connect provides helps you to reduce network costs and increase the amount of bandwidth that can travel through your network.



**Subnets
-
A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private. 

Public subnets contain resources that need to be accessible by the public, such as an online store’s website.

Private subnets contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories. 

In a VPC, subnets can communicate with each other. For example, you might have an application that involves Amazon EC2 instances in a public subnet communicating with databases that are located in a private subnet.


**Network traffic in a VPC
--
When a customer requests data from an application hosted in the AWS Cloud, this request is sent as a packet. A packet is a unit of data sent over the internet or a network. 

It enters into a VPC through an internet gateway. Before a packet can enter into a subnet or exit from a subnet, it checks for permissions. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet.


**Network ACLs
--
A network ACL is a virtual firewall that controls inbound and outbound traffic at the subnet level.
Each AWS account includes a default network ACL. When configuring your VPC, you can use your account’s default network ACL or create custom network ACLs. 

By default, your account’s default network ACL allows all inbound and outbound traffic, but you can modify it by adding your own rules. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic to allow. Additionally, all network ACLs have an explicit deny rule. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied. 

**Stateless packet filtering
--
Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound. 
When a packet response for that request comes back to the subnet, the network ACL does not remember your previous request. The network ACL checks the packet response against its list of rules to determine whether to allow or deny.

**Security groups
--
A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.
By default, a security group denies all inbound traffic and allows all outbound traffic. You can add custom rules to configure which traffic should be allowed; any other traffic would then be denied
If you have multiple Amazon EC2 instances within the same VPC, you can associate them with the same security group or use different security groups for each instance.

**Domain Name System (DNS)
--
Suppose that AnyCompany has a website hosted in the AWS Cloud. Customers enter the web address into their browser, and they are able to access the website. This happens because of Domain Name System (DNS) resolution. DNS resolution involves a customer DNS resolver communicating with a company DNS server.


**Amazon Route 53
--
Amazon Route 53(opens in a new tab) is a DNS web service. It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS. 

Amazon Route 53 connects user requests to infrastructure running in AWS (such as Amazon EC2 instances and load balancers). It can route users to infrastructure outside of AWS.

Another feature of Route 53 is the ability to manage the DNS records for domain names. You can register new domain names directly in Route 53. You can also transfer DNS records for existing domain names managed by other domain registrars. This enables you to manage all of your domain names within a single location.

In the previous module, you learned about Amazon CloudFront, a content delivery service. The following example describes how Route 53 and Amazon CloudFront work together to deliver content to customers.

**Stateful packet filtering
--
Security groups perform stateful packet filtering. They remember previous decisions made for incoming packets.

Consider the same example of sending a request out from an Amazon EC2 instance to the internet. 

When a packet response for that request returns to the instance, the security group remembers your previous request. The security group allows the response to proceed, regardless of inbound security group rules.




** DNS 
Translating a domain name to an IP address
The correct response option is Translating a domain name to an IP address.

For example, if you want to visit AnyCompany’s website, you enter the domain name into your PC and this request is sent to a DNS server. Next, the DNS server asks the web server for the IP address that corresponds to AnyCompany’s website. The web server responds by providing the IP address for AnyCompany’s website, 192.0.2.0.



Storage service
-
Instance stores

Block-level storage volumes behave like physical hard drives.

An instance store(opens in a new tab) provides temporary block-level storage for an Amazon EC2 instance. An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store.


**Amazon Elastic Block Store (Amazon EBS)(opens in a new tab) 
is a service that provides block-level storage volumes that you can use with Amazon EC2 instances. If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.

To create an EBS volume, you define the configuration (such as volume size and type) and provision it. After you create an EBS volume, it can attach to an Amazon EC2 instance.

Because EBS volumes are for data that needs to persist, it’s important to back up the data. You can take incremental backups of EBS volumes by creating Amazon EBS snapshots.

An EBS snapshot(opens in a new tab) is an incremental backup. This means that the first backup taken of a volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved. 

Incremental backups are different from full backups, in which all the data in a storage volume copies each time a backup occurs. The full backup includes data that has not changed since the most recent backup.

**In object storage, each object consists of data, metadata, and a key.

The data might be an image, video, text document, or any other type of file. Metadata contains information about what the data is, how it is used, the object size, and so on. An object’s key is its unique identifier.

**Amazon Simple Storage Service (Amazon S3)
-
Amazon Simple Storage Service (Amazon S3) is a service that provides object-level storage. Amazon S3 stores data as objects in buckets.

You can upload any type of file to Amazon S3, such as images, videos, text files, and so on. For example, you might use Amazon S3 to store backup files, media files for a website, or archived documents. Amazon S3 offers unlimited storage space. The maximum file size for an object in Amazon S3 is 5 TB.

When you upload a file to Amazon S3, you can set permissions to control visibility and access to it. You can also use the Amazon S3 versioning feature to track changes to your objects over time.

Amazon S3 storage classes

With Amazon S3, you pay only for what you use. You can choose from a range of storage classes to select a fit for your business and cost needs. When selecting an Amazon S3 storage class, consider these two factors:

How often you plan to retrieve your data
How available you need your data to be

why S3 - 
Data Backup and Stroage  - secure backup of important files, ensuring data durability and accessibility
Static website Hosting - - making it globally accessible
Data Archiving - Archive and preserve data for long term storage with cost efficiency 
Content Distribution - distribute content globally 
Data Transfer - facilitate secure data transfer between AWS services and region supporting seamless integration
Data Analytics -large data set can analize using services like Amazon Athena
Application and software distribution - 
Log Storage  - store and manages log files generated by AWS services, easy to tracj activities

S3 features - 
Durability and Availability - provides  99.99999999999% durability of objects overa given years
Scalability - scales seamlessly to accommodate any amount of data
Security - multiple layers of security access control ,encryption and identity management
Events and Notification - set up event notifications to trigger actions or workflows in response to change in your S3 buckets


key terminologies of S3 -
--
Buckets - big folder , organize your data into buckets, much like orgnizing files into folders in computer, can create upto 100 buckets
Objects - individual file stored within bucket , eg photos, vidios, documnets, or any digital file 
key - unique identifiers for objets in buckets, each object has a key similar to a file path 

Storage classes Avaible in S3
**S3 Standard - frequently access data
-
Designed for frequently accessed data 
Stores data in a minimum of three Availability Zones
Amazon S3 Standard provides high availability for objects. This makes it a good choice for a wide range of use cases, such as websites, content distribution, and data analytics. Amazon S3 Standard has a higher cost than other storage classes intended for infrequently accessed data and archival storage.
low latency

**S3 Standard-Infrequent Access (S3 Standard-IA) - long lived, infrequently access data
-
Ideal for infrequently accessed data
Similar to Amazon S3 Standard but has a lower storage price and higher retrieval price
Amazon S3 Standard-IA is ideal for data infrequently accessed but requires high availability when needed. Both Amazon S3 Standard and Amazon S3 Standard-IA store data in a minimum of three Availability Zones. Amazon S3 Standard-IA provides the same level of availability as Amazon S3 Standard but with a lower storage price and a higher retrieval price.
low cost , 

S3 One Zone-Infrequent Access (S3 One Zone-IA) - long lived, infrequently access data, non-critical data
-
Stores data in a single Availability Zone
Has a lower storage price than Amazon S3 Standard-IA
Compared to S3 Standard and S3 Standard-IA, which store data in a minimum of three Availability Zones, S3 One Zone-IA stores data in a single Availability Zone. This makes it a good storage class to consider if the following conditions apply:
You want to save costs on storage.
You can easily reproduce your data in the event of an Availability Zone failure.

**S3 Intelligent-Tiering - long-lived data with changing or unknown access patterns
-
Ideal for data with unknown or changing access patterns
Requires a small monthly monitoring and automation fee per object
In the S3 Intelligent-Tiering storage class, Amazon S3 monitors objects’ access patterns. If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.

**S3 Glacier Instant Retrieval  - archive data with retrieval tiime ranging from minutes to hours
-
Works well for archived data that requires immediate access
Can retrieve objects within a few milliseconds
When you decide between the options for archival storage, consider how quickly you must retrieve the archived objects. You can retrieve objects stored in the S3 Glacier Instant Retrieval storage class within milliseconds, with the same performance as S3 Standard.

**S3 Glacier Flexible Retrieval  - 
-
Low-cost storage designed for data archiving
Able to retrieve objects within a few minutes to hours
S3 Glacier Flexible Retrieval is a low-cost storage class that is ideal for data archiving. For example, you might use this storage class to store archived customer records or older photos and video files. You can retrieve your data from S3 Glacier Flexible Retrieval from 1 minute to 12 hours.

**S3 Glacier Deep Archive  - archive data that rarely, if ever needed to be access with retrieval times in hours
-
Lowest-cost object storage class ideal for archiving
Able to retrieve objects within 12 hours
S3 Deep Archive supports long-term retention and digital preservation for data that might be accessed once or twice in a year. This storage class is the lowest-cost storage in the AWS Cloud, with data retrieval from 12 to 48 hours. All objects from this storage class are replicated and stored across at least three geographically dispersed Availability Zones.

**S3 Outposts
-
Creates S3 buckets on Amazon S3 Outposts

Makes it easier to retrieve, store, and access data on AWS Outposts

Amazon S3 Outposts delivers object storage to your on-premises AWS Outposts environment. Amazon S3 Outposts is designed to store data durably and redundantly across multiple devices and servers on your Outposts. It works well for workloads with local data residency requirements that must satisfy demanding performance needs by keeping data close to on-premises applications.

**File storage
-
In file storage, multiple clients (such as users, applications, servers, and so on) can access data that is stored in shared file folders. In this approach, a storage server uses block storage with a local file system to organize files. Clients access data through file paths.

Compared to block storage and object storage, file storage is ideal for use cases in which a large number of services and resources need to access the same data at the same time.

Amazon Elastic File System (Amazon EFS)(opens in a new tab) is a scalable file system used with AWS Cloud services and on-premises resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications. 

Amazon EFS is a regional service. It stores data in and across multiple Availability Zones. 

The duplicate storage enables you to access data concurrently from all the Availability Zones in the Region where a file system is located. Additionally, on-premises servers can access Amazon EFS using AWS Direct Connect.


**Relational databases
-
In a relational database, data is stored in a way that relates it to other pieces of data. 
Relational databases use structured query language (SQL) to store and query data. This approach allows data to be stored in an easily understandable, consistent, and scalable way. For example, the coffee shop owners can write a SQL query to identify all the customers whose most frequently purchased drink is a medium latte.

**Amazon Relational Database Service (RDS)
-

relational database for transactional processes
Amazon Relational Database Service (Amazon RDS) is a service that enables you to run relational databases in the AWS Cloud.
manages setup, backup, scaling, replication and patching of your relational databases
features
    multi AZ deployment
    read replicas
    storage auto-scaling
    automated backups
    manual snapshot - copy 
    
Amazon RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups. With these capabilities, you can spend less time completing administrative tasks and more time using data to innovate your applications. You can integrate Amazon RDS with other services to fulfill your business and operational needs, such as using AWS Lambda to query your database from a serverless application.

Amazon RDS provides a number of different security options. Many Amazon RDS database engines offer encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received).

Amazon RDS database engines

Amazon RDS is available on six database engines, which optimize for memory, performance, or input/output (I/O). Supported database engines include:

Amazon Aurora
PostgreSQL
MySQL
MariaDB
Oracle Database
Microsoft SQL Server


Amazon Aurora

Amazon Aurora is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational databases. It is up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases.

Amazon Aurora helps to reduce your database costs by reducing unnecessary input/output (I/O) operations, while ensuring that your database resources remain reliable and available. 

Consider Amazon Aurora if your workloads require high availability. It replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.

EMR - manages hadoop 
**Nonrelational databases
-
In a nonrelational database, you create tables. A table is a place where you can store and query data.

Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. One type of structural approach for nonrelational databases is key-value pairs. With key-value pairs, data is organized into items (keys), and items have attributes (values). You can think of attributes as being different features of your data.

In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes. 

**Amazon DynamoDB
-
Amazon DynamoDB is a key-value database service. It delivers single-digit millisecond performance at any scale.
DynamoDB is serverless, which means that you do not have to provision, patch, or manage servers. 

You also do not have to install, maintain, or operate software.

As the size of your database shrinks or grows, DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance. 
This makes it a suitable choice for use cases that require high performance while scaling.

**Amazon Redshift
-
is relational databse for online analytical proccesses(batch processing)
Amazon Redshift is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.


**AWS Database Migration Service (AWS DMS)
-
AWS Database Migration Service (AWS DMS)(opens in a new tab) enables you to migrate relational databases, nonrelational databases, and other types of data stores.

With AWS DMS, you move data between a source database and a target database. The source and target databases(opens in a new tab) can be of the same type or different types. During the migration, your source database remains operational, reducing downtime for any applications that rely on the database. 

For example, suppose that you have a MySQL database that is stored on premises in an Amazon EC2 instance or in Amazon RDS. Consider the MySQL database to be your source database. Using AWS DMS, you could migrate your data to a target database, such as an Amazon Aurora database.

*Other use cases for AWS DMS
Enabling developers to test applications against production data without affecting production users
Combining several databases into a single database
Sending ongoing copies of your data to other target sources instead of doing a one-time migration

**Additional database services
*Amazon DocumentDB
-
Amazon DocumentDB(opens in a new tab) is a document database service that supports MongoDB workloads.

*Amazon Neptune
-
Amazon Neptune(opens in a new tab) is a graph database service. 
You can use Amazon Neptune to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.

*Amazon Quantum Ledger Database (Amazon QLDB)
-
Amazon Quantum Ledger Database (Amazon QLDB)(opens in a new tab) is a ledger database service. 
You can use Amazon QLDB to review a complete history of all the changes that have been made to your application data.

*Amazon Managed Blockchain
-
Amazon Managed Blockchain(opens in a new tab) is a service that you can use to create and manage blockchain networks with open-source frameworks. 
Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.

*Amazon ElastiCache
-
Amazon ElastiCache(opens in a new tab) is a service that adds caching layers on top of your databases to help improve the read times of common requests. 
It supports two types of data stores: Redis and Memcached.

*Amazon DynamoDB Accelerator
-
Amazon DynamoDB Accelerator (DAX)(opens in a new tab) is an in-memory cache for DynamoDB. 
It helps improve response times from single-digit milliseconds to microseconds.

**
**The AWS shared responsibility model
-
The resources include Amazon EC2 instances, Amazon S3 buckets, and Amazon RDS databases. Who is responsible for keeping these resources secure: you (the customer) or AWS?

The answer is both. The reason is that you do not treat your AWS environment as a single object. Rather, you treat the environment as a collection of parts that build upon each other. AWS is responsible for some parts of your environment and you (the customer) are responsible for other parts. This concept is known as the shared responsibility model(opens in a new tab).

The shared responsibility model divides into customer responsibilities (commonly referred to as “security in the cloud”) and AWS responsibilities (commonly referred to as “security of the cloud”).

*Customers: Security in the cloud
-
Customers are responsible for the security of everything that they create and put in the AWS Cloud.
When using AWS services, you, the customer, maintain complete control over your content. You are responsible for managing security requirements for your content, including which content you choose to store on AWS, which AWS services you use, and who has access to that content. You also control how access rights are granted, managed, and revoked.

The security steps that you take will depend on factors such as the services that you use, the complexity of your systems, and your company’s specific operational and security needs. Steps include selecting, configuring, and patching the operating systems that will run on Amazon EC2 instances, configuring security groups, and managing user accounts. 

*AWS: Security of the cloud
-
AWS is responsible for security of the cloud.

AWS operates, manages, and controls the components at all layers of infrastructure. This includes areas such as the host operating system, the virtualization layer, and even the physical security of the data centers from which services operate. 

AWS is responsible for protecting the global infrastructure that runs all of the services offered in the AWS Cloud. This infrastructure includes AWS Regions, Availability Zones, and edge locations.

AWS manages the security of the cloud, specifically the physical infrastructure that hosts your resources, which include:

Physical security of data centers
Hardware and software infrastructure
Network infrastructure
Virtualization infrastructure
Although you cannot visit AWS data centers to see this protection firsthand, AWS provides several reports from third-party auditors. These auditors have verified its compliance with a variety of computer security standards and regulations.

***
**AWS Identity and Access Management (IAM)
-
AWS Identity and Access Management (IAM)(opens in a new tab) enables you to manage access to AWS services and resources securely.   

IAM gives you the flexibility to configure access based on your company’s specific operational and security needs. You do this by using a combination of IAM features, which are explored in detail in this lesson:

IAM users, groups, and roles
IAM policies
Multi-factor authentication
You will also learn best practices for each of these features.

*AWS account root user
-
When you first create an AWS account, you begin with an identity known as the root user(opens in a new tab). 

The root user is accessed by signing in with the email address and password that you used to create your AWS account. You can think of the root user as being similar to the owner of the coffee shop. It has complete access to all the AWS services and resources in the account.

*IAM users
-
An IAM user is an identity that you create in AWS. It represents the person or application that interacts with AWS services and resources. It consists of a name and credentials.

By default, when you create a new IAM user in AWS, it has no permissions associated with it. To allow the IAM user to perform specific actions in AWS, such as launching an Amazon EC2 instance or creating an Amazon S3 bucket, you must grant the IAM user the necessary permissions.

*IAM policies
-
An IAM policy is a document that allows or denies permissions to AWS services and resources.  

IAM policies enable you to customize users’ levels of access to resources. For example, you can allow users to access all of the Amazon S3 buckets within your AWS account, or only a specific bucket.

*Example: IAM policy
-
Here’s an example of how IAM policies work. Suppose that the coffee shop owner has to create an IAM user for a newly hired cashier. The cashier needs access to the receipts kept in an Amazon S3 bucket with the ID: AWSDOC-EXAMPLE-BUCKET.

Example of an IAM policy
This example IAM policy allows permission to access the objects in the Amazon S3 bucket with ID: AWSDOC-EXAMPLE-BUCKET.

In this example, the IAM policy is allowing a specific action within Amazon S3: ListObject. The policy also mentions a specific bucket ID: AWSDOC-EXAMPLE-BUCKET. When the owner attaches this policy to the cashier’s IAM user, it will allow the cashier to view all of the objects in the AWSDOC-EXAMPLE-BUCKET bucket. 

If the owner wants the cashier to be able to access other services and perform other actions in AWS, the owner must attach additional policies to specify these services and actions.

*IAM groups
-

An IAM group is a collection of IAM users. When you assign an IAM policy to a group, all users in the group are granted permissions specified by the policy.

Here’s an example of how this might work in the coffee shop. Instead of assigning permissions to cashiers one at a time, the owner can create a “Cashiers” IAM group. The owner can then add IAM users to the group and then attach permissions at the group level. 

*IAM roles
-
When the employee needs to switch to a different task, they give up their access to one workstation and gain access to the next workstation. The employee can easily switch between workstations, but at any given point in time, they can have access to only a single workstation. This same concept exists in AWS with IAM roles.

An IAM role is an identity that you can assume to gain temporary access to permissions.  

Before an IAM user, application, or service can assume an IAM role, they must be granted permissions to switch to the role. When someone assumes an IAM role, they abandon all previous permissions that they had under a previous role and assume the permissions of the new role. 

*Multi-factor authentication
-
Have you ever signed in to a website that required you to provide multiple pieces of information to verify your identity? You might have needed to provide your password and then a second form of authentication, such as a random code sent to your phone. This is an example of multi-factor authentication(opens in a new tab).

In IAM, multi-factor authentication (MFA) provides an extra layer of security for your AWS account.

*AWS Organizations
-
Suppose that your company has multiple AWS accounts. You can use AWS Organizations(opens in a new tab) to consolidate and manage multiple AWS accounts within a central location.

When you create an organization, AWS Organizations automatically creates a root, which is the parent container for all the accounts in your organization. 

In AWS Organizations, you can centrally control permissions for the accounts in your organization by using service control policies (SCPs)(opens in a new tab). SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

*Organizational units
-
In AWS Organizations, you can group accounts into organizational units (OUs) to make it easier to manage accounts with similar business or security requirements. When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy.  

By organizing separate accounts into OUs, you can more easily isolate workloads or applications that have specific security requirements. For instance, if your company has accounts that can access only the AWS services that meet certain regulatory requirements, you can put these accounts into one OU. Then, you can attach a policy to the OU that blocks access to all other AWS services that do not meet the regulatory requirements.

To review an example of how a company might use AWS Organizations, choose the arrow buttons to display each step.

*AWS Artifact
-
Depending on your company’s industry, you may need to uphold specific standards. An audit or inspection will ensure that the company has met those standards.

AWS Artifact(opens in a new tab) is a service that provides on-demand access to AWS security and compliance reports and select online agreements. AWS Artifact consists of two main sections: AWS Artifact Agreements and AWS Artifact Reports.

AWS Artifact Agreements
-
Suppose that your company needs to sign an agreement with AWS regarding your use of certain types of information throughout AWS services. You can do this through AWS Artifact Agreements. 

 

In AWS Artifact Agreements, you can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations. Different types of agreements are offered to address the needs of customers who are subject to specific regulations, such as the Health Insurance Portability and Accountability Act (HIPAA).

AWS Artifact Reports
-
–
Next, suppose that a member of your company’s development team is building an application and needs more information about their responsibility for complying with certain regulatory standards. You can advise them to access this information in AWS Artifact Reports.


AWS Artifact Reports provide compliance reports from third-party auditors. These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific security standards and regulations. AWS Artifact Reports remains up to date with the latest reports released. You can provide the AWS audit artifacts to your auditors or regulators as evidence of AWS security controls. 

Customer Compliance Center
-
The Customer Compliance Center(opens in a new tab) contains resources to help you learn more about AWS compliance. 

In the Customer Compliance Center, you can read customer compliance stories to discover how companies in regulated industries have solved various compliance, governance, and audit challenges.

You can also access compliance whitepapers and documentation on topics such as:

AWS answers to key compliance questions
An overview of AWS risk and compliance
An auditing security checklist
Additionally, the Customer Compliance Center includes an auditor learning path. This learning path is designed for individuals in auditing, compliance, and legal roles who want to learn more about how their internal operations can demonstrate compliance using the AWS Cloud.

Denial-of-service attacks
-
A denial-of-service (DoS) attack is a deliberate attempt to make a website or application unavailable to users.
For example, an attacker might flood a website or application with excessive network traffic until the targeted website or application becomes overloaded and is no longer able to respond. If the website or application becomes unavailable, this denies service to users who are trying to make legitimate requests.

Distributed denial-of-service attacks

Now, suppose that the prankster has enlisted the help of friends. 

The prankster and their friends repeatedly call the coffee shop with requests to place orders, even though they do not intend to pick them up. These requests are coming in from different phone numbers, and it’s impossible for the coffee shop to block them all. Additionally, the influx of calls has made it increasingly difficult for customers to be able to get their calls through. This is similar to a distributed denial-of-service attack.

AWS Shield
-
AWS Shield is a service that protects applications against DDoS attacks. AWS Shield provides two levels of protection: Standard and Advanced.
AWS Shield Standard
–
AWS Shield Standard automatically protects all AWS customers at no cost. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks. 
As network traffic comes into your applications, AWS Shield Standard uses a variety of analysis techniques to detect malicious traffic in real time and automatically mitigates it. 

AWS Shield Advanced
–
AWS Shield Advanced is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. 
It also integrates with other services such as Amazon CloudFront, Amazon Route 53, and Elastic Load Balancing. Additionally, you can integrate AWS Shield with AWS WAF by writing custom rules to mitigate complex DDoS attacks.

AWS Key Management Service (AWS KMS)
-
The coffee shop has many items, such as coffee machines, pastries, money in the cash registers, and so on. You can think of these items as data. The coffee shop owners want to ensure that all of these items are secure, whether they’re sitting in the storage room or being transported between shop locations. 

In the same way, you must ensure that your applications’ data is secure while in storage (encryption at rest) and while it is transmitted, known as encryption in transit.

AWS Key Management Service (AWS KMS)(opens in a new tab) enables you to perform encryption operations through the use of cryptographic keys. A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data. You can use AWS KMS to create, manage, and use cryptographic keys. You can also control the use of keys across a wide range of services and in your applications.

With AWS KMS, you can choose the specific levels of access control that you need for your keys. For example, you can specify which IAM users and roles are able to manage keys. Alternatively, you can temporarily disable keys so that they are no longer in use by anyone. Your keys never leave AWS KMS, and you are always in control of them.

AWS WAF
-
AWS WAF(opens in a new tab) is a web application firewall that lets you monitor network requests that come into your web applications. 

AWS WAF works together with Amazon CloudFront and an Application Load Balancer. Recall the network access control lists that you learned about in an earlier module. AWS WAF works in a similar way to block or allow traffic. However, it does this by using a web access control list (ACL)(opens in a new tab) to protect your AWS resources. 

Here’s an example of how you can use AWS WAF to allow and block specific requests.

AWS WAF allows a packet request from a customer.
Suppose that your application has been receiving malicious network requests from several IP addresses. You want to prevent these requests from continuing to access your application, but you also want to ensure that legitimate users can still access it. You configure the web ACL to allow all requests except those from the IP addresses that you have specified.

When a request comes into AWS WAF, it checks against the list of rules that you have configured in the web ACL. If a request does not come from one of the blocked IP addresses, it allows access to the application.

AWS WAF denies a malicious packet request from a hacker.
However, if a request comes from one of the blocked IP addresses that you have specified in the web ACL, AWS WAF denies access.

Amazon Inspector
-
Suppose that the developers at the coffee shop are developing and testing a new ordering application. They want to make sure that they are designing the application in accordance with security best practices. However, they have several other applications to develop, so they cannot spend much time conducting manual assessments. To perform automated security assessments, they decide to use Amazon Inspector(opens in a new tab).

Amazon Inspector helps to improve the security and compliance of applications by running automated security assessments. It checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions. 

After Amazon Inspector has performed an assessment, it provides you with a list of security findings. The list prioritizes by severity level, including a detailed description of each security issue and a recommendation for how to fix it. However, AWS does not guarantee that following the provided recommendations resolves every potential security issue. Under the shared responsibility model, customers are responsible for the security of their applications, processes, and tools that run on AWS services.

Amazon GuardDuty
-
Amazon GuardDuty(opens in a new tab) is a service that provides intelligent threat detection for your AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.

Four main steps of using Amazon GuardDuty: Enable, analyze, intelligently detect, and review findings to take action.
After you have enabled GuardDuty for your AWS account, GuardDuty begins monitoring your network and account activity. You do not have to deploy or manage any additional security software. GuardDuty then continuously analyzes data from multiple AWS sources, including VPC Flow Logs and DNS logs. 

If GuardDuty detects any threats, you can review detailed findings about them from the AWS Management Console. Findings include recommended steps for remediation. You can also configure AWS Lambda functions to take remediation steps automatically in response to GuardDuty’s security findings.

***
Monitoring And Analytics
--

Amazon CloudWatch
--
Amazon CloudWatch(opens in a new tab) is a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.

CloudWatch uses metrics(opens in a new tab) to represent the data points for your resources. AWS services send metrics to CloudWatch. CloudWatch then uses these metrics to create graphs automatically that show how performance has changed over time. 

CloudWatch alarms
--
With CloudWatch, you can create alarms(opens in a new tab) that automatically perform actions if the value of your metric has gone above or below a predefined threshold. 

For example, suppose that your company’s developers use Amazon EC2 instances for application development or testing purposes. If the developers occasionally forget to stop the instances, the instances will continue to run and incur charges. 

In this scenario, you could create a CloudWatch alarm that automatically stops an Amazon EC2 instance when the CPU utilization percentage has remained below a certain threshold for a specified period. When configuring the alarm, you can specify to receive a notification whenever this alarm is triggered.

CloudWatch dashboard
--
CloudWatch dashboard showing metrics for Amazon RDS, Amazon EC2, and Amazon EBS
The CloudWatch dashboard(opens in a new tab) feature enables you to access all the metrics for your resources from a single location. For example, you can use a CloudWatch dashboard to monitor the CPU utilization of an Amazon EC2 instance, the total number of requests made to an Amazon S3 bucket, and more. You can even customize separate dashboards for different business purposes, applications, or resources.

AWS CloudTrail
--
AWS CloudTrail(opens in a new tab) records API calls for your account. The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more. You can think of CloudTrail as a “trail” of breadcrumbs (or a log of actions) that someone has left behind them.

Recall that you can use API calls to provision, manage, and configure your AWS resources. With CloudTrail, you can view a complete history of user activity and API calls for your applications and resources. 

Events are typically updated in CloudTrail within 15 minutes after an API call. You can filter events by specifying the time and date that an API call occurred, the user who requested the action, the type of resource that was involved in the API call, and more.

Example: AWS CloudTrail event

Suppose that the coffee shop owner is browsing through the AWS Identity and Access Management (IAM) section of the AWS Management Console. They discover that a new IAM user named Mary was created, but they do not know who, when, or which method created the user.

To answer these questions, the owner navigates to AWS CloudTrail.

CloudTrail event details: What happened, who made the request, when the request occurred, and how the request was made.
In the CloudTrail Event History section, the owner applies a filter to display only the events for the “CreateUser” API action in IAM. The owner locates the event for the API call that created an IAM user for Mary. This event record provides complete details about what occurred: 

On January 1, 2020 at 9:00 AM, IAM user John created a new IAM user (Mary) through the AWS Management Console.

CloudTrail Insights

Within CloudTrail, you can also enable CloudTrail Insights(opens in a new tab). This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account. 

For example, CloudTrail Insights might detect that a higher number of Amazon EC2 instances than usual have recently launched in your account. You can then review the full event details to determine which actions you need to take next.


AWS Trusted Advisor(opens in a new tab) is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.
-
Trusted Advisor compares its findings to AWS best practices in five categories: cost optimization, performance, security, fault tolerance, and service limits. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 

The guidance provided by AWS Trusted Advisor can benefit your company at all stages of deployment. For example, you can use AWS Trusted Advisor to assist you while you are creating new workflows and developing new applications. You can also use it while you are making ongoing improvements to existing applications and resources.

AWS Trusted Advisor dashboard

AWS Trusted Advisor dashboard where the number of problems, investigations, and actions is indicated for each category.
When you access the Trusted Advisor dashboard on the AWS Management Console, you can review completed checks for cost optimization, performance, security, fault tolerance, and service limits.

For each category:
*
The green check indicates the number of items for which it detected no problems.
*
The orange triangle represents the number of recommended investigations.
*
The red circle represents the number of recommended actions.

***
Pricing And Support
--

AWS Free Tier
-
The AWS Free Tier(opens in a new tab) enables you to begin using certain services without having to worry about incurring costs for the specified period. 

Three types of offers are available: 

Always Free
12 Months Free
Trials
For each free tier offer, make sure to review the specific details about exactly which resource types are included. 

Always Free
-
These offers do not expire and are available to all AWS customers.
For example, AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month. Amazon DynamoDB allows 25 GB of free storage per month.

12 Months Free
-
These offers are free for 12 months following your initial sign-up date to AWS.
Examples include specific amounts of Amazon S3 Standard Storage, thresholds for monthly hours of Amazon EC2 compute time, and amounts of Amazon CloudFront data transfer out.

Trials
-
Short-term free trial offers start from the date you activate a particular service. The length of each trial might vary by number of days or the amount of usage in the service.
For example, Amazon Inspector offers a 90-day free trial. Amazon Lightsail (a service that enables you to run virtual private servers) offers 750 free hours of usage over a 30-day period.

How AWS pricing works
----

Pay for what you use.
-
For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing. 

Pay less when you reserve.
-
Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.
For example, suppose that your company is using Amazon EC2 instances for a workload that needs to run continuously. You might choose to run this workload on Amazon EC2 Instance Savings Plans, because the plan allows you to save up to 72% over the equivalent On-Demand Instance capacity.

Pay less with volume-based discounts when you use more.
-
Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage.
For example, the more Amazon S3 storage space you use, the less you pay for it per GB.


Consolidated billing
--
In an earlier module, you learned about AWS Organizations, a service that enables you to manage multiple AWS accounts from a central location. AWS Organizations also provides the option for consolidated billing(opens in a new tab). 

The consolidated billing feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. By consolidating, you can easily track the combined costs of all the linked accounts in your organization. The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.

On your monthly bill, you can review itemized charges incurred by each account. This enables you to have greater transparency into your organization’s accounts while still maintaining the convenience of receiving a single monthly bill.

Another benefit of consolidated billing is the ability to share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in your organization. For instance, one account might not have enough monthly usage to qualify for discount pricing. However, when multiple accounts are combined, their aggregated usage may result in a benefit that applies across all accounts in the organization.


AWS Budgets
--
In AWS Budgets(opens in a new tab), you can create budgets to plan your service usage, service costs, and instance reservations.

The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.

In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

Example: AWS Budgets

Suppose that you have set a budget for Amazon EC2. You want to ensure that your company’s usage of Amazon EC2 does not exceed $200 for the month. 

In AWS Budgets, you could set a custom budget to notify you when your usage has reached half of this amount ($100). This setting would allow you to receive an alert and decide how you would like to proceed with your continued use of Amazon EC2.

AWS Cost Explorer
--
AWS Cost Explorer(opens in a new tab) is a tool that lets you visualize, understand, and manage your AWS costs and usage over time.

AWS Cost Explorer includes a default report of the costs and usage for your top five cost-accruing AWS services. You can apply custom filters and groups to analyze your data. For example, you can view resource usage at the hourly level.

Example: AWS Cost Explorer

Example of the AWS Cost Explorer dashboard.
This example of the AWS Cost Explorer dashboard displays monthly costs for Amazon EC2 instances over a 6-month period. The bar for each month separates the costs for different Amazon EC2 instance types, such as t2.micro or m3.large. 

By analyzing your AWS costs over time, you can make informed decisions about future costs and how to plan your budgets.

***
AWS Support
---
AWS offers four different Support plans(opens in a new tab) to help you troubleshoot issues, lower costs, and efficiently use AWS services. 

You can choose from the following Support plans to meet your company’s needs: 

Basic
Developer
Business
Enterprise On-Ramp
Enterprise
Basic Support

Basic Support is free for all AWS customers. It includes access to whitepapers, documentation, and support communities. With Basic Support, you can also contact AWS for billing questions and service limit increases.

With Basic Support, you have access to a limited selection of AWS Trusted Advisor checks. Additionally, you can use the AWS Personal Health Dashboard, a tool that provides alerts and remediation guidance when AWS is experiencing events that may affect you. 

If your company needs support beyond the Basic level, you could consider purchasing Developer, Business, Enterprise On-Ramp, and Enterprise Support.

Developer, Business, Enterprise On-Ramp, and Enterprise Support

The Developer, Business, Enterprise On-Ramp, and Enterprise Support plans include all the benefits of Basic Support, in addition to the ability to open an unrestricted number of technical support cases. These Support plans have pay-by-the-month pricing and require no long-term contracts.

The information in this course highlights only a selection of details for each Support plan. A complete overview of what is included in each Support plan, including pricing for each plan, is available on the AWS Support(opens in a new tab) site.

In general, for pricing, the Developer plan has the lowest cost, the Business and Enterprise On-Ramp plans are in the middle, and the Enterprise plan has the highest cost.

Developer Support
-
Customers in the Developer Support plan have access to features such as:

Best practice guidance
Client-side diagnostic tools
Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together
For example, suppose that your company is exploring AWS services. You’ve heard about a few different AWS services. However, you’re unsure of how to potentially use them together to build applications that can address your company’s needs. In this scenario, the building-block architecture support that is included with the Developer Support plan could help you to identify opportunities for combining specific services and features.

Business Support
-
Customers with a Business Support plan have access to additional features, including: 

Use-case guidance to identify AWS offerings, features, and services that can best support your specific needs
All AWS Trusted Advisor checks
Limited support for third-party software, such as common operating systems and application stack components
Suppose that your company has the Business Support plan and wants to install a common third-party operating system onto your Amazon EC2 instances. You could contact AWS Support for assistance with installing, configuring, and troubleshooting the operating system. For advanced topics such as optimizing performance, using custom scripts, or resolving security issues, you may need to contact the third-party software provider directly.

Enterprise On-Ramp Support
-
In November 2021, AWS opened enrollment into AWS Enterprise On-Ramp Support plan. In addition to all the features included in the Basic, Developer, and Business Support plans, customers with an Enterprise On-Ramp Support plan have access to:

A pool of Technical Account Managers to provide proactive guidance and coordinate access to programs and AWS experts

A Cost Optimization workshop (one per year)

A Concierge support team for billing and account assistance

Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard

Enterprise On-Ramp Support plan also provides access to a specific set of proactive support services, which are provided by a pool of Technical Account Managers.

Consultative review and architecture guidance (one per year)

Infrastructure Event Management support (one per year)

Support automation workflows

30 minutes or less response time for business-critical issues

Enterprise Support
-
In addition to all features included in the Basic, Developer, Business, and Enterprise On-Ramp support plans, customers with Enterprise Support have access to:

A designated Technical Account Manager to provide proactive guidance and coordinate access to programs and AWS experts

A Concierge support team for billing and account assistance

Operations Reviews and tools to monitor health

Training and Game Days to drive innovation

Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard

The Enterprise plan also provides full access to proactive services, which are provided by a designated Technical Account Manager:

Consultative review and architecture guidance

Infrastructure Event Management support

Cost Optimization Workshop and tools

Support automation workflows

15 minutes or less response time for business-critical issues

Technical Account Manager (TAM)
-
The Enterprise On-Ramp and Enterprise Support plans include access to a Technical Account Manager (TAM).

The TAM is your primary point of contact at AWS. If your company subscribes to Enterprise Support or Enterprise On-Ramp, your TAM educates, empowers, and evolves your cloud journey across the full range of AWS services. TAMs provide expert engineering guidance, help you design solutions that efficiently integrate AWS services, assist with cost-effective and resilient architectures, and provide direct access to AWS programs and a broad community of experts.

For example, suppose that you are interested in developing an application that uses several AWS services together. Your TAM could provide insights into how to best use the services together. They achieve this, while aligning with the specific needs that your company is hoping to address through the new application.

AWS Marketplace

AWS Marketplace(opens in a new tab) is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS. 

For each listing in AWS Marketplace, you can access detailed information on pricing options, available support, and reviews from other AWS customers.

You can also explore software solutions by industry and use case. For example, suppose your company is in the healthcare industry. In AWS Marketplace, you can review use cases that software helps you to address, such as implementing solutions to protect patient records or using machine learning models to analyze a patient’s medical history and predict possible health risks.

AWS Marketplace categories
-

AWS Marketplace offers products in several categories, such as Infrastructure Software, DevOps, Data Products, Professional Services, Business Applications, Machine Learning, Industries, and Internet of Things (IoT).
Within each category, you can narrow your search by browsing through product listings in subcategories. For example, subcategories in the DevOps category include areas such as Application Development, Monitoring, and Testing.

***
Migration and Innovation
-

AWS Cloud Adoption Framework (AWS CAF)
-

Six core perspectives of the Cloud Adoption Framework

At the highest level, the AWS Cloud Adoption Framework (AWS CAF)(opens in a new tab) organizes guidance into six areas of focus, called Perspectives. Each Perspective addresses distinct responsibilities. The planning process helps the right people across the organization prepare for the changes ahead.

In general, the Business, People, and Governance Perspectives focus on business capabilities, whereas the Platform, Security, and Operations Perspectives focus on technical capabilities.

Business Perspective
-
The Business Perspective ensures that IT aligns with business needs and that IT investments link to key business results.
Use the Business Perspective to create a strong business case for cloud adoption and prioritize cloud adoption initiatives. Ensure that your business strategies and goals align with your IT strategies and goals.

Common roles in the Business Perspective include: 

Business managers
Finance managers
Budget owners
Strategy stakeholders

People Perspective
-
The People Perspective supports development of an organization-wide change management strategy for successful cloud adoption.
Use the People Perspective to evaluate organizational structures and roles, new skill and process requirements, and identify gaps. This helps prioritize training, staffing, and organizational changes.
Common roles in the People Perspective include: 

Human resources
Staffing
People managers

Governance Perspective
-
The Governance Perspective focuses on the skills and processes to align IT strategy with business strategy. This ensures that you maximize the business value and minimize risks.
Use the Governance Perspective to understand how to update the staff skills and processes necessary to ensure business governance in the cloud. Manage and measure cloud investments to evaluate business outcomes.

Common roles in the Governance Perspective include: 

Chief Information Officer (CIO)
Program managers
Enterprise architects
Business analysts
Portfolio managers

Platform Perspective
-
The Platform Perspective includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud.
Use a variety of architectural models to understand and communicate the structure of IT systems and their relationships. Describe the architecture of the target state environment in detail.

Common roles in the Platform Perspective include: 

Chief Technology Officer (CTO)
IT managers
Solutions architects

Security Perspective
-
The Security Perspective ensures that the organization meets security objectives for visibility, auditability, control, and agility. 
Use the AWS CAF to structure the selection and implementation of security controls that meet the organization’s needs.

Common roles in the Security Perspective include: 

Chief Information Security Officer (CISO)
IT security managers
IT security analysts

Operations Perspective
-
The Operations Perspective helps you to enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholders.
Define how day-to-day, quarter-to-quarter, and year-to-year business is conducted. Align with and support the operations of the business. The AWS CAF helps these stakeholders define current operating procedures and identify the process changes and training needed to implement successful cloud adoption.

Common roles in the Operations Perspective include: 

IT operations managers
IT support managers


6 strategies for migration
--
When migrating applications to the cloud, six of the most common migration strategies(opens in a new tab) that you can implement are:

Rehosting
-
Rehosting also known as “lift-and-shift” involves moving applications without changes. 

In the scenario of a large legacy migration, in which the company is looking to implement its migration and scale quickly to meet a business case, the majority of applications are rehosted.  

Replatforming
-
Replatforming, also known as “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit. Optimization is achieved without changing the core architecture of the application.

Refactoring/re-architecting
-
Refactoring (also known as re-architecting) involves reimagining how an application is architected and developed by using cloud-native features. Refactoring is driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.

Repurchasing
-
Repurchasing involves moving from a traditional license to a software-as-a-service model. 
For example, a business might choose to implement the repurchasing strategy by migrating from a customer relationship management (CRM) system to Salesforce.com.

Retaining
-
Retaining consists of keeping applications that are critical for the business in the source environment. This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.

Retiring
-
Retiring is the process of removing applications that are no longer needed.


AWS Snow Family members
--
The AWS Snow Family(opens in a new tab) is a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS. 

AWS Snow Family is composed of AWS Snowcone, AWS Snowball, and AWS Snowmobile. 


These devices offer different capacity points, and most include built-in computing capabilities. AWS owns and manages the Snow Family devices and integrates with AWS security, monitoring, storage management, and computing capabilities.  

AWS Snowcone(opens in a new tab)
-
is a small, rugged, and secure edge computing and data transfer device. 
It features 2 CPUs, 4 GB of memory, and up to 14 TB of usable storage.

AWS Snowball 
-
    transfer terabyte or petabytes of data from on-premises


offers two types of devices:
Snowball Edge Storage Optimized 
-
devices are well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs. 
Storage: 80 TB of hard disk drive (HDD) capacity for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA solid state drive (SSD) for block volumes. 
Compute: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe1 instances (equivalent to C5).

Snowball Edge Compute Optimized 
-
provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks. 
Storage: 80-TB usable HDD capacity for Amazon S3 compatible object storage or Amazon EBS compatible block volumes and 28 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes. 
Compute: 104 vCPUs, 416 GiB of memory, and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances.

AWS Snowmobile
-
is an exabyte-scale data transfer service used to move large amounts of data to AWS. 
You can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.

Innovate with AWS Services
--
When examining how to use AWS services, it is important to focus on the desired outcomes. You are properly equipped to drive innovation in the cloud if you can clearly articulate the following conditions: 

The current state
The desired state
The problems you are trying to solve
Consider some of the paths you might explore in the future as you continue on your cloud journey. 

Serverless applications
-
With AWS, serverless refers to applications that don’t require you to provision, maintain, or administer servers. You don’t need to worry about fault tolerance or availability. AWS handles these capabilities for you.
AWS Lambda is an example of a service that you can use to run serverless applications. If you design your architecture to trigger Lambda functions to run your code, you can bypass the need to manage a fleet of servers.
Building your architecture with serverless applications enables your developers to focus on their core product instead of managing and operating servers.

Artificial intelligence
-
AWS offers a variety of services powered by artificial intelligence (AI). 
For example, you can perform the following tasks:

Convert speech to text with Amazon Transcribe.
Discover patterns in text with Amazon Comprehend.
Identify potentially fraudulent online activities with Amazon Fraud Detector.
Build voice and text chatbots with Amazon Lex.

Machine learning
-
Traditional machine learning (ML) development is complex, expensive, time consuming, and error prone. AWS offers Amazon SageMaker to remove the difficult work from the process and empower you to build, train, and deploy ML models quickly.
You can use ML to analyze data, solve complex problems, and predict outcomes before they happen.

In Amazon Lex, you can quickly build, test, and deploy conversational chatbots to use in your applications.
A machine learning service that automatically extracts text and data from scanned document describes Amazon Textract.
A document database service that supports MongoDB workloads describes Amazon DocumentDB.
A service that enables you to identify potentially fraudulent online activities describes Amazon Fraud Detector.

***
The AWS Well-Architected Framework
--
The AWS Well-Architected Framework(opens in a new tab) helps you understand how to design and operate reliable, secure, efficient, and cost-effective systems in the AWS Cloud. It provides a way for you to consistently measure your architecture against best practices and design principles and identify areas for improvement.

Operational excellence
-
Operational excellence is the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.  
Design principles for operational excellence in the cloud include performing operations as code, annotating documentation, anticipating failure, and frequently making small, reversible changes.

Security
-
The Security pillar is the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies. 
When considering the security of your architecture, apply these best practices:

Automate security best practices when possible.
Apply security at all layers.
Protect data in transit and at rest.

Reliability
-
Reliability is the ability of a system to do the following:

Recover from infrastructure or service disruptions
Dynamically acquire computing resources to meet demand
Mitigate disruptions such as misconfigurations or transient network issues
Reliability includes testing recovery procedures, scaling horizontally to increase aggregate system availability, and automatically recovering from failure.

Performance efficiency
-
Performance efficiency is the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve. 
Evaluating the performance efficiency of your architecture includes experimenting more often, using serverless architectures, and designing systems to be able to go global in minutes.


Cost optimization
-
Cost optimization is the ability to run systems to deliver business value at the lowest price point. 
Cost optimization includes adopting a consumption model, analyzing and attributing expenditure, and using managed services to reduce the cost of ownership.


Sustainability
-
In December 2021, AWS introduced a sustainability pillar as part of the AWS Well-Architected Framework.
Sustainability is the ability to continually improve sustainability impacts by reducing energy consumption and increasing efficiency across all components of a workload by maximizing the benefits from the provisioned resources and minimizing the total resources required.

To facilitate good design for sustainability:

Understand your impact

Establish sustainability goals

Maximize utilization

Anticipate and adopt new, more efficient hardware and software offerings

Use managed services

Reduce the downstream impact of your cloud workloads

Advantages of cloud computing
--
Operating in the AWS Cloud offers many benefits over computing in on-premises or hybrid environments. 

In this section, you will learn about six advantages of cloud computing:

Trade upfront expense for variable expense.
-
Upfront expenses include data centers, physical servers, and other resources that you would need to invest in before using computing resources. 
Instead of investing heavily in data centers and servers before you know how you’re going to use them, you can pay only when you consume computing resources.

Benefit from massive economies of scale.
-
By using cloud computing, you can achieve a lower variable cost than you can get on your own. 
Because usage from hundreds of thousands of customers aggregates in the cloud, providers such as AWS can achieve higher economies of scale. Economies of scale translate into lower pay-as-you-go prices.

Stop guessing capacity.
-
With cloud computing, you don’t have to predict how much infrastructure capacity you will need before deploying an application. 
For example, you can launch Amazon Elastic Compute Cloud (Amazon EC2) instances when needed and pay only for the compute time you use. Instead of paying for resources that are unused or dealing with limited capacity, you can access only the capacity that you need, and scale in or out in response to demand. 

Increase speed and agility.
-
The flexibility of cloud computing makes it easier for you to develop and deploy applications.
This flexibility also provides your development teams with more time to experiment and innovate.

Stop spending money running and maintaining data centers.
-
Cloud computing in data centers often requires you to spend more money and time managing infrastructure and servers. 
A benefit of cloud computing is the ability to focus less on these tasks and more on your applications and customers.

Go global in minutes.
-
The AWS Cloud global footprint enables you to quickly deploy applications to customers around the world, while providing them with low latency.


What are key components of AWS?
  cloud watch - used to monitor AWS resources
  Elastic Block Storage - used as persistent storage volumes
  Route 53 - A DNS web service
  Identity Access Management - used as identity management gor AWS account 
  Simple Storage Service - used to store and retrieve the bulk amount of data at any time on the web
  Elastic Compute Cloud - used to provide on demand computing resources for hosting application
How can we send a request to amazon S3?
  S3 used REST service , rest api, AWS SDK, AWS management console
