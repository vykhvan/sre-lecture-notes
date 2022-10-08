# SLOs and SLIs

## Application measurements = business performance

* Scenario 1: results need to be returned within 2.5s to win users over
    * SLO - 90% of requests less than 2.5 seconds
    * SLI - # requests below 2.5 seconds / total # requests
* Scenario 2: customers will wait on average 5s to filter a result
    * SLO - 99% results return within 5 seconds
    * SLI - # requests below 5 seconds / total # requests

## What are SLOs and SLIs

* **Service Level Objectives (SLOs)** - They are objectives a business sets.
    * Example SLO: 99% availability of a website.
* **Service Level Indicators (SLIs)** - They are service level indicators. They are how we measure SLOs.
    * Example SLI: total number of successful requests.
* **Service Level Agreements (SLAs)** - legal agreements between clients and providers about consequences and guarantees of a service.
    * Example SLA: 5 9's of availability or 99.999% uptime guarantee.

**SLO in comparison to SLAs:**
    
* SLO detail specific objectives such as 99% availability
* SLOs do NOT define what happens when the objective isn't met
* SLOs/SLIs do not deal with underlying hardware metrics generally such as CPU and memory usage
* SLOs/SLIs measure application performance such as database query transactions 

**More SLOs and SLIs Examples**

* SLO #1: Data change rate of 5% over 60 minutes
    * SLI: data_change_rate > 5% [60m]
* SLO #2: API responds to external requests in less than 50ms over the last 5 minutes
    * SLI: http_response_latency  < 50ms [5m]
* SLO #3: Search results average return within 3 seconds over the last 60 minutes
    * SLI: search_query_return_time < 3s [60m]
* SLO #4: Application errors out less than 5 times in 1 minute
    * SLI: application_crashes < 5 times [1m]