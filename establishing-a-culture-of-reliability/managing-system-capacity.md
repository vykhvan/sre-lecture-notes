# Managing System Capacity

## Load Testing

* Testing environment
    * Do not test in the live production environment.
        * Do test in the production environment before going live.
    * You should create a testing environment that mirrors production and use data that resembles actual production workloads.
* Load testing scripts
    * Determine what a typical user workflow looks like.
        * Use actual user data, if available.
        * Work with business leaders for expected workflow for non-live systems.
    * Create actual scripts that will be used in the load test.
        * Include a realistic mix of steps that reflect what a typical user will do.
    * A good practice is to add pauses between steps to allow for user interactions and reading.
* Load test metrics for measuring results
    * Resource utilization
        * Look at how much CPU, RAM, storage, and networking are utilized.
        * Look for potential bottlenecks.
    * Response times
        * Direct measure of how your user experiences your system.
        * Higher response times = poor user experience.

## Analyzing System Requirements

* Redundancy
    * Redundancy can be done at several levels. For example,
        * Multiple instances in a data center.
        * Multiple cloud environments spread out all over the world.
    * Benefits of having redundancy:
        * Increases reliability by having multiple instances handling the same function.
        * Improves performance by allowing the workload to be shared among multiple instances.
        * Increases the responsiveness of the system by using server assets closer to the user who has requested it.
        * More flexibility in responding to changes in capacity needs.
* Resource needs
    * Perform load testing to determine needs.
    * Start load tests as soon as the system is in a functioning state.
    * Generalize server function to estimate potential needs.
* User expectations
    * Consider user expectations; different applications need different levels of responsiveness.
    * It is important to meet your users’ expectations while still being realistic about the level of service your system can handle.

## Tiered Capacity Management

* Short-term capacity
    * Capacity for demand right now.
    * Based on current usage patterns, i.e. your current user count and resource usage.
    * Use load testing to determine needs.
* Long-term capacity
    * Resources reserved for growth based on future predictions.
    * Since these resources will take time to bring online, you need to make sure you plan carefully to ensure a positive user experience and avoid wasting money.
* Emergency capacity
    * Used when demand exceeds current resources.
    * The emergency tier refers to resources that can be brought online quickly to help handle a surge in demand. E.g., powered-down VMs that are pre-configured.
    * Incurs some additional costs, but less than leaving resources on and idle.

## Capacity Management Best Practices

* Demand
    * Determine demand by looking at the number of users and requests coming in and the amount of system resources utilized.
    * As demand rises, so does the amount of system resources needed to maintain a functioning system.
* Resource utilization
    * Early warning sign for capacity issues.
    * Look out for low demand but high utilization scenarios, due to users performing more complex operations.
    * Should receive alerts before the user experience is impacted.
* User experience
    * Metrics include response times and error rates.
    * The higher these metrics, the poorer the user experience. This should be handled immediately.
