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

## Defining Good SLOs

**Bad**
* Very generic and not specific
* Do not indicate an application is functioning properly
* Don't tell specifics about application performance

**Good**
* Have specific time frames and speficif goals
* Indicate a specific user experience goal such as application responsiveness

## Categories for SLOs

### Availability
* Availability means if the application is available to users
* SLO
    * Successful requests to the application
    * Health checks
* Ex: application is up 99% of time over the last 7 days
    * Specific goals: 99%
    * Specific time frame: 7 days
    * SLI: total # successful requests / total # requests

### Error Budget
* Error budget: how much the infrastructure is allowed or budgeted for to be down for a period of time
    * Include outages and maintenance
* 10% error budget means
    * Serve 10% failed requests (e.g. 10 fails if you only have 100 requests in month)
    * 90% **availability**
        * ```availability = 1 - error budget```
    * 40% **usage** of error budget if 4 errors has occured
        * ```usage = (error occured)/(error budget)```
    * 60% **usage remaining** if 4 errors has occured
        * ```usage remaining = 1 - error budget usage```
* SLO:
    * Looks at the number of failures, typically in percentage
    * Goal is to have low numbers
    * Can be displayed in remaining error budget
* Ex: Over the last 30 days have less than 10% of results return failures
    * Specific time frame: 30 days
    * Specific goal: 10% of results returned failures
    * SLI: number of error requests / total number of requests in budget

### Latency
* Latency: how fast you want your application to respond
* SLO:
    * Generally measured in milliseconds (ms)
    * Use a percentage of requests
    * Quantiles not averages
* Ex: 90% requests are served within 50ms
    * SLI: Histogram buckets
        * requests and associated latency
        * A 90th percentile over a 5 mins period shows the top 90% latency for requests over a 5 mins period

### Freshness
* Freshness: data being read is the freshest
    * Fastest and most accurate
* SLO:
    * Most recently writeen
* Ex: 90% of requests are being read from the cache or the most recent write over the last 5 minutes
    * SLI: percentage of requests read from the cache / requests not read from cache

### Correctness
* Correctness: the data returned by an application conforms to a good known dataset
* SLO:
    * Goal is to have a high percentage
* Ex: 99.9% of records compared are correct
    * SLI: count of all requests that are correct / count of all requests

### Throughput
* Throughput: how much can you site handle
* SLO:
    * Often measured in requests per seconds (RPS)
    * Sometimes target just successful requests
* Ex: site reaches 1000 RPS over the last 5 minutes
* Ex: (backend) database transaction stays above 1000 RPS over the last 10 minutes
* Ex: (backend) database transaction stays below 1500 RPS over tha last 15 minutes
* SLI: total number of requests over a period of time

### SLO/SLI Table

| Category | SLI | SLO |
|----------|-----|-----|
| Availability | Number of successful requests/total number of requests | 99% success |
| Latency | Bucket of requests in a histogram showing the 95th percentile over the last 30 seconds | 90% of requests < 50 ms |
| Throughput | Total number of requests | Maintain 1000 RPS |
| Error Budget | 1 - availability | 10% error budget |

## Implementing SLOs and SLIs

### Examples
* SLO: 90% availability
    * SLI: total number of successful requests / total number of requests
    * Successful web request? Anything that is 2xx
    * Query: ```http_request_total {code =~ "200"} / http_request_total```
* SLO: 90% of requests served within 50ms over the last 30 seconds
    * SLI: Bucket of requests in a histogram showing the 90th percentile over the last 30 seconds
    * ```histogram_quantile(0.90, sum(rate(http_request_duration_seconds_bucket{job="website"}[30s])) by (le, verb))```
* SLO: Throughput of 100 requests per second (RPS) over 5 minutes
    * SLI: total number of successful requests over 5 minutes
    * Query: ```sum(rate(http_request_total{code=~"2.."}[5m]))```
* SLO: Error Budget of 10% over 7 days
    * Error budget itself is static but how to display this can vary
    * Remaining percentage of the error budget or how much is left of your 10%
* Formulas:
    * ```% error occured = 1 - compliance = 1 - successful requests/total requests```
        * Ex: total of 100 requests and 97 are successful, so 97% are in compliance, 3% are erroneous
    * ```error budget = 1 - availability```
        * Ex: availability is 90%, so error budget is 10%
    * ```% error used = % error occured/error budget```
        * Ex: 3% error requests and the error budget is 10%, 30% of the error budget is used
    * ```% remaining error budget = 1 - % error used```
        * Ex: 30% of the error budget is used, meaning 70% of the error budget is remaining
    * Query: ```1 - ((1 - sum(increase(http_request_total{job="webserver", code="200"}[7d])) by (verb) / sum(increase(http_request_total{job="webserver"}[7d])) by (verb)) / (1 - .90))```
    