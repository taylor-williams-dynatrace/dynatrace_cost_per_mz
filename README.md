# Dynatrace Cost per Management Zone Template

This repository contains a pre-built Workflow and Dashboard that can be used to summarize Dynatrace cost data by Management Zone for any time within your metrics retention period. 

While the core DQL query can be run ad-hoc, the nature of Dynatrace metrics granularity results in inaccurate cost results for any queries run beyond 14 days. DPS consumption is based on 15 minute increments of usage and to keep the query accurate with DPS consumption, the returned intervals must also be in 15 minute increments. Outside of 14 days, metric granularity increases to 1 hour (or more). This leads to the need to "summarize" results if you would like to run the query beyond 14 days. The worklfow in this repository provides a template to summarize daily cost records over a time period defined in the intial "js_set_parameters"  task.

**Included DPS Cost Objects
1. Full Stack Monitoring
2. Infrastructure Monitoring
3. Foundation and Discovery Monitoring
4. App-Only Monitoring
5. Platform as a Service Monitoring
6. Synthetic Browser Checks and Steps
7. Synthetic HTTP Checks

Follow these initial steps to get the workflow working in yours or your customer's environments:

## Adjust the "js_set_parameters" task

Depending on how far back you would like data summarized, adjust the "FROM_DAY" and "TO_DAY" settings on lines 3 and 4. For example, if I want to run an initial summary for the past 30 days, I would set "FROM_DAY" to 30 and "TO_DAY" to 0. These variables can be set back as far as the retention of your metrics are available.
