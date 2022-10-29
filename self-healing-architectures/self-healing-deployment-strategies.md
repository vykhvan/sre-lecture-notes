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

## Rolling Back Deployments

### Rollback Deployment Scenarios

* Errors on deployment completion
* Broken functionality during deployment testing
* Rejected version

### Complications with Rollbacks & Databases

**Rollbacks that include databases must be critically assessed:**

* Deleted table rows
* Populated new tables
* Roll forward with backward compatible database changes

Rolling forward with backward compatible database changes is possible following the **Expand/Contract** method

![image](img/transition-period.png)
