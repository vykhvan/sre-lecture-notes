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

## Creating a Dashboard for Host Metrics

**Host Metrics include:**

* CPU
    * How busy the processor is at a given time.
* Memory
    * How much memory is free.
* Network I/O
    * How much throughput there is in sending and receiving data.
* Disk I/O
    * How much throughput there is writing to disk.

## Synthetic Monitoring Solutions

* Monitor an endpoint and tell us:
    * If the endpoint goes down
    * When the endpoint goes down
    * Any endpoint can be added
* Simulates what end-users see:
    * Saves embarrassment
    * Many solutions
    * Easy to build your own
    * Easy to set up and configure

## Creating Alerts for Application Metrics

Monitoring is nothing without alerts

**It' essential to:**

* Enable proper alerts to go to the appropriate teams
    * Ensure alerts are using the correct notification system (chat, e-mail, text)
* Configure alerts that will get you out of bed at 3 am.
    * Do not configure too many alerts. You will never sleep.
    * Keep alerting to a minimum. Too many alerts will cause you to ignore all of them.
    * Alert on symptoms of end-user pain.

**Good examples of alerts:**

* CPU at 90% or above for the last 10 minutes
* The disk is at 90% capacity
* Synthetic monitoring has returned a non-200 HTTP code for the last 5 minutes for our production website.

The first two highlight potential issues and allow enough time to fix them before any significant outages. The third will need to be addressed immediately.

**Bad examples of alerts:**

* CPU at 90% or above at all
* The disk is less than 90% capacity; There is time to correct this in a non-emergency setting.
* Synthetic monitoring has returned a single non-200 HTTP code for our production website.

These alerts can all wait. Although the CPU may go above 90%, it does not stay there. It could go above 90% 500 times in an hour. As long as it does not remain above 90% for a long time, I would consider that unimportant.

The same goes for synthetic monitoring; minor connectivity issues can happen a few times a day. You only want to be alerted if the network issue persists for a duration of time.
