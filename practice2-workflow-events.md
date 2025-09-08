# Practice 2: Basic Workflow Events

Create a simple workflow that responds to multiple GitHub events and tells you which event triggered it.

---

## Exercise: Event Name Detector

### Scenario
You want to create a workflow that can be triggered in different ways and shows you exactly which event caused it to run. This is useful for understanding GitHub Actions triggers and debugging workflows.

### Requirements

**Events to Handle:**
- `workflow_dispatch` - Manual trigger (you click "Run workflow" button)
- `push` - When code is pushed to any branch
- `pull_request` - When pull requests are created, updated, or closed

### Job Configuration

**Single Job:** `echo`
- **Runner:** `ubuntu-latest`
