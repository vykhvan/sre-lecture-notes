# Self-healing Deployment Strategies

## Deployment Strategies: Basic

Active services are brought down together and replaced with the new version

**Pros**
* Simple
* Fast
* Cheap

**Cons**
* High Risk
* Destructive, causes outages
* Not a best practice
* Not easy to rollback

**Usage scenarios:**
* Application is non-critical to the business or mission
* Deploying to a lower environment
* Application is not in use
* During off-hours
