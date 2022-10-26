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
