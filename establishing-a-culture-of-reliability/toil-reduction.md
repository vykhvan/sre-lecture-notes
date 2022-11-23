# Toil Reduction

## Identifying and Measuring Toil

### Identifying Toil

* **Repetitive**
    * Ask yourself, how frequently is the task done? Any task you are doing more than several times a week is probably toil.
    * How long does it take to do the task each time? Tasks that take up a good portion of time, even if they happen less frequently, are probably toil.
    * Is there a lot of effort involved in doing the task?
* **Manual**
    * Is human intervention necessary? If an event can be completely handled by a machine without the input of a human, and a person is handling it, then it is toil.
* **Automatable**
    * Any task with a clearly defined set of steps is probably automatable and is therefore toil.
    * You can prevent these types of toil from building up by automating from the start.
* **Stateless**
    * Does it accomplish something meaningful? If a task does not solve a long-term problem but rather just remedies an immediate symptom, then it probably is toil.
    * Is there a long-term and positive change in the end? If the system just returns to the status quo, the task probably is toil.

### Measuring Toil

* Time spent on toil tasks
* Number of toil tasks done

## Common Toil Reduction Strategies

* **System refactoring**
    * Reduce unnecessary redundancy. Some common ways to do so include
        * Condense similar services onto one host.
        * Migrate physical hosts to VMs.
* **Uniformity**
    * More uniform systems are easier to manage.
    * This is especially true if you are using automation and configuration management tools; you do not have to rewrite the same scripts to work on multiple systems.
* **Capacity planning**
    * Capacity planning is also a way of reducing toil.
    * Proper capacity planning allows systems to react to a wide range of demand and resource usage scenarios without human intervention.
* **Automation**
    * Automation is key to reducing toil. The more tasks machines can perform, the more time you have focus on reliability.
    * Automate tasks so that they can be triggered automatically whenever possible.

## Creating a Toil Reduction Plan

1. **Identify and measure toil**
    * Having an idea of the total amount of toil you are facing and measuring how much toil a particular task represents, you can establish a baseline for reviewing your progress later.
2. **Prioritize the tasks to reduce toil**
    * Perform cost-versus-benefit analysis to help prioritize the items.
    * Tasks that increase reliability should have greater priority.
3. **Decide on strategies for eliminating toil**
    * Each item may have several possible strategies.
    * You can also combine strategies depending on your individual circumstances.
4. **Plan for evaluating progress**
    * Evaluate your progress regularly.
    * Ensure that toil is actually decreasing.
    * Have concrete goals for each progress check.
    * Re-allocate resources as needed.
 
