# Clockwork
Recurring batch data pipelines are a staple of the modern enterprisescale data warehouse. As a data warehouse scales to support more products and services, a growing number of interdependent pipelines running at various cadences can give rise to periodic resource bottlenecks for a cluster. This resource contention results in pipelines starting at unpredictable times each day and consequently variable landing times for the data artifacts they produce. The variability gets compounded by the dependency structure of the workload, and the resulting unpredictability can disrupt the project workstreams which consume this data. We present Clockwork, a delay-based global scheduling framework for data pipelines which improves landing time stability by spreading out tasks throughout the day. Whereas most scheduling algorithms optimize for makespan or average job completion times, Clockwork’s execution plan optimizes for stability in task completion times while also targeting predifined pipeline. Online experiments comparing this novel scheduling algorithm and a previously proposed greedy procrastinating heurstic show tasks complete almost an hour earlier on average, while exhibiting lower landing time variance and producing significantly less competition for resources in a target cluster.

## What is Included?
As part of this repo we plan to include examples of our core planning logic as well as a few of our scheduling algorithms.  

## Examples
```
> python3 main.py
DEBUG:asyncio:Using selector: EpollSelector
DEBUG:algorithm.algorithm:Presto Metadata Size 3
DEBUG:algorithm.right_based.algorithm:Scheduled 0/3, 0 accepted
DEBUG:algorithm.algorithm:Presto Plan Size 3
DEBUG:algorithm.algorithm:Spark Metadata Size 3
DEBUG:algorithm.right_based.algorithm:Scheduled 0/3, 0 accepted
DEBUG:algorithm.algorithm:Spark Metadata Size 2
DEBUG:planner.planner:Planning Finished | In Plan: 5 | Missing from Plan: 1
DEBUG:planner.plan_writer:Final Plan: {TaskInstance(task_id='task6', period_id=Timestamp(10)): Timestamp(60), TaskInstance(task_id='task3', period_id=Timestamp(0)): Timestamp(100), TaskInstance(task_id='task5', period_id=Timestamp(10)): Timestamp(35), TaskInstance(task_id='task2', period_id=Timestamp(0)): Timestamp(40), TaskInstance(task_id='task1', period_id=Timestamp(0)): Timestamp(20)}
```


## Requirements

See the [CONTRIBUTING](CONTRIBUTING.md) file for how to help out.

## License
Clockwork is MIT licensed, as found in the LICENSE file.
