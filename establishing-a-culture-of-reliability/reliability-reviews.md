# Reliability Reviews

* Identify and prevent potential areas of failure
* Formal procedure for assessing and planning failure points
* Use known issues, launch reviews, and as-built docs
* Assess impact and ways to mitigate potential failures

## Documenting New Feature Design

### Documenting Features

* New features introduce risks
* Important to document new features
    * New feature: New addition to your system/service/application
* Key things when documenting design:
    * Stakeholders
    * Resource needs
    * Dependencies
    * Feature Design

### Stakeholders

* Developers
    * Developed the feature
    * Have a deep understanding of the feature
    * Consult them if the feature causes issues
* Maintainers
    * Responsible for the feature going forward
    * May or may not be the same group that developed the feature

### Resource Needs

* Resource needs
    * Physical resources: RAM, CPU, disk space
    * Network resources: Sending and receiving data
    * General: E.g., DNS names, firewall rules
* Small changes can have cumulative effects

### Dependencies

**Internal Dependencies**

* Things within your company:
    * Self-hosted servers: Database, caches, web, etc.
    * Private networking
    * In-house libraries

**External Dependencies**

* Examples:
    * Outside services: DNS, CDNs, cloud providers
    * Third-party libraries
    * Vendor support

### Design

* The actual design of the feature
    * Architectural diagrams
    * Data model: API, database, etc.
    * Sub-components
    * Feature limitations
