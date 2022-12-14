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

## Maintaining an As-Built Document

### As-Build Document

* Constantly evolving as new things are added
* Document actual changes in the system/service/application

**As-Build Doc**

* Track actual changes as they happen
* Continuous: You add to it every time there is something new
* Features are added after being complete, but before being released

**Design Doc**

* Used as a template to build
* Static: Written before a feature is implemented
* Written before development starts and used to guide development

### Analyzing for Reliability

**Reliability assessment** A list of potential failures & mitigations

* Dependencies
    * Third-party library
    * Vendor
    * Database
* Physical resources
    * Things written to disk
    * Heavy user load; CPU maxed out
* Network
    * Internal network and redundancies
    * Bandwidth and latency

### Example of As-Built Document

--------------------------------------------

## <center>As-Built Doc Release 1</center>

### **Stakeholders**

* Developers
    * John Doe
    * Jane Peters
    * Sam Ross
* Ops
    * Jay Smith
* SRE
    * John Robert

### **Code Changes**

* Security fixes
    * Added new password requirements (Tk-100)
    * Fixed how SQL queries were handled (Tk-103)
* Feature additions
    * Added new menu options for users (Tk-102)
    * Users can now have middle names (Tk-101)

### **Data and System Changes**

* Data model changes
    * Added columns for middle names in user table (Tk-101)
    * Added additional New Menu table (Tk-102)
    * Users table was split into 2 smaller tables (Tk-101)

### **Design Decision Highlights**

Users table was split into two smaller tables to create more efficient queries and mappings. Keeping it as one big table began to cause slow queries. See Design Doc 132 for further discussion.

### **Test Section**

All test suites are passing 100%.

### **Deployment Notes**

The database admins asked for an additional set of scripts to be run for data corrections.

--------------------------------------------

## Performing a Launch Review

### Version Control

* Vital for managing changes in a system/application
* Implement safeguards
* Branching model and process for adding code
* Document process for future reference

### New release

* Nail down the release process
* Schedule
* Automation
* Document process

### Testing

* Build a solid testing plan
* Include functional and non-functional tests
* Identify testing blindspots
* Double-check your triage process
* Automate your test suite

### Build Process

* Schedule
    * On regualr schedule or triggered by events
    * Automate the build process
* Integration
    * Test to validate the code
    * Integration with version control
    * Deployment process
* Completed builds
    * Save every build or just specific builds

### Indentifying Reliability Risks

**System Risks**

* Connectivity: How system components "talk" to each other
* Compliance: Handling compliance needs
* Security: Ensuring data integrity

**Resource**

* Often overlooked as a reliability risk
* Review your monitoring setup for blind spots
* Organize monitored data in a logical way

**Monitoring**

* Have the correct amount of resources available
* Physical (CPU/RAM/storage)
* Networking (bandwidth/latency)

**Services**

* External
    * Potential impact of service outage and mitigations
    * Keep the contacts for each service vender
    * Create self-hosted mirrors where possible
* Internal
    * Redundancy with automated failover
    * Spread hosted services

### Launch Review Checklist

* Guide your launch process
* Flexible for any launch
* Review the entire system for reliability risks

1. Questions for guiding the important parts for review.
2. Action items to complete before launch.