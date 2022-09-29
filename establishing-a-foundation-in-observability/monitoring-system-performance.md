# Monitoring System Performance

## System Monitoring

**Data aggregation & Centralization**

* Collecting metrics from IT infrastructure
    * Installing an exporter program to the collect information
    * Configuring the exporter program to start when the machine starts
* Storing it in one place
    * It makes it easy to manage and configure
    * You only need one tool to view data

**Dashboarding**

* Displaying the stored data
* Organizing the displayed data
* Forming logical groupings of data in charts
    * e.g., A chart for each metric--latency, saturation, errors, and traffic--displayed on one dashboard

**Alerting**

* Configuring alerting rules
    * Categorizing alerts into severity levels
    * Telling alerts when to fire
* Setting up notification groups
* Consuming a webhook in a team chat/communication program such as Slack
* Creating the alert message itself
    * What information should the alert contain?