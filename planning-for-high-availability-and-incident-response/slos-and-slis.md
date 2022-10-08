# SLOs and SLIs

## Application measurements = business performance

* Scenario 1: results need to be returned within 2.5s to win users over
    * SLO - 90% of requests less than 2.5 seconds
    * SLI - # requests below 2.5 seconds / total # requests
* Scenario 2: customers will wait on average 5s to filter a result
    * SLO - 99% results return within 5 seconds
    * SLI - # requests below 5 seconds / total # requests
