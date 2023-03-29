# AWS Cloud Practitioner Essentials: Storage and Databases

## Resources

## Notes

### Instance Stores and Amazon Elastic Block Store (Amazon EBS)

**Instance stores**

Block-level storage volumes behave like physical hard drives.

An [instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html) store provides temporary block-level storage for an Amazon EC2 instance. An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store. 

Instance store is ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content. It can also be used to store temporary data that you replicate across a fleet of instances, such as a load-balanced pool of web servers.

An Amazon EC2 instance with an attached instance store is running.

![EC2 Instance](../img/instance.png)

The instance is stopped or terminated.

![Stopped EC2 Instance](../img/ec2_instance.png)

All data on the attached instance store is deleted.

![EC2 Instance without Data](../img/instance_with_out_datastore.png)

**Amazon Elastic Block Storage (Amazon EBS)**

[Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs) is a service that provides block-level storage volumes that you can use with Amazon EC2 instances. If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.

To create an EBS volume, you define the configuration (such as volume size and type) and provision it. After you create an EBS volume, it can attach to an Amazon EC2 instance.

Because EBS volumes are for data that needs to persist, it’s important to back up the data. You can take incremental backups of EBS volumes by creating Amazon EBS snapshots.

![EBS](../img/ebs.png)

**Amazon EBS Snapshots**

An EBS snapshot is an incremental backup. This means that the first backup taken of a volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved. 

Incremental backups are different from full backups, in which all the data in a storage volume copies each time a backup occurs. The full backup includes data that has not changed since the most recent backup.

![EBS Snapshot](../img/snapshots.png)

### Amazon Simple Storage Service (Amazon S3)

### Amazon Elastic File System (Amazon EFS)

### Amazon Relational Database Service (Amazon RDS)

### Amazon DynamoDB

### Amazon Redshift

### AWS Database Migration Service (AWS DMS)

### Additional AWS Database Services
