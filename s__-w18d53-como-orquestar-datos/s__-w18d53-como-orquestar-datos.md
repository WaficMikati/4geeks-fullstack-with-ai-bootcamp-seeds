# Course Outline: How to Orchestrate Data

**Title:** How to Orchestrate Data
**Skill:** __ — Skill x: Model debugging and integration
**Learnpack:** + ¿Cómo orquestar datos?
**File:** s__-w18d53-como-orquestar-datos
**Prerequisite:** Background processing (cronjobs, triggers), data pipelines, ETL concepts
**Target Audience:** Beginner developers who need to keep their data pipelines running automatically and reliably
**Total Lessons:** 8
**Format:** Mixed (12.5% hands-on)

---

## Course Description

A pipeline that runs once is a script. A pipeline that runs reliably, on schedule, and monitors its own health is an orchestrated system. This course explains what data orchestration means, how it differs from a plain cronjob or script, and how to build and monitor a Python pipeline that runs each step in sequence, checks its own output, and reports status. Students finish by writing a small orchestration script that demonstrates the core loop: run → validate → log → repeat.

---

## Course Philosophy

This course emphasizes:
- Understanding WHY orchestration exists before learning HOW to implement it
- Building monitoring and logging habits from the start — not as afterthoughts
- Pragmatic orchestration: a well-structured Python script is often sufficient before reaching for heavy tools

---

## Course Statistics Summary

| Section | Lessons |
|---------|---------|
| 00 - Welcome | 1 |
| 01 - Data Orchestration | 2 |
| 02 - Monitoring Pipelines | 3 |
| 03 - Assessment | 1 |
| 04 - Outro | 1 |
| **Total** | **8** |

---

### 00.0 Keeping Your Data Pipeline Running 📖

**Learning Objectives:**
- Explain the gap between a one-time script and a production-grade pipeline
- Describe what orchestration adds to a data pipeline

**Content Outline:**
- The problem: a script runs manually once and produces data — but what happens next week?
- What makes a pipeline "production-grade": scheduling, error handling, logging, monitoring
- Orchestration as the answer: coordinating when things run, in what order, and how failures are handled
- Overview of what this course covers

**Transitions:**
This lesson frames the need. Section 01 explains what orchestration is and what tools exist.

**Key Principles:**
- A pipeline without monitoring is a blind pipeline — you don't know if it ran or failed
- Orchestration is the practice of making pipelines reliable and observable over time

**Examples:**
- A daily ETL job that extracts sales data, transforms it, and loads it to a data warehouse — but it silently fails every Tuesday when the source API is slow
- With orchestration: the job is scheduled, retried on failure, and sends an alert if it hasn't completed by 7am

---

### 01.0 Data Orchestration 📖

**Learning Objectives:**
- Define data orchestration and explain what it adds beyond a plain cronjob or script
- Describe the key concepts of a DAG-based orchestrator: tasks, dependencies, DAGs
- Preview what lesson 01.1 covers (orchestration tools in practice)

**Content Outline:**
- **What orchestration means:** coordinating the sequence, timing, and dependencies of pipeline steps
- **Beyond cronjobs:** cronjobs run scripts on a schedule; orchestrators also track state, handle failures, retry, log, and alert
- **DAG (Directed Acyclic Graph):** a way to model tasks and their dependencies — task A must complete before task B starts
  - "Directed" = there's a direction of flow
  - "Acyclic" = no circular dependencies
- **Key orchestration concepts:** task, dependency, run, success/failure, retry, alert
- **When plain Python or cronjobs are enough:** for simple, low-stakes pipelines with 1-3 steps

**Transitions:**
Now you know what orchestration is. Lesson 01.1 looks at real orchestration tools and their core patterns.

**Key Principles:**
- Orchestration is not a technology — it's a discipline. You can orchestrate with a simple Python script or with Airflow
- The right tool depends on pipeline complexity: simple pipelines don't need Airflow

**Examples:**
- A DAG: Extract (task 1) → Validate (task 2) → Transform (task 3) → Load (task 4)
- Task 2 cannot start until task 1 succeeds; if task 1 fails, tasks 2–4 are skipped

---

### 01.1 Orchestration in Practice 📖

**Learning Objectives:**
- Compare plain Python scripts, cronjobs, and dedicated orchestration tools as pipeline coordination mechanisms
- Identify when each approach is appropriate
- Describe how Airflow and Prefect work conceptually (DAG definition, task execution, UI)

**Content Outline:**
- **Plain Python script:** simplest orchestration — tasks are functions called in sequence; logging is manual; no retries
  - Use when: 1-3 steps, runs daily or less, error tolerance is high
- **Cronjob:** adds scheduling; script still runs sequentially but on a timer
  - Use when: the pipeline is stable and failures are acceptable; no dependency tracking needed
- **Airflow (conceptual):** DAG defined in Python; Airflow scheduler runs tasks on workers; UI shows run history, failures, retries
  - Strengths: battle-tested, rich UI, extensive integrations
  - Weaknesses: heavy to set up; overkill for small teams
- **Prefect (conceptual):** Python-native orchestration; tasks and flows are Python functions with decorators; cloud or self-hosted
  - Strengths: lightweight, developer-friendly, easy to add to existing Python code
  - Use when: team is Python-first and doesn't need Airflow's ecosystem
- **Practical starting point:** begin with a well-structured Python script, add logging and error handling; only add a dedicated orchestrator when the pipeline complexity demands it

**Transitions:**
You know the tools. Section 02 focuses on monitoring — knowing whether your pipeline ran, whether it produced good output, and what to do when things go wrong.

**Key Principles:**
- The best orchestration tool is the one your team will actually use and maintain
- Complexity in your orchestration system adds maintenance burden — start simple

**Examples:**
Orchestration decision tree:
- 1-2 steps, monthly run → plain Python script
- 1-3 steps, daily run → cronjob
- 3+ steps, daily run, need retry + alerting → Prefect
- Enterprise, many teams, complex dependencies → Airflow

---

### 02.0 Monitoring Pipelines 📖

**Learning Objectives:**
- Explain what pipeline monitoring means and why it matters
- List the key signals to monitor: execution time, failure rate, data freshness, SLA compliance
- Preview the metrics and hands-on content in lessons 02.1 and 02.2

**Content Outline:**
- **What monitoring means:** tracking pipeline health over time — not just whether it ran, but whether it produced useful output
- **Why monitoring matters:** silent failures are the worst kind — the pipeline appears to run but the output is wrong or stale
- **Key signals to monitor:**
  - **Execution time:** did it complete in the expected window?
  - **Data freshness:** was output produced recently enough?
  - **Error rate:** what fraction of runs failed this week?
  - **Output quality:** does the output pass basic validation (row count, nulls, value ranges)?
- **SLA (Service Level Agreement):** a commitment about when the pipeline will produce output — e.g., "sales data available by 7am every day"
- Overview of 02.1 (health metrics) and 02.2 (hands-on monitoring script)

**Transitions:**
This overview establishes WHY you monitor. Lesson 02.1 goes deeper into which metrics to track and how to define thresholds.

**Key Principles:**
- A pipeline that runs but produces stale or wrong data is worse than a pipeline that fails loudly — at least a loud failure tells you something is wrong
- Monitoring is part of the pipeline, not an afterthought

**Examples:**
- A sales pipeline runs at midnight but takes 4 hours. Data is available at 4am. The SLA is 7am. Everything is fine.
- The same pipeline now takes 6 hours. Data arrives at 6am. Still fine. Next week: 9 hours. SLA is missed. Alerts fire.
- Without monitoring: no one notices until an analyst reports that today's dashboard is blank.

---

### 02.1 Pipeline Health Metrics 📖

**Learning Objectives:**
- Define and calculate four key pipeline health metrics: run duration, success rate, data freshness, and output row count
- Set meaningful thresholds for each metric
- Explain the difference between alerting on individual failures vs patterns

**Content Outline:**
- **Run duration:** how long does the pipeline take? Establish a baseline; alert when it exceeds 2× baseline
  - Track as: `end_time - start_time` per run
- **Success rate:** what percentage of scheduled runs completed successfully?
  - Track weekly: if success rate drops below 80%, investigate root cause
- **Data freshness:** when was the output last updated? The pipeline may have run, but the output might not have changed
  - Critical for downstream consumers: analysts, dashboards, models
- **Output row count:** does the output have the expected number of rows? A sudden drop from 10,000 rows to 50 rows is a signal
  - Set min/max bounds from historical data
- **Alerting strategy:**
  - Individual failure: log it, retry once, then alert if the retry also fails
  - Pattern: if 3 consecutive runs fail → page someone
  - Avoid alert fatigue: don't alert on every transient failure

**Transitions:**
With metrics defined, lesson 02.2 builds a Python script that implements the run → validate → log → status cycle.

**Key Principles:**
- A metric without a threshold is just noise — always define what "good" and "bad" look like before you start collecting
- Alert on patterns, not individual events — one failed run is noise; three consecutive failures is a problem

**Anti-patterns:**
- **Logging success only:** failures must also be logged with enough context to diagnose the root cause
- **Alerting on every failure:** this produces alert fatigue — engineers stop responding

**Examples:**
Pipeline health dashboard snapshot:
| Metric | This Week | Last Week | Threshold |
|---|---|---|---|
| Success rate | 86% | 100% | > 80% |
| Avg duration | 47 min | 43 min | < 90 min |
| Freshness (hours since last update) | 2.1h | 1.8h | < 6h |
| Avg output rows | 9,847 | 10,123 | 8,000–12,000 |

---

### 02.2 Building a Pipeline Monitor 💻

**Challenge Prompt:**
Write a Python script that orchestrates three pipeline steps in sequence (extract, transform, load), validates each step's output count, and prints a final status summary showing which steps passed and which failed.

**Solution Code:**
```python
import random

def extract():
    print("Extracting data...")
    rows = random.randint(90, 110)
    return rows

def transform(rows):
    print(f"Transforming {rows} rows...")
    transformed = int(rows * 0.95)
    return transformed

def load(rows):
    print(f"Loading {rows} rows...")
    return rows

def validate(step, rows, min_rows=80):
    passed = rows >= min_rows
    status = "PASS" if passed else "FAIL"
    print(f"  [{status}] {step}: {rows} rows (min: {min_rows})")
    return passed

results = {}

raw = extract()
results["extract"] = validate("extract", raw)

transformed = transform(raw)
results["transform"] = validate("transform", transformed)

loaded = load(transformed)
results["load"] = validate("load", loaded)

print("\n--- Pipeline Status Summary ---")
for step, passed in results.items():
    print(f"{step}: {'OK' if passed else 'FAILED'}")
print(f"Overall: {'SUCCESS' if all(results.values()) else 'FAILURE'}")
```

**Challenge Code:**
```python
import random

def extract():
    print("Extracting data...")
    rows = random.randint(90, 110)
    return rows

def transform(rows):
    print(f"Transforming {rows} rows...")
    transformed = int(rows * 0.95)
    return transformed

def load(rows):
    print(f"Loading {rows} rows...")
    return rows

def validate(step, rows, min_rows=80):
    passed = rows >= min_rows
    status = "PASS" if passed else "FAIL"
    print(f"  [{status}] {step}: {rows} rows (min: {min_rows})")
    return passed

results = {}

# Step 1: run extract and validate its output
raw = extract()
results["extract"] = # your code here

# Step 2: run transform and validate its output
transformed = transform(raw)
results["transform"] = # your code here

# Step 3: run load and validate its output
loaded = load(transformed)
results["load"] = # your code here

# Step 4: print the summary
print("\n--- Pipeline Status Summary ---")
for step, passed in results.items():
    print(f"{step}: {'OK' if passed else 'FAILED'}")
print(f"Overall: {'SUCCESS' if all(results.values()) else 'FAILURE'}")
```

---

### 03.0 Data Orchestration Assessment 🧠

**Learning Objectives:**
- Demonstrate understanding of orchestration concepts and when to use them
- Correctly interpret pipeline monitoring metrics
- Identify alert fatigue anti-patterns and propose better alternatives

**Question Format:** Multiple choice

**Questions:**

1. What is the key difference between a cronjob and a dedicated orchestrator like Airflow or Prefect?
   - a) Cronjobs run on Linux; Airflow runs on any OS
   - b) An orchestrator tracks task state, handles retries, manages dependencies, and provides visibility; a cronjob just runs a script on a schedule
   - c) Cronjobs are faster; orchestrators are slower but more reliable
   - d) Orchestrators replace cronjobs entirely; cronjobs should never be used

2. What does "data freshness" measure in pipeline monitoring?
   - a) How many rows the pipeline produced today
   - b) How recently the output was updated — whether consumers are getting current data
   - c) Whether the pipeline ran without errors
   - d) How fast the pipeline completed relative to its SLA

3. A pipeline has run 10 times this week. 3 runs failed. What is the success rate?
   - a) 30%
   - b) 70%
   - c) 75%
   - d) 80%

4. Your pipeline normally produces 10,000 rows. Today it produced 55 rows. What should happen?
   - a) Nothing — small fluctuations are normal
   - b) Log a warning but continue — row count is not a critical metric
   - c) Trigger an alert — a drop from 10,000 to 55 rows indicates a likely data quality or extraction failure
   - d) Increase the minimum row threshold to 100 and re-run

5. A team receives alerts for every single pipeline failure. Engineers start ignoring the alerts. What is this called and how should it be fixed?
   - a) Alert overload — fix by removing all alerts
   - b) Alert fatigue — fix by alerting on patterns (e.g., 3 consecutive failures) instead of individual failures
   - c) Monitoring failure — fix by adding more alerts
   - d) SLA breach — fix by extending the SLA window

6. When is a plain Python script with logging a sufficient orchestration solution?
   - a) Never — always use Airflow for production pipelines
   - b) Only if the pipeline runs once and never again
   - c) When the pipeline has 1-3 steps, runs infrequently, and failures are acceptable or easy to catch manually
   - d) Only if the team doesn't know Airflow

7. What does a DAG (Directed Acyclic Graph) represent in data orchestration?
   - a) A type of database optimized for pipelines
   - b) A graph of tasks and their dependencies, where tasks flow in one direction with no circular loops
   - c) A monitoring dashboard that shows pipeline run history
   - d) A Python library for scheduling jobs

**Evaluation Criteria:**
- 7/7: Excellent — strong grasp of orchestration and monitoring concepts
- 5–6/7: Good — minor gaps in metric interpretation or tool selection
- 3–4/7: Needs review — revisit Sections 01 and 02
- Below 3/7: Restart recommended

**Score Interpretation:**
Questions map to: orchestrator vs cronjob (Q1), data freshness (Q2), success rate calculation (Q3), row count alerting (Q4), alert fatigue (Q5), when Python is enough (Q6), what a DAG is (Q7).

---

### 04.0 Your Pipeline Never Sleeps

**Content Outline:**
- Course recap: what students accomplished
  - Understood what orchestration adds beyond plain scripts and cronjobs
  - Learned key orchestration concepts: tasks, dependencies, DAGs
  - Compared Python scripts, cronjobs, Airflow, and Prefect
  - Defined pipeline health metrics: success rate, duration, freshness, row count
  - Set alerting thresholds and avoided alert fatigue anti-patterns
  - Built a pipeline monitoring script that runs, validates, and reports status
- Connection to bigger picture: every ML model depends on fresh, high-quality data arriving reliably — orchestration is what makes that possible
- Next steps: the next modules introduce CLIs and MCPs, which provide another layer of tooling for giving AI agents access to data and capabilities
- Resources for further exploration:
  - Apache Airflow documentation: airflow.apache.org
  - Prefect documentation: docs.prefect.io
  - "Designing Machine Learning Systems" (Chip Huyen) — data pipeline chapters
  - Great Expectations: open-source data validation framework
- Encouragement: a pipeline that runs reliably and alerts you when something goes wrong is engineering at its best — it frees you to focus on what matters

**Note:** This is conclusion only — no theory, exercises, or assessment.

---
