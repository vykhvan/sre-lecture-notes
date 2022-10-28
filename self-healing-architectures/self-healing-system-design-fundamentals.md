# Self-healing System Design Fundamentals

**Resiliency:** The degree to which a system and it's components can handle or recover from workload or stress.

## Insight: Self-healing System Design Fundamentals

* **Flexibility** - The ability to add new components to a design without impacting the system.
* **Best Practices** - The ability to learn from a community of engineers, and apply lessons learned to avoid pitfalls.
* **Maintainability** - The ability to modernize without breaking the system.
* **Visualization** - The ability to display your architectural choices in a diagram so that it's easy to understand by non-technical folks. This can be important when presenting your use case for changes to the business.

## Single Point of Failure

**Single point of failure** is a bottleneck that occurs when a system is impacted by the failure of a single component. This single component is sometimes referred to as a **hotspot**. A high activity zone in your system.

### How to Solve Single Point of Failure?

**High Availability**
* Scaling

**Disaster Recovery**
* Failover

**Modularity**
* Break down components

## Three-Tier Architecture

* Presentation Layer, known as the frontend
* An application layer, the backend
* A data layer, the database, or data source

**Pros**

* Easy stack updated
* Development team expertise
* Greater reliability
* Easier to scale
* Innovation

**Cons**

* Complexity
* Presentation & data layer separation
* Increased testing requirements

## Self-healing Automation Strategies

### Automation Strategies

* Scaling
* Fault Tolerance
* High Availability

### System Design: Scaling

* Scaling Up (+ Memory, + CPU)
* Scaling Out (+ Replicas)
* Scaling In (- Replicas)

### System Design: Fault Tolerance

Fault tolerance is the ability to continue operating despite failures or malfunctions.

**Example: multi-region databases**

### System Design: High Availability

High availability is similar to fault tolerance in that it is the ability to continue operating despite failures or malfunctions.

**Example: read and write replicas in databases**

## Self-healing Micro-service Design

### Self-Healing: Health Checks

* Application API endpoint that provides status information
* Text("OK")
* Resource Utilization
* Metadata

### Self-Healing: Load Balancing

Sending an equal amount of requests to a group of applications

### Self-Healing: Change Management

* Keeping track of change in an application
* Version controlling releases to cloud environments

### Self-Healing: Graceful Service Degradation

* Gracefully shutdown after receiving a termination signal
* Typically occurs during: Scale In Events New Deployments

### Self-Healing: Rate Limiting

* Cap the number of requests a microservice can handle
