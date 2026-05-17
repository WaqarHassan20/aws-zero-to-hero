## What is Cost Optimization ?

##### There are two things in Cloud Working :
- One is simply doing the things.
- Second is doing the things in a cost effective way. 

- Cost optimization is the process of reducing cloud costs while maintaining performance and reliability. It involves identifying and eliminating unnecessary expenses, optimizing resource usage, and implementing cost-effective strategies to maximize the value of cloud investments.
- In an organization , people shift gears to cloud services to save costs.
- One main focus is ***Reduce Overhead of Infrastructure***.
- Second main focus is ***Reduce Cost of Infrastructure***.


## AWS Cloud Cost Optimization - Identifying Stale Resources

### Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

---

#### Example of snapshots, Volumes and EC2 Instances:
- How they are working altogether :
    - EC2 Instances are virtual servers that run applications.
    - EBS Volumes are block storage devices that can be attached to EC2 instances to provide persistent storage.
    - EBS Snapshots are point-in-time backups of EBS volumes, which can be used for data recovery or creating new volumes.
- Now if an ec2 is terminated or stopped and the EBS volume is not deleted, then the snapshot of that volume becomes stale and it will continue to incur storage costs. By identifying and deleting these stale snapshots, we can optimize our cloud costs effectively.
- You can also add a buffer time that after this time that specific snapshot will be deleted, as it is of not use in that last buffer time.
- Delete the snapshot if it is not attached to the volume.
- Delete the snapshot if it is attached to the volume but the volume is not attached to any instance.
- The above deletion policy can vary from organization to organization.