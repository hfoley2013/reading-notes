# AWS Cloud Practitioner Essentials: Compute in the Cloud

## Summary

* Amazon Elastic Compute Cloud (**EC2** ) is how you gain access to virtual servers hosted by AWS
* AWS is constantly operating a massive amount of compute capacity. And you can use whatever portion of that capacity, when you need it
* All you have to do is request the EC2 instances you want, and they will launch and boot up, ready to be used within a few minutes
* Once you're done, you can easily stop or terminate the EC2 instances
* When you spin up an EC2 instance, you weren't necessarily taking an entire host to yourself. Instead, you are sharing the host, with multiple other instances, otherwise known as virtual machines. And a hypervisor running on the host machine is responsible for sharing the underlying physical resources between the virtual machines.
* This idea of sharing underlying hardware is called **multitenancy**
  * The hypervisor is responsible for coordinating this multitenancy and it is managed by AWS
  * The hypervisor is responsible for isolating the virtual machines from each other as they share resources from the host
    * Therefore, EC2 instances are not aware of any other EC2 instance operating on the same host
* When you provision an EC2 instance, you can choose the operating system based on either Windows or Linux

### [Amazon Elastic Compute Cloud (EC2)](https://aws.amazon.com/ec2/)

Amazon Elastic Compute Cloud (Amazon EC2) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances. 

Imagine you are responsible for the architecture of your company's resources and need to support new websites. With traditional on-premises resources, you have to do the following:

* Spend money upfront to purchase hardware.
* Wait for the servers to be delivered to you.
* Install the servers in your physical data center.
* Make all the necessary configurations.

By comparison, with an Amazon EC2 instance you can use a virtual server to run applications in the AWS Cloud.

* You can provision and launch an Amazon EC2 instance within minutes.
* You can stop using it when you have finished running a workload.
* You pay only for the compute time you use when an instance is running, not when it is stopped or terminated.
* You can save costs by paying only for server capacity that you need or want.

**How EC2 Works**

![EC2](./ec2.png)

**Launch**

First, you launch an instance. Begin by selecting a template with basic configurations for your instance. These configurations include the operating system, application server, or applications. You also select the instance type, which is the specific hardware configuration of your instance. 

As you are preparing to launch an instance, you specify security settings to control the network traffic that can flow into and out of your instance. Later in this course, we will explore Amazon EC2 security features in greater detail.

**Connect**

Next, connect to the instance. You can connect to the instance in several ways. Your programs and applications have multiple different methods to connect directly to the instance and exchange data. Users can also connect to the instance by logging in and accessing the computer desktop.

**Use**

After you have connected to the instance, you can begin using it. You can run commands to install software, add storage, copy and organize files, and more.

### [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/)

* Each instance type is grouped under an instance family that is optimized for certain types of tasks
  * Various combinations of CPU, memory, storage, and networking capacity
* Instance Families
  * **General Purpose**
    * Balanced resources
    * Diverse workloads
    * Web servers
    * Code Repositories
  * **Compute Optimized**
    * Ideal for compute intensive tasks
    * Gaming servers
    * High performance computing (HPC)
    * Scientific modeling
  * **Memory Optimized**
    * Memory intensive tasks
  * **Accelerated Computing**
    * Floating point number calculations
    * Graphic processing
    * Data pattern matching
    * Utilize hardware accelerators
  * **Storage Optimized**
    * High performance for locally stored data
