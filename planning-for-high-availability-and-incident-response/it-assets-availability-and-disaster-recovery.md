# IT Assets, Availability and Disaster Recovery

**Disaster Recovery = Business Continuity = Prevent lost Revenue!**

* **Disaster:** anything that disrupts the normal flow of business
* **The goal for businesses:** minimize downtime

## Discovering IT Assests

### Assets

* Existing documentation
    * CMDB (Configuration management database)
    * Service catalog
    * Diagrams
* Breaking Down Infrastructure
    * Expand existing documents and fill in the missing pieces
    * Servers, storage arrays, load balancers, switches...
    * Databases
    * Even the small pieces matter! (Ex. SSH key)

### Business Critical Applications

* Any application that serves a critical function of the business
* How can you identify these critical applications?
    * Conduct a survey or job shadow different business units
        * Ask: does it make the business money?
        * Ask: if it goes down, what functions stop?
        * Ask: who or what units are impacted when it goes down?

## Consolidating IT Assets

### Why Consolidate?

* Cloud-centric
    * Many cloud resources are serverles or not-managetd
    * Cloud provider is consolidating resources on the backend
* Cost effective
    * Less cost, less underlying hardware, less software licensing and less manpower
    * With could: billed per hour or per transaction or per how may instances you are running
* Simpler management
    * Less work
    * Less dependencies and less failures
    * High complexity means higher skill sets of the admins, more ares for failure, more infrastructure to document
* Better availability
    * Cloud providers have HA built in to many servers
    * Move a single app running on a single server to a group of servers

### What to Consolidate?

* Similar departments
* Similar functions

### Example

* Current setup
    * 3 web servers running an HR application
    * 3 database servers serving the HR application
    * 3 web server serving the recruiting system
    * 3 database servers serving recruiting system
* Consolidated setup
    * 3 web servers running HR application
    * 3 database servers serving the HR application

### Cons of Consolidation

* You may not always know why the separation is there
* Resources dictate separation
* More risks: if one server fails, potentially more applications fail
