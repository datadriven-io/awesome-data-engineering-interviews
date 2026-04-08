# Awesome Data Engineering Interviews

> A curated set of real data engineering interview questions, with public solutions, drawn from FAANG, fintech, and data infrastructure interview reports. Maintained by [datadriven.io](https://datadriven.io).

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

Data engineering interviews test a different skill set than software engineering interviews: SQL fluency under pressure, the ability to reason about data quality, knowing when to use a window function vs a self-join, and being able to whiteboard a pipeline that breaks at 3 AM. The questions in this list are real patterns asked at companies that hire data engineers at scale.

Every problem links to a public, runnable version on datadriven.io with sample data and a built-in SQL or Python sandbox. **No login required.**

## Contents

- [The starter set](#the-starter-set)
  - [SQL](#sql) (11 questions)
  - [Python and PySpark](#python-and-pyspark) (11 questions)
  - [Data Modeling](#data-modeling) (3 questions)
  - [Pipeline Architecture](#pipeline-architecture) (3 questions)
- [How to use this list](#how-to-use-this-list)
- [What gets tested in a data engineering interview](#what-gets-tested-in-a-data-engineering-interview)
- [Beyond this list](#beyond-this-list)
- [Contributing](#contributing)
- [License](#license)

## The starter set

These are the 28 questions we recommend every data engineer solve before walking into an interview. They cover the patterns that show up in nearly every screen and onsite: window functions, deduplication, schema design, and pipeline architecture tradeoffs. There are hundreds more on [datadriven.io](https://datadriven.io) once you finish these.

### SQL

SQL questions test your ability to express set logic, handle null and duplicate edge cases, and reason about query execution. Most data engineering interviews are 60% SQL.

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 1 | [Spending by Account Status](https://datadriven.io/problems/spending_by_account_status) | Medium | Segment user spending and activity by account status across the platform |
| 2 | [Power Users by Session Activity](https://datadriven.io/problems/power_users_by_session_activity) | Medium | The growth team defines a power user as someone with more than 3 sessions and over 100 total page... |
| 3 | [Cloud Cost Trend Analysis](https://datadriven.io/problems/cloud_cost_trend_analysis) | Medium | The procurement team tracks cloud cost trends across billing periods. |
| 4 | [7-Check Rolling Average](https://datadriven.io/problems/7_check_rolling_average) | Medium | Compute a moving average over the last 7 entries. |
| 5 | [Average Spending by Account Status](https://datadriven.io/problems/average_spending_by_account_status) | Medium | Average per-user lifetime spending segmented by account status |
| 6 | [Content Recommendation Engine](https://datadriven.io/problems/content_recommendation_engine) | Medium | The content recommendations team wants to surface pages users haven't discovered yet. |
| 7 | [First-Day Session Retention](https://datadriven.io/problems/first_day_session_retention) | Hard | The growth team needs the first-day retention rate. |
| 8 | [Daily Spam Impression Rate](https://datadriven.io/problems/daily_spam_impression_rate) | Medium | Trust and safety wants the daily spam rate for ad impressions from users with page views. |
| 9 | [API Call Distribution Fraction](https://datadriven.io/problems/api_call_distribution_fraction) | Hard | The SRE team needs to see what fraction of total API calls each method and status combination rep... |
| 10 | [Longest Visit Streaks](https://datadriven.io/problems/longest_visit_streaks) | Hard | The growth team needs the top 3 users with the longest continuous daily visit streaks up to {{YEA... |
| 11 | [Previous Day Top Service](https://datadriven.io/problems/previous_day_top_service) | Hard | The daily revenue dashboard needs each date's top-spending service from the previous day. |

### Python and PySpark

Python questions in DE interviews focus on data transformation, streaming patterns, and the kinds of one-off scripts you write to debug a broken pipeline. Less algorithmic, more practical than a SWE interview.

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 12 | [Distribute Values Into Container Types](https://datadriven.io/problems/distribute_values_into_container_types) | Medium | Round-robin the values. Keep rotating. |
| 13 | [The Consecutive Sequence Finder](https://datadriven.io/problems/the_consecutive_sequence_finder) | Medium | Numbers that flow without interruption. |
| 14 | [The Record Reconciler](https://datadriven.io/problems/the_record_reconciler) | Medium | Two versions of the same truth. |
| 15 | [Merge Overlapping Time Ranges](https://datadriven.io/problems/merge_overlapping_time_ranges) | Medium | Intervals piling up. Clean the timeline. |
| 16 | [The Chunked Reader](https://datadriven.io/problems/the_chunked_reader) | Medium | Too big for memory. Read in pieces. |
| 17 | [The Dependency Resolver](https://datadriven.io/problems/the_dependency_resolver) | Medium | Everything depends on everything. |
| 18 | [Execution Timer Wrapper](https://datadriven.io/problems/execution_timer_wrapper) | Medium | Function wrapped with a timer. Duration captured on exit. |
| 19 | [The Eviction Policy](https://datadriven.io/problems/the_eviction_policy) | Medium | Fixed capacity. Oldest unused entry gets evicted. |
| 20 | [The Hierarchy Builder](https://datadriven.io/problems/the_hierarchy_builder) | Hard | Parent-child pairs, flat. Build the family tree. |
| 21 | [The Change Data Capture](https://datadriven.io/problems/the_change_data_capture) | Hard | Inserts, updates, deletes :  all present. |
| 22 | [Stream-Process a Large CSV](https://datadriven.io/problems/stream_process_a_large_csv) | Hard | Too big to load. Read what you can. |

### Data Modeling

Data modeling questions ask you to design schemas (star, snowflake, slowly-changing dimensions) and reason about tradeoffs between normalization, query performance, and storage cost.

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 23 | [Customer Address History](https://datadriven.io/problems/customer_address_history) | Easy | People move. Sometimes twice in a month. How do you remember where everyone was, and when? |
| 24 | [Social Platform Data Model](https://datadriven.io/problems/social_platform_data_model) | Medium | Follows, posts, likes, replies to replies. The interactions never stop and they all connect. |
| 25 | [Ride-Sharing Platform Schema](https://datadriven.io/problems/ride_sharing_platform_schema) | Medium | People need rides, drivers need fares, and someone needs to keep track of it all. |

### Pipeline Architecture

Pipeline architecture questions are open-ended whiteboard problems: design an ETL system, choose batch vs streaming, handle late-arriving data, recover from failure. These are the questions that separate senior data engineers from juniors.

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 26 | [Hourly ETL Pipeline with Consistency](https://datadriven.io/problems/hourly_etl_pipeline_with_consistency) | Medium | Design an ETL pipeline that loads data every hour with consistency and reliability. |
| 27 | [Database Replication and Schema Normalization Pipeline](https://datadriven.io/problems/database_replication_and_schema_normalization_pipeline) | Medium | Design a pipeline to replicate a production database to an analytics system, normalizing and comb... |
| 28 | [Gaming Event Pipeline: Streaming vs Batch Architecture Decision](https://datadriven.io/problems/gaming_event_pipeline_streaming_vs_batch_architecture_decision) | Medium | Design a gaming event pipeline for a major console platform and justify the streaming vs batch ar... |

## How to use this list

**If you have 4 or more weeks before your interview**: work through every question in order. Each section builds on the last. Start with SQL, move to Python, then schema design, then end with the open-ended pipeline architecture problems.

**If you have 1 to 2 weeks**: focus on SQL and pipeline architecture. SQL because it appears in nearly every screen, pipeline architecture because seniors are often differentiated on this round.

**If you have 48 hours**: skim every prompt, identify the patterns you have not seen before, and solve only those. The goal is pattern recognition, not muscle memory.

**If you are stuck on a question**: read the prompt, attempt a solution, then check the discussion. The solution that works is usually less interesting than the trap that almost worked.

## What gets tested in a data engineering interview

Different from a SWE interview in three ways:

1. **SQL is the primary language.** Expect 60 to 80 percent of your screen and onsite to be SQL. Window functions, CTEs, self-joins, and date arithmetic show up constantly.
2. **Data quality matters as much as correctness.** Interviewers will introduce duplicate rows, null values, late-arriving data, and timezone gotchas. Catching the trap is half the score.
3. **You will be asked to discuss tradeoffs**, not just write code. Why this join? What happens if this table grows 10x? How would you make this incremental? These questions separate seniors from juniors.

Topics that appear in nearly every onsite:

- Window functions (ROW_NUMBER, LAG and LEAD, RANK, running aggregates)
- Deduplication and idempotency
- Slowly-changing dimensions (Type 1 vs Type 2)
- Star vs snowflake schema tradeoffs
- Batch vs streaming pipeline design
- Backfill and recovery strategies
- Data partitioning and clustering
- Cost-aware query optimization

## Beyond this list

When you finish the starter set, [datadriven.io](https://datadriven.io) has hundreds more questions across every domain:

- [Browse all problems](https://datadriven.io/problems) - 850+ SQL, 380+ Python, and 100+ pipeline architecture questions
- [Mock interviews](https://datadriven.io/interview) - Company-specific question packs (Snowflake, Airbnb, Stripe, Datadog, and more)
- [Learning paths](https://datadriven.io/learn) - Foundational concepts: query structure, data modeling, pipeline architecture
- [Daily challenge](https://datadriven.io/daily) - One new data engineering interview question every day
- [Discussion](https://datadriven.io/discuss) - Interview reports and solutions from other DEs

## Contributing

This list is curated. To suggest a question for inclusion, open an issue with:

- The pattern the question tests
- A real source (interview report, blog, or your own experience)
- Why it belongs in the starter set rather than the long tail

## License

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). You may share and adapt this list for any purpose, including commercially, as long as you give appropriate credit to datadriven.io.
