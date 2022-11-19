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

### Redundancy

* Multiple instanced of a service
* Multiple environments across different regions
* Increases reliability
* Increases performance
* Increases responsiveness
* Greater flexibility

### Resource Needs

* Physical resource needs
* Load Testing
* Start as early as possible
* Generalize system function

### User Expectations

* Longer response times may be ok with large datasets
* Long response times my NOT be okay with time-sensitive transactions
* Be realistic about system capacity