# Background Jobs Pattern

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describes how to create and manage background jobs correctly in this codebase.

## How to Fill This Out

This pattern should describe the **mechanics** of creating, queuing, and executing background jobs. It should ensure jobs are reliable and observable.

### What to Find

1. **Which Files to Touch**
   - Where do job definitions live?
   - Where is job queue configuration?
   - Any job processing infrastructure?

2. **What Sequence to Follow**
   - How to define a new job
   - How to queue a job
   - How to process jobs
   - How to handle failures
   - How to monitor jobs

3. **Common Mistakes to Avoid**
   - Job failure handling
   - Retry logic mistakes
   - Resource cleanup issues
   - Dead letter queue handling

4. **How to Verify Correctness**
   - How to test jobs locally
   - How to verify job execution
   - How to monitor job health
   - What to check in production

5. **Examples**
   - Example job definition
   - Example of queuing a job
   - Example of job processing
   - Error handling example

### How to Scan

- Search for job/queue libraries in `package.json` (Bull, BullMQ, SQS, etc.)
- Look for job directories (`jobs/`, `workers/`, `queues/`, `src/jobs/`, etc.)
- Find job definition examples (how jobs are structured)
- Search for job queuing patterns (how jobs are triggered)
- Look for job processing infrastructure (workers, processors)
- Check for job monitoring or dashboard setup
- **Note:** If no background job system exists, document that and explain when one might be needed

### Pattern Structure

```
## Overview
Brief description of the job system

## Job Queue System
- What queue system? (Bull, BullMQ, SQS, etc.)
- Where is it configured?
- How are jobs persisted?

## Creating a Job
1. Define job handler
2. Define job payload type
3. Add error handling
4. Add logging
5. Register job processor

## Queuing a Job
- How to queue from API
- How to queue from background process
- Job options (retries, delays, etc.)

## Processing Jobs
- How workers are started
- Concurrency settings
- Job execution flow

## Error Handling
- Retry logic
- Failure handling
- Dead letter queue
- Alerting

## Monitoring
- How to monitor job health
- Metrics to track
- Logging requirements

## Common Mistakes
- Not handling failures
- Missing idempotency
- etc.
```

### Key Rule

Patterns never contain feature intent. They describe *implementation mechanics only*.

This pattern should work for any background job, regardless of what feature it's for.

---

## Your Content Goes Here

Replace this section with your actual background jobs pattern extracted from the codebase.

