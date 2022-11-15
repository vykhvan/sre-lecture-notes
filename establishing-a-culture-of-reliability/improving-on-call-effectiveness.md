# Improving On-call Effectiveness

## Introduction to Improving On-call Effectiveness

### Effective On-Calls

* Balanced between operational work and on-call work
* Have clear documentation for
    * Escalation
    * Incident management process
* A continuous process
    * Regularly review the quality of on-call life
    * Establish metrics for tracking goals

### Thoughts from an Expert

* Balanced on-call rotations
* Prepare for a messy start
* Prevent complacency
* Solid foundation of documentation is key
* Healthy culture is everything

## Incident Management

### When is an Incident?

To identify an incident, you should review the following metrics:

* **SLO/SLAs you have with customers (both internal and external)**
    * SLO/SLAs define your obligations to customers and the metrics for meeting those obligations.
    * Your team should be involved with creating the SLA/SLOs.
* **Actions necessary to correct an issue**
    * if an engineer has to make major changes to the system, it is most likely an incident. A major change includes things like reboots, rollbacks, configuration changes.
    * These major changes or actions need to be coordinated between different groups.
* **Time spent on correcting the issue**
    * Set a threshold for the max time for which an engineer can troubleshoot an issue before calling for backup.
    * Setting this threshold prevents issues from dragging on or becoming full-blown outages and promotes better on-call balance.
* **Data issues**
    * If there are any issues with data, it should immediately be declared an incident. You should ensure your customers' data is intact and secure.
    * Data issues include loss, corruption, and non-compliance.
        * Data loss: if data does not reach its destination, is not saved to disk, or is deleted by accident.
        * Data non-compliance: examples are data theft or inappropriate access.
* **Visibility**
    * If any external customer can see the effects of an issue, it is an Incident. For example, if customers would notice that a system is down, then it is an incident.

### Incident Management Process

* Incident commander
    * Notify the incident commander as soon as an incident is declared.
    * The incident commander's responsibilities include:
        * In charge of coordinating tasks and delegating duties.
        * Engage additional resources as necessary.
        * Initiate a central point of communication, i.e., a shared state document.
* Communications
    * There should also be a person dedicated to handling communications.
        * Is in charge of tracking the state of the incident.
        * Updates relevant stakeholders on the state of the incident.
* Engineers
    * The group performing operational work.
        * Should be the only group doing operation work.
    * Should have one engineer-in-charge coordinating work.

![image](img/incident-management-process.png)

### Benefits of Having a Clear Command Structure

* Keep everyone calm and focused
* Weel-thought-out actions better than snap decisions
* Easier to bring in additional resources

### Documenting an Incident

* Important Incident Documents
    * Live state document during incident
        * Provide the state of the incident
        * Reference for writing a post-mortem
    * Post-mortem

### Structure of a Live State Document

* Stakeholders
    * Everyone involved and those affected
        * Operations, communications, management, and the Incident Commander
    * Internal and external consumers
* Timeline
    * Actions
    * Communications
    * Alerts
    * Track things as they come in
    * Central location of events for cause-effect construction
* Summary
    * High-level summary for non-technical people
        * Update the executive management
        * Customer communications
    * Additional operational support: Good overview of the situation
* Technical Status Report
    * More technical and detailed status report
        * Get support team(s) up-to-speed
        * Centralize the state of affected systems
    * Review this section periodically
* Resolution Objectives
    * Align with your SLA or other metrics
    * Measurable objective with clear goal
    * Incident resolved
* Post-Incident Actions
    * Future steps for incident prevention
    * Basis for action plan in post-mortem
    * General fixes that should be implemented
