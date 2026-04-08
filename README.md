# Awesome Data Engineering Interviews

> The DataDriven 75. A curated set of 75 real data engineering interview questions, with public solutions, drawn from FAANG, fintech, and data infrastructure interview reports. Maintained by [datadriven.io](https://datadriven.io).

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

Data engineering interviews test a different skill set than software engineering interviews: SQL fluency under pressure, the ability to reason about data quality, knowing when to use a window function vs a self-join, and being able to whiteboard a pipeline that breaks at 3 AM. The 75 questions in this list are real patterns asked at companies that hire data engineers at scale.

Every problem links to a public, runnable version on datadriven.io with sample data and a built-in SQL or Python sandbox. **No login required.**

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

The DataDriven 75 is organized into 17 clusters across 4 tracks. Each cluster targets a specific pattern that interviewers test. Work through them in order, or jump to the section you need.

### SQL

SQL questions test your ability to express set logic, handle null and duplicate edge cases, and reason about query execution. Most data engineering interviews are 60% SQL.

#### Aggregation & Filtering

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 1 | [Spending by Account Status](https://datadriven.io/problems/spending_by_account_status) | Medium | Segment user spending and activity by account status across the platform |
| 2 | [Power Users by Session Activity](https://datadriven.io/problems/power_users_by_session_activity) | Medium | The growth team defines a power user as someone with more than 3 sessions and over 100 total page... |
| 3 | [Daily Spam Impression Rate](https://datadriven.io/problems/daily_spam_impression_rate) | Medium | Trust and safety wants the daily spam rate for ad impressions from users with page views. |
| 4 | [API Call Distribution Fraction](https://datadriven.io/problems/api_call_distribution_fraction) | Hard | The SRE team needs to see what fraction of total API calls each method and status combination rep... |
| 5 | [Active User Penetration Rate](https://datadriven.io/problems/active_user_penetration_rate) | Hard | The growth team defines an active user as one whose last session started within the last 30 days,... |

#### CTEs & Recursion

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 6 | [Flatten Org Chart Hierarchy](https://datadriven.io/problems/flatten_org_chart_hierarchy) | Hard | Traverse a tree structure with recursive queries. |
| 7 | [Full Funnel](https://datadriven.io/problems/full_funnel) | Hard | The funnel team wants users who engaged at every stage: searching, browsing, and buying. Find use... |
| 8 | [Funnel Leakage Report](https://datadriven.io/problems/funnel_leakage_report) | Hard | Build a multi-step conversion funnel with drop-off rates, broken down by tags. |
| 9 | [Monthly Cohort Retention](https://datadriven.io/problems/monthly_cohort_retention) | Medium | Compute month over month retention rates for user signup cohorts. |

#### JOINs & Subqueries

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 10 | [Average Spending by Account Status](https://datadriven.io/problems/average_spending_by_account_status) | Medium | Average per-user lifetime spending segmented by account status |
| 11 | [Content Recommendation Engine](https://datadriven.io/problems/content_recommendation_engine) | Medium | The content recommendations team wants to surface pages users haven't discovered yet. |
| 12 | [First-Day Session Retention](https://datadriven.io/problems/first_day_session_retention) | Hard | The growth team needs the first-day retention rate. |
| 13 | [Joined Employee Details](https://datadriven.io/problems/joined_employee_details) | Easy | Combine two related tables with a join. |
| 14 | [NULL Keys in Joins](https://datadriven.io/problems/null_keys_in_joins) | Easy | Understand why an inner join silently drops rows with NULL keys |

#### Window Functions

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 15 | [Cloud Cost Trend Analysis](https://datadriven.io/problems/cloud_cost_trend_analysis) | Medium | The procurement team tracks cloud cost trends across billing periods. |
| 16 | [7-Check Rolling Average](https://datadriven.io/problems/7_check_rolling_average) | Medium | Compute a moving average over the last 7 entries. |
| 17 | [Longest Visit Streaks](https://datadriven.io/problems/longest_visit_streaks) | Hard | The growth team needs the top 3 users with the longest continuous daily visit streaks up to {{YEA... |
| 18 | [Previous Day Top Service](https://datadriven.io/problems/previous_day_top_service) | Hard | The daily revenue dashboard needs each date's top-spending service from the previous day. |
| 19 | [Cumulative Sales Per Customer](https://datadriven.io/problems/cumulative_sales_per_customer) | Medium | Compute a running total of transactions per customer, ordered by transaction date. Reported from ... |

#### Date & Time Logic

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 20 | [7-Day Onboarding Conversion](https://datadriven.io/problems/7_day_onboarding_conversion) | Hard | The growth team is measuring onboarding-to-engagement conversion. |
| 21 | [Active Tokens on Target Date](https://datadriven.io/problems/active_tokens_on_target_date) | Medium | The compliance team needs to identify token owners who were active on November 1, {{YEAR}}. |
| 22 | [After Hours API Calls](https://datadriven.io/problems/after_hours_api_calls) | Medium | The compliance team needs to flag API calls made outside business hours in December {{YEAR}}. |
| 23 | [Average Response Time by Hour](https://datadriven.io/problems/average_response_time_by_hour) | Easy | The SRE team needs average response time broken down by hour of day, sorted chronologically. |
| 24 | [30-Day Page View Counts](https://datadriven.io/problems/30_day_page_view_counts) | Easy | Product analytics wants a quick engagement snapshot. |

#### NULL Handling & Dedup

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 25 | [Deduplicate and Keep Latest](https://datadriven.io/problems/deduplicate_and_keep_latest) | Medium | ROW_NUMBER dedup keeping latest row per key. |
| 26 | [Deduplicated Sales Volume by Category](https://datadriven.io/problems/deduplicated_sales_volume_by_category) | Medium | Deduplicate transactions, then sum sales per category. |
| 27 | [Distinct Blog Referrers](https://datadriven.io/problems/distinct_blog_referrers) | Easy | The analytics team needs a deduplicated list of all referrer sources for blog content. |
| 28 | [Distinct Chat Conversations](https://datadriven.io/problems/distinct_chat_conversations) | Medium | The messaging analytics team needs total unique conversations in chat_msgs. |
| 29 | [Duplicate DQ Check Records](https://datadriven.io/problems/duplicate_dq_check_records) | Medium | The data quality team suspects duplicate check entries. |

#### Set Ops & Pivots

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 30 | [Combined Cloud Spend by Region and Service](https://datadriven.io/problems/combined_cloud_spend_by_region_and_service) | Medium | The finance team needs total cloud spending for each combination of region and service, merging d... |
| 31 | [Experiment Conversion Pivot](https://datadriven.io/problems/experiment_conversion_pivot) | Medium | The A/B testing platform needs a pivot report of conversion outcomes by variant. |
| 32 | [Feature Name Intersection](https://datadriven.io/problems/feature_name_intersection) | Hard | The ML features team maintains feature names from two sources: 'training' and 'serving'. |
| 33 | [Push Notification Status Pivot](https://datadriven.io/problems/push_notification_status_pivot) | Medium | The notification analytics team needs a pivot showing push notification counts by status for each... |

### Python and PySpark

Python questions in DE interviews focus on data transformation, streaming patterns, and the kinds of one-off scripts you write to debug a broken pipeline. Less algorithmic, more practical than a SWE interview.

#### Data Processing & Transforms

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 34 | [The Record Reconciler](https://datadriven.io/problems/the_record_reconciler) | Medium | Two versions of the same truth. |
| 35 | [Merge Overlapping Time Ranges](https://datadriven.io/problems/merge_overlapping_time_ranges) | Medium | Intervals piling up. Clean the timeline. |
| 36 | [The Change Data Capture](https://datadriven.io/problems/the_change_data_capture) | Hard | Inserts, updates, deletes :  all present. |
| 37 | [Stream-Process a Large CSV](https://datadriven.io/problems/stream_process_a_large_csv) | Hard | Too big to load. Read what you can. |
| 38 | [The Column Transformer](https://datadriven.io/problems/the_column_transformer) | Easy | Each column gets its function. |

#### Data Structures & Iteration

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 39 | [Distribute Values Into Container Types](https://datadriven.io/problems/distribute_values_into_container_types) | Medium | Round-robin the values. Keep rotating. |
| 40 | [The Consecutive Sequence Finder](https://datadriven.io/problems/the_consecutive_sequence_finder) | Medium | Numbers that flow without interruption. |
| 41 | [The Eviction Policy](https://datadriven.io/problems/the_eviction_policy) | Medium | Fixed capacity. Oldest unused entry gets evicted. |
| 42 | [The Hierarchy Builder](https://datadriven.io/problems/the_hierarchy_builder) | Hard | Parent-child pairs, flat. Build the family tree. |
| 43 | [The File Tree Builder](https://datadriven.io/problems/the_file_tree_builder) | Medium | Flat paths. Build the nested tree. |

#### Functional Patterns & Generators

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 44 | [The Chunked Reader](https://datadriven.io/problems/the_chunked_reader) | Medium | Too big for memory. Read in pieces. |
| 45 | [The Dependency Resolver](https://datadriven.io/problems/the_dependency_resolver) | Medium | Everything depends on everything. |
| 46 | [Execution Timer Wrapper](https://datadriven.io/problems/execution_timer_wrapper) | Medium | Function wrapped with a timer. Duration captured on exit. |
| 47 | [The Throttle Wall](https://datadriven.io/problems/the_throttle_wall) | Hard | Stop the abusers. Let the rest through. |
| 48 | [The Timing Decorator](https://datadriven.io/problems/the_timing_decorator) | Medium | Wrap any function to capture how long it takes. |

#### Aggregation & Bucketing

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 49 | [Cumulative Sum](https://datadriven.io/problems/cumulative_sum) | Medium | Open-ended pattern |
| 50 | [Group Average](https://datadriven.io/problems/group_average) | Hard | Open-ended pattern |
| 51 | [Group By](https://datadriven.io/problems/group_by) | Medium | Open-ended pattern |
| 52 | [Null Counter](https://datadriven.io/problems/null_counter) | Easy | Open-ended pattern |
| 53 | [Running Distinct Count](https://datadriven.io/problems/running_distinct_count) | Medium | Open-ended pattern |

#### Merge & Reconcile

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 54 | [Merge Counters](https://datadriven.io/problems/merge_counters) | Medium | Open-ended pattern |
| 55 | [Merge Intervals](https://datadriven.io/problems/merge_intervals) | Hard | Open-ended pattern |
| 56 | [The Matching Manifest](https://datadriven.io/problems/the_matching_manifest) | Easy | Two warehouses, one shipment - only load what's in both. |
| 57 | [The Schema Diff](https://datadriven.io/problems/the_schema_diff) | Medium | Two versions of the same config - what changed between them? |
| 58 | [The Perfect Match](https://datadriven.io/problems/the_perfect_match) | Medium | Two numbers walk into an interview... |

#### Streaming & I/O

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 59 | [Batch Partitioner](https://datadriven.io/problems/batch_partitioner) | Medium | Open-ended pattern |
| 60 | [Parse Log Line](https://datadriven.io/problems/parse_log_line) | Medium | Open-ended pattern |
| 61 | [The Exception Handler](https://datadriven.io/problems/the_exception_handler) | Medium | Good code handles failure as gracefully as success. |
| 62 | [Permissions Manager](https://datadriven.io/problems/permissions_manager) | Medium | Manage user permissions with config updates. |
| 63 | [Char Profile](https://datadriven.io/problems/char_profile) | Medium | Open-ended pattern |

### Data Modeling

Data modeling questions ask you to design schemas (star, snowflake, slowly-changing dimensions) and reason about tradeoffs between normalization, query performance, and storage cost.

#### Normalization & ERDs

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 64 | [Customer Address History](https://datadriven.io/problems/customer_address_history) | Easy | People move. Sometimes twice in a month. How do you remember where everyone was, and when? |
| 65 | [Social Platform Data Model](https://datadriven.io/problems/social_platform_data_model) | Medium | Follows, posts, likes, replies to replies. The interactions never stop and they all connect. |
| 66 | [Ride-Sharing Platform Schema](https://datadriven.io/problems/ride_sharing_platform_schema) | Medium | People need rides, drivers need fares, and someone needs to keep track of it all. |

#### Star Schemas & Warehouses

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 67 | [Online Retail Star Schema](https://datadriven.io/problems/online_retail_star_schema) | Medium | Prices change, categories shift, and the BI team wants to slice revenue every way imaginable. |
| 68 | [POS Sales Data Warehouse](https://datadriven.io/problems/pos_sales_data_warehouse) | Medium | Every beep at every register across hundreds of locations. Coupons and returns make it messy. |
| 69 | [Movie Streaming Analytics Schema](https://datadriven.io/problems/movie_streaming_analytics_schema) | Medium | Someone pressed play. Did they finish? Did they skip the intro? Content licensing adds another tw... |

### Pipeline Architecture

Pipeline architecture questions are open-ended whiteboard problems: design an ETL system, choose batch vs streaming, handle late-arriving data, recover from failure. These are the questions that separate senior data engineers from juniors.

#### Batch vs. Streaming

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 70 | [Hourly ETL Pipeline with Consistency](https://datadriven.io/problems/hourly_etl_pipeline_with_consistency) | Medium | Design an ETL pipeline that loads data every hour with consistency and reliability. |
| 71 | [Database Replication and Schema Normalization Pipeline](https://datadriven.io/problems/database_replication_and_schema_normalization_pipeline) | Medium | Design a pipeline to replicate a production database to an analytics system, normalizing and comb... |
| 72 | [Gaming Event Pipeline: Streaming vs Batch Architecture Decision](https://datadriven.io/problems/gaming_event_pipeline_streaming_vs_batch_architecture_decision) | Medium | Design a gaming event pipeline for a major console platform and justify the streaming vs batch ar... |

#### ETL & Connectors

| # | Question | Difficulty | What it tests |
| --- | --- | --- | --- |
| 73 | [CDC Connector: Log-Based vs Trigger-Based](https://datadriven.io/problems/cdc_connector_log_based_vs_trigger_based) | Medium | Design a CDC-based replication connector and evaluate the tradeoffs between WAL/binlog and trigge... |
| 74 | [AWS Pipeline Auto-Scaling for Variable Volume](https://datadriven.io/problems/aws_pipeline_auto_scaling_for_variable_volume) | Hard | Design a cloud-native data pipeline on AWS that automatically scales to handle unpredictable data... |
| 75 | [City-Wide Bicycle Demand Forecasting Pipeline](https://datadriven.io/problems/city_wide_bicycle_demand_forecasting_pipeline) | Hard | Design a multi-source ingestion and feature pipeline that powers hourly bicycle demand prediction... |

## How to use this list

**If you have 4 or more weeks before your interview**: work through every question in order. Each cluster builds on the last. Start with SQL, move to Python, then schema design, then end with the open-ended pipeline architecture problems.

**If you have 1 to 2 weeks**: focus on the SQL track and pipeline architecture. SQL because it appears in nearly every screen, pipeline architecture because seniors are often differentiated on this round.

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
