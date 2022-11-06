# Cloud Automation

## Cloud Automation: Auto Scaling

### Cloud Automation: Auto Scaling Group

**Event Types**

* Resource Utilization
    * CPu
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
