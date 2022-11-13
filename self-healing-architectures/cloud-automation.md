# Cloud Automation

## Cloud Automation: Auto Scaling

### Cloud Automation: Auto Scaling Group

**Event Types**

* Resource Utilization
    * CPU
    * Memory
* Custom Metrics
* Manual

### Cloud Automation: Auto Scaling Group Configuration

**Configuration Fields:**

* Minimum Size
* Desired Capacity
* Maximum Size

### Pros and Cons of Auto Scaling Cloud Automation

**Pros:**

* Manage cost
* Improves resilience
* Improves application availability

**Cons:**

* Expensive if misconfigured
* Spin up time may be slow

## Cloud Automation: Scaling Virtual Machines

**Scaling Strategies:**

* Scaling up: upgrading VM CPU or memory capacity
* Scaling out: replicating a VM through an autoscaling group

### Scaling Virtual Machines: Use Cases

Scale virtual machines when resource utilization is dynamic

* **Microservice clusters** - VMs are used to create a cluster of resources for deployed services
* **Processing data from a queue** - Scale proportional to the number of items in the queue that require processing

### Cloud Automation: VM Auto Scaling Group

**Configuration Fields:**

* Minimum Size
* Desired Capacity
* Maximum Size

## Scaling Microservice Clusters with Cloud Automation

* Nodes are scaled
* Automation configured in auto scaling group launch template

A cluster is a logical grouping of VMs used for deploying microservices. Each VM int the cluster is known as a Node which is scaled as part of autoscaling orchestration.

* Autoscaling occurs in the cloud via automation configured in an autoscaling group's launch template.
* This tempalte is a description of the scenarios that initiate a scaling event.
* Scaling events may be triggered by resource constraints suck as lack of cpu or memory utilization or manual in preparation for future load demands.

The scaling event may be horizontal or vertical, to support the needs of the microservices.

* In the case of a horizontal scaling scenario the autoscaling group will keep the scaling withing the bounds defined by the maximum size, and scale-in based on the desired size once the extra replicas are no longer needed.
* In the case of a vertical scaling scenario, the launch template will define what VM types are allowed to be upgraded to.
