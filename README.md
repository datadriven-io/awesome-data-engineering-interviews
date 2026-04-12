# Awesome Data Engineering Interviews

> The DataDriven 75. A curated set of 75 real data engineering interview questions, organized by the patterns interviewers actually test. Maintained by [datadriven.io](https://datadriven.io).

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

Data engineering interviews test a different skill set than software engineering interviews: SQL fluency under pressure, the ability to reason about data quality, knowing when to use a window function vs a self-join, and being able to whiteboard a pipeline that breaks at 3 AM. The 75 questions in this list are real patterns asked at companies that hire data engineers at scale.

Every problem links to a public, runnable version on datadriven.io with sample data and a built-in SQL or Python sandbox. **No login required.**

## Related repositories

This repo is the **focused 75**. If you want broader coverage, see the sibling repos:

- **[data-engineering-interview-questions](https://github.com/datadriven-io/data-engineering-interview-questions)** for the full **1400+ question bank** across SQL, Python, schema design, and pipeline architecture.
- **[data-engineering-interview-handbook](https://github.com/datadriven-io/data-engineering-interview-handbook)** for the chapter by chapter **flagship handbook** with study plans and worked examples.
- **[awesome-data-engineering-interview](https://github.com/datadriven-io/awesome-data-engineering-interview)** (singular) for the broader curated **list of resources**: books, blogs, courses, tools, and external practice sites.
- **[data-engineer-interview-prep](https://github.com/datadriven-io/data-engineer-interview-prep)** for an **8 week structured practice schedule** with weekly problem sets.
- **[system-design-for-data-engineers](https://github.com/datadriven-io/system-design-for-data-engineers)** for **120 pipeline system design case studies**.
- **[data-engineering-cheatsheet](https://github.com/datadriven-io/data-engineering-cheatsheet)** for the **night before recall reference**.

## Contents

- [The 75](#the-75)
  - [SQL](#sql) (33 questions)
  - [Python and PySpark](#python-and-pyspark) (30 questions)
  - [Data Modeling](#data-modeling) (6 questions)
  - [Pipeline Architecture](#pipeline-architecture) (6 questions)
- [How to use this list](#how-to-use-this-list)
- [What gets tested in a data engineering interview](#what-gets-tested-in-a-data-engineering-interview)
- [Beyond the 75](#beyond-the-75)
- [Contributing](#contributing)
- [License](#license)

## The 75

SQL is the bulk of every DE screen, so the SQL track is the longest. Window functions, CTEs, and NULL handling are where most candidates lose points - the syntax is easy, the edge cases are not. Data modeling and pipeline architecture are interleaved into the SQL and Python tracks rather than saved for the end, because in real interviews you have to switch contexts cold and the only way to practice that is to do it.

### SQL

SQL questions test your ability to express set logic, handle null and duplicate edge cases, and reason about query execution. Most data engineering interviews are 60% SQL.

#### Aggregation & Filtering

GROUP BY, HAVING, conditional aggregation, and the difference between filtering rows (WHERE) versus filtering groups (HAVING). These are the warm-up questions in almost every SQL screen, used by interviewers to check that you can express a metric in one query without falling back to subqueries.

- [Spending by Account Status](https://datadriven.io/problems/spending_by_account_status)
- [Power Users by Session Activity](https://datadriven.io/problems/power_users_by_session_activity)
- [Daily Spam Impression Rate](https://datadriven.io/problems/daily_spam_impression_rate)
- [API Call Distribution Fraction](https://datadriven.io/problems/api_call_distribution_fraction)
- [Active User Penetration Rate](https://datadriven.io/problems/active_user_penetration_rate)

#### JOINs & Subqueries

Inner, left, anti, and self-joins, plus the choice between joining and using a subquery or EXISTS clause. The interviewer is watching whether you reach for the right join type for unmatched rows, whether you understand the row-explosion risk of fan-out joins, and whether you remember that NULL keys silently drop rows in inner joins.

- [Average Spending by Account Status](https://datadriven.io/problems/average_spending_by_account_status)
- [Content Recommendation Engine](https://datadriven.io/problems/content_recommendation_engine)
- [First-Day Session Retention](https://datadriven.io/problems/first_day_session_retention)
- [Joined Employee Details](https://datadriven.io/problems/joined_employee_details)
- [NULL Keys in Joins](https://datadriven.io/problems/null_keys_in_joins)

#### NULL Handling & Dedup

COALESCE, NULL-safe comparisons, ROW_NUMBER deduplication, and DISTINCT vs GROUP BY. Real production data is full of duplicates from at-least-once delivery and NULLs from optional columns; the interviewer wants to see you catch these traps without being prompted.

- [Deduplicate and Keep Latest](https://datadriven.io/problems/deduplicate_and_keep_latest)
- [Deduplicated Sales Volume by Category](https://datadriven.io/problems/deduplicated_sales_volume_by_category)
- [Distinct Blog Referrers](https://datadriven.io/problems/distinct_blog_referrers)
- [Distinct Chat Conversations](https://datadriven.io/problems/distinct_chat_conversations)
- [Duplicate DQ Check Records](https://datadriven.io/problems/duplicate_dq_check_records)

#### Date & Time Logic

Date arithmetic, day-of-week and hour bucketing, time-window filters, and timezone gotchas. These appear constantly in retention, cohort, and SLA queries, and they are the most common place where a candidate writes a query that looks right and is silently off by one day.

- [7-Day Onboarding Conversion](https://datadriven.io/problems/7_day_onboarding_conversion)
- [Active Tokens on Target Date](https://datadriven.io/problems/active_tokens_on_target_date)
- [After Hours API Calls](https://datadriven.io/problems/after_hours_api_calls)
- [Average Response Time by Hour](https://datadriven.io/problems/average_response_time_by_hour)
- [30-Day Page View Counts](https://datadriven.io/problems/30_day_page_view_counts)

#### Window Functions

ROW_NUMBER, RANK, LAG/LEAD, running aggregates, and partitioned ORDER BY. Window functions are the single highest-leverage SQL skill for data engineers because they replace clunky self-join patterns and unlock cohort, retention, and time-series queries.

- [Cloud Cost Trend Analysis](https://datadriven.io/problems/cloud_cost_trend_analysis)
- [7-Check Rolling Average](https://datadriven.io/problems/7_check_rolling_average)
- [Longest Visit Streaks](https://datadriven.io/problems/longest_visit_streaks)
- [Previous Day Top Service](https://datadriven.io/problems/previous_day_top_service)
- [Cumulative Sales Per Customer](https://datadriven.io/problems/cumulative_sales_per_customer)

#### CTEs & Recursion

WITH clauses for query layering, recursive CTEs for hierarchies and graphs, and cohort funnels built as multi-step CTEs. The interviewer is checking that you can decompose a complex query into readable steps and that you can traverse a parent/child relationship without flattening it manually.

- [Flatten Org Chart Hierarchy](https://datadriven.io/problems/flatten_org_chart_hierarchy)
- [Full Funnel](https://datadriven.io/problems/full_funnel)
- [Monthly Cohort Retention](https://datadriven.io/problems/monthly_cohort_retention)

#### Set Ops & Pivots

UNION, INTERSECT, EXCEPT, and conditional aggregation pivots that turn rows into columns. These show up when the interviewer wants a side-by-side comparison report or a cross-tab, and they test whether you reach for the simple set-operator solution instead of building multi-join workarounds.

- [Combined Cloud Spend by Region and Service](https://datadriven.io/problems/combined_cloud_spend_by_region_and_service)
- [Experiment Conversion Pivot](https://datadriven.io/problems/experiment_conversion_pivot)
- [Feature Name Intersection](https://datadriven.io/problems/feature_name_intersection)
- [Push Notification Status Pivot](https://datadriven.io/problems/push_notification_status_pivot)
- [Funnel Leakage Report](https://datadriven.io/problems/funnel_leakage_report)

### Python and PySpark

Python questions in DE interviews focus on data transformation, streaming patterns, and the kinds of one-off scripts you write to debug a broken pipeline. Less algorithmic, more practical than a SWE interview.

#### Data Structures & Iteration

Dictionaries, sets, defaultdicts, nested data, and the iteration patterns that turn raw records into lookups. These questions test whether you can pick the right structure on the first try - using a dict where a list of tuples would be O(n) per lookup is the kind of thing interviewers grade silently.

- [Distribute Values Into Container Types](https://datadriven.io/problems/distribute_values_into_container_types)
- [The Consecutive Sequence Finder](https://datadriven.io/problems/the_consecutive_sequence_finder)
- [The Eviction Policy](https://datadriven.io/problems/the_eviction_policy)
- [The Hierarchy Builder](https://datadriven.io/problems/the_hierarchy_builder)
- [The File Tree Builder](https://datadriven.io/problems/the_file_tree_builder)

#### Aggregation & Bucketing

Group-by counting, running totals, histograms, and bucket assignment without pulling in pandas. The interviewer wants to see whether you can do basic analytics in pure Python because in a real pipeline you often cannot import a heavy library into a Lambda or a streaming job.

- [Cumulative Sum](https://datadriven.io/problems/cumulative_sum)
- [Group Average](https://datadriven.io/problems/group_average)
- [Group By](https://datadriven.io/problems/group_by)
- [Null Counter](https://datadriven.io/problems/null_counter)
- [Running Distinct Count](https://datadriven.io/problems/running_distinct_count)

#### Streaming & I/O

Reading large files line-by-line, chunked CSV processing, parsing log lines, and writing partitioned output. These questions test whether you understand that loading a 50GB file into memory is not an option and that the right answer involves generators or batch iteration.

- [Batch Partitioner](https://datadriven.io/problems/batch_partitioner)
- [Parse Log Line](https://datadriven.io/problems/parse_log_line)
- [The Exception Handler](https://datadriven.io/problems/the_exception_handler)
- [Permissions Manager](https://datadriven.io/problems/permissions_manager)
- [Char Profile](https://datadriven.io/problems/char_profile)

#### Merge & Reconcile

Joining two record streams in Python, reconciling schema drift between two sources, and computing diffs between snapshots. This pattern is what every CDC, ETL, and dedup pipeline comes down to, and the interviewer is checking that you can write the merge correctly without reaching for a database.

- [Merge Counters](https://datadriven.io/problems/merge_counters)
- [Merge Intervals](https://datadriven.io/problems/merge_intervals)
- [The Matching Manifest](https://datadriven.io/problems/the_matching_manifest)
- [The Schema Diff](https://datadriven.io/problems/the_schema_diff)
- [The Perfect Match](https://datadriven.io/problems/the_perfect_match)

#### Functional Patterns & Generators

Generators, decorators, context managers, and higher-order functions like throttles and timers. These show up when the interviewer wants to see whether you can write reusable plumbing code - the kind of utility wrappers that make the difference between a clean pipeline and 200 lines of copy-pasted retry logic.

- [The Chunked Reader](https://datadriven.io/problems/the_chunked_reader)
- [The Dependency Resolver](https://datadriven.io/problems/the_dependency_resolver)
- [Execution Timer Wrapper](https://datadriven.io/problems/execution_timer_wrapper)
- [The Throttle Wall](https://datadriven.io/problems/the_throttle_wall)
- [The Timing Decorator](https://datadriven.io/problems/the_timing_decorator)

#### Data Processing & Transforms

Multi-step record transformation, schema cleanup, column-wise transforms, and pipeline-style composition of small steps. These questions test whether you can write code that is easy to extend and easy to debug when an upstream API changes its payload format.

- [The Record Reconciler](https://datadriven.io/problems/the_record_reconciler)
- [Merge Overlapping Time Ranges](https://datadriven.io/problems/merge_overlapping_time_ranges)
- [The Change Data Capture](https://datadriven.io/problems/the_change_data_capture)
- [Stream-Process a Large CSV](https://datadriven.io/problems/stream_process_a_large_csv)
- [The Column Transformer](https://datadriven.io/problems/the_column_transformer)

### Data Modeling

Data modeling questions ask you to design schemas (star, snowflake, slowly-changing dimensions) and reason about tradeoffs between normalization, query performance, and storage cost.

#### Normalization & ERDs

Designing normalized tables, picking primary and foreign keys, and modeling slowly-changing dimensions for entities like customers, addresses, and subscriptions. The interviewer is checking that you can think about update anomalies and history tracking, not just draw boxes.

- [Customer Address History](https://datadriven.io/problems/customer_address_history)
- [Social Platform Data Model](https://datadriven.io/problems/social_platform_data_model)
- [Ride-Sharing Platform Schema](https://datadriven.io/problems/ride_sharing_platform_schema)

#### Star Schemas & Warehouses

Fact and dimension tables, grain selection, conformed dimensions, and the tradeoffs between star and snowflake schemas. These appear in BI-heavy interviews and at any company where analysts and data engineers share a warehouse - the interviewer wants to see whether you can design for query performance and analyst ergonomics at the same time.

- [Online Retail Star Schema](https://datadriven.io/problems/online_retail_star_schema)
- [POS Sales Data Warehouse](https://datadriven.io/problems/pos_sales_data_warehouse)
- [Movie Streaming Analytics Schema](https://datadriven.io/problems/movie_streaming_analytics_schema)

### Pipeline Architecture

Pipeline architecture questions are open-ended whiteboard problems: design an ETL system, choose batch vs streaming, handle late-arriving data, recover from failure. These are the questions that separate senior data engineers from juniors.

#### Batch vs. Streaming

Choosing between batch and streaming for a given workload, handling late-arriving data, and designing for consistency and replay. These are open-ended whiteboard questions where the interviewer is grading the discussion as much as the diagram - they want to hear you reason about latency requirements, cost, and failure modes.

- [Hourly ETL Pipeline with Consistency](https://datadriven.io/problems/hourly_etl_pipeline_with_consistency)
- [Database Replication and Schema Normalization Pipeline](https://datadriven.io/problems/database_replication_and_schema_normalization_pipeline)
- [Gaming Event Pipeline: Streaming vs Batch Architecture Decision](https://datadriven.io/problems/gaming_event_pipeline_streaming_vs_batch_architecture_decision)

#### ETL & Connectors

Designing CDC connectors, incremental sync strategies, schema-drift handling, and auto-scaling pipelines for variable load. These are senior-level questions that test whether you have actually run a pipeline in production - the answer is never "use Airflow" and is always about how you recover from the moment something breaks at 3 AM.

- [CDC Connector: Log-Based vs Trigger-Based](https://datadriven.io/problems/cdc_connector_log_based_vs_trigger_based)
- [AWS Pipeline Auto-Scaling for Variable Volume](https://datadriven.io/problems/aws_pipeline_auto_scaling_for_variable_volume)
- [City-Wide Bicycle Demand Forecasting Pipeline](https://datadriven.io/problems/city_wide_bicycle_demand_forecasting_pipeline)

## How to use this list

**If you have 4 or more weeks before your interview**: work through every question in order. Each pattern builds on the last. Start with SQL, move to Python, then schema design, then end with the open-ended pipeline architecture problems.

**If you have 1 to 2 weeks**: focus on the SQL track and pipeline architecture. SQL because it appears in nearly every screen, pipeline architecture because seniors are often differentiated on this round.

**If you have 48 hours**: skim every pattern description, identify the patterns you have not seen before, and solve only those questions. The goal is pattern recognition, not muscle memory.

**If you are stuck on a question**: read the prompt, attempt a solution, then check the discussion. The solution that works is usually less interesting than the trap that almost worked.

## What gets tested in a data engineering interview

Different from a SWE interview in three ways:

1. **SQL is the primary language.** Expect 60 to 80 percent of your screen and onsite to be SQL. Window functions, CTEs, self-joins, and date arithmetic show up constantly.
2. **Data quality matters as much as correctness.** Interviewers will introduce duplicate rows, null values, late-arriving data, and timezone gotchas. Catching the trap is half the score.
3. **You will be asked to discuss tradeoffs**, not just write code. Why this join? What happens if this table grows 10x? How would you make this incremental? These questions separate seniors from juniors.

## Beyond the 75

When you finish the 75, [datadriven.io](https://datadriven.io) has hundreds more questions across every domain:

- [Browse all problems](https://datadriven.io/problems) - 850+ SQL, 380+ Python, and 100+ pipeline architecture questions
- [Mock interviews](https://datadriven.io/interview) - Company-specific question packs (Snowflake, Airbnb, Stripe, Datadog, and more)
- [Learning paths](https://datadriven.io/learn) - Foundational concepts: query structure, data modeling, pipeline architecture
- [Daily challenge](https://datadriven.io/daily) - One new data engineering interview question every day
- [Discussion](https://datadriven.io/discuss) - Interview reports and solutions from other DEs

## Contributing

This list is curated. To suggest a question for inclusion, open an issue with:

- The pattern the question tests
- A real source (interview report, blog, or your own experience)
- Why it belongs in the 75 rather than the long tail

## License

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). You may share and adapt this list for any purpose, including commercially, as long as you give appropriate credit to datadriven.io.
