<h1 align="center">Awesome Data Engineering Interviews <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a></h1>

<p align="center">
  The DataDriven 75. A focused, hand picked set of 75 real data engineering interview questions, organized by the patterns interviewers actually test.
</p>

<p align="center">
  <a href="https://github.com/datadriven-io/awesome-data-engineering-interviews/stargazers"><img src="https://img.shields.io/github/stars/datadriven-io/awesome-data-engineering-interviews?style=flat&color=ffd33d" alt="Stars"></a>
  <a href="https://creativecommons.org/licenses/by/4.0/"><img src="https://img.shields.io/badge/license-CC%20BY%204.0-blue.svg" alt="License"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
  <a href="https://datadriven.io"><img src="https://img.shields.io/badge/sandbox-datadriven.io-9333ea.svg" alt="Sandbox"></a>
</p>

<p align="center">
  <a href="#sql-33">SQL</a> ·
  <a href="#python-and-pyspark-30">Python</a> ·
  <a href="#data-modeling-6">Schema</a> ·
  <a href="#pipeline-architecture-6">Pipelines</a> ·
  <a href="#companion-repos">Companion repos</a>
</p>

---

Every problem links to a runnable browser sandbox at [datadriven.io](https://datadriven.io). No login required.

If you want a wider net, the sibling repo [data-engineering-interview-questions](https://github.com/datadriven-io/data-engineering-interview-questions) has the full 1418 question bank.

## Contents

- [SQL (33)](#sql-33)
- [Python and PySpark (30)](#python-and-pyspark-30)
- [Data Modeling (6)](#data-modeling-6)
- [Pipeline Architecture (6)](#pipeline-architecture-6)
- [How to use this list](#how-to-use-this-list)
- [Companion repos](#companion-repos)

## SQL (33)

### Aggregation and filtering

`GROUP BY`, `HAVING`, conditional aggregation, and the difference between filtering rows and filtering groups.

- [Spending by Account Status](https://datadriven.io/problems/spending_by_account_status)
- [Power Users by Session Activity](https://datadriven.io/problems/power_users_by_session_activity)
- [Daily Spam Impression Rate](https://datadriven.io/problems/daily_spam_impression_rate)
- [API Call Distribution Fraction](https://datadriven.io/problems/api_call_distribution_fraction)
- [Active User Penetration Rate](https://datadriven.io/problems/active_user_penetration_rate)

### Joins and subqueries

Inner, left, anti, and self joins. The choice between joining and using a subquery or `EXISTS`.

- [Average Spending by Account Status](https://datadriven.io/problems/average_spending_by_account_status)
- [Content Recommendation Engine](https://datadriven.io/problems/content_recommendation_engine)
- [First Day Session Retention](https://datadriven.io/problems/first_day_session_retention)
- [Joined Employee Details](https://datadriven.io/problems/joined_employee_details)
- [NULL Keys in Joins](https://datadriven.io/problems/null_keys_in_joins)

### NULL handling and dedup

`COALESCE`, NULL safe comparisons, `ROW_NUMBER` deduplication, `DISTINCT` vs `GROUP BY`.

- [Deduplicate and Keep Latest](https://datadriven.io/problems/deduplicate_and_keep_latest)
- [Deduplicated Sales Volume by Category](https://datadriven.io/problems/deduplicated_sales_volume_by_category)
- [Distinct Blog Referrers](https://datadriven.io/problems/distinct_blog_referrers)
- [Distinct Chat Conversations](https://datadriven.io/problems/distinct_chat_conversations)
- [Duplicate DQ Check Records](https://datadriven.io/problems/duplicate_dq_check_records)

### Date and time

Date arithmetic, day of week and hour bucketing, time window filters, timezone gotchas.

- [7 Day Onboarding Conversion](https://datadriven.io/problems/7_day_onboarding_conversion)
- [Active Tokens on Target Date](https://datadriven.io/problems/active_tokens_on_target_date)
- [After Hours API Calls](https://datadriven.io/problems/after_hours_api_calls)
- [Average Response Time by Hour](https://datadriven.io/problems/average_response_time_by_hour)
- [30 Day Page View Counts](https://datadriven.io/problems/30_day_page_view_counts)

### Window functions

`ROW_NUMBER`, `RANK`, `LAG`, `LEAD`, running aggregates, partitioned `ORDER BY`.

- [Cloud Cost Trend Analysis](https://datadriven.io/problems/cloud_cost_trend_analysis)
- [7 Check Rolling Average](https://datadriven.io/problems/7_check_rolling_average)
- [Longest Visit Streaks](https://datadriven.io/problems/longest_visit_streaks)
- [Previous Day Top Service](https://datadriven.io/problems/previous_day_top_service)
- [Cumulative Sales Per Customer](https://datadriven.io/problems/cumulative_sales_per_customer)

### CTEs and recursion

`WITH` clauses for query layering, recursive CTEs for hierarchies and graphs, multi step funnels.

- [Flatten Org Chart Hierarchy](https://datadriven.io/problems/flatten_org_chart_hierarchy)
- [Full Funnel](https://datadriven.io/problems/full_funnel)
- [Monthly Cohort Retention](https://datadriven.io/problems/monthly_cohort_retention)

### Set ops and pivots

`UNION`, `INTERSECT`, `EXCEPT`, conditional aggregation pivots that turn rows into columns.

- [Combined Cloud Spend by Region and Service](https://datadriven.io/problems/combined_cloud_spend_by_region_and_service)
- [Experiment Conversion Pivot](https://datadriven.io/problems/experiment_conversion_pivot)
- [Feature Name Intersection](https://datadriven.io/problems/feature_name_intersection)
- [Push Notification Status Pivot](https://datadriven.io/problems/push_notification_status_pivot)
- [Funnel Leakage Report](https://datadriven.io/problems/funnel_leakage_report)

## Python and PySpark (30)

### Data structures and iteration

Dicts, sets, defaultdicts, nested data, iteration patterns that turn raw records into lookups.

- [Distribute Values Into Container Types](https://datadriven.io/problems/distribute_values_into_container_types)
- [The Consecutive Sequence Finder](https://datadriven.io/problems/the_consecutive_sequence_finder)
- [The Eviction Policy](https://datadriven.io/problems/the_eviction_policy)
- [The Hierarchy Builder](https://datadriven.io/problems/the_hierarchy_builder)
- [The File Tree Builder](https://datadriven.io/problems/the_file_tree_builder)

### Aggregation and bucketing

Group by counting, running totals, histograms, bucket assignment in pure Python.

- [Cumulative Sum](https://datadriven.io/problems/cumulative_sum)
- [Group Average](https://datadriven.io/problems/group_average)
- [Group By](https://datadriven.io/problems/group_by)
- [Null Counter](https://datadriven.io/problems/null_counter)
- [Running Distinct Count](https://datadriven.io/problems/running_distinct_count)

### Streaming and I/O

Reading large files line by line, chunked CSV processing, parsing log lines, partitioned output.

- [Batch Partitioner](https://datadriven.io/problems/batch_partitioner)
- [Parse Log Line](https://datadriven.io/problems/parse_log_line)
- [The Exception Handler](https://datadriven.io/problems/the_exception_handler)
- [Permissions Manager](https://datadriven.io/problems/permissions_manager)
- [Char Profile](https://datadriven.io/problems/char_profile)

### Merge and reconcile

Joining two record streams in Python, reconciling schema drift, computing snapshot diffs.

- [Merge Counters](https://datadriven.io/problems/merge_counters)
- [Merge Intervals](https://datadriven.io/problems/merge_intervals)
- [The Matching Manifest](https://datadriven.io/problems/the_matching_manifest)
- [The Schema Diff](https://datadriven.io/problems/the_schema_diff)
- [The Perfect Match](https://datadriven.io/problems/the_perfect_match)

### Functional patterns and generators

Generators, decorators, context managers, higher order functions for throttles and timers.

- [The Chunked Reader](https://datadriven.io/problems/the_chunked_reader)
- [The Dependency Resolver](https://datadriven.io/problems/the_dependency_resolver)
- [Execution Timer Wrapper](https://datadriven.io/problems/execution_timer_wrapper)
- [The Throttle Wall](https://datadriven.io/problems/the_throttle_wall)
- [The Timing Decorator](https://datadriven.io/problems/the_timing_decorator)

### Data processing and transforms

Multi step record transformation, schema cleanup, column wise transforms, pipeline composition.

- [The Record Reconciler](https://datadriven.io/problems/the_record_reconciler)
- [Merge Overlapping Time Ranges](https://datadriven.io/problems/merge_overlapping_time_ranges)
- [The Change Data Capture](https://datadriven.io/problems/the_change_data_capture)
- [Stream Process a Large CSV](https://datadriven.io/problems/stream_process_a_large_csv)
- [The Column Transformer](https://datadriven.io/problems/the_column_transformer)

## Data Modeling (6)

### Normalization and ERDs

Designing normalized tables, picking primary and foreign keys, modeling slowly changing dimensions.

- [Customer Address History](https://datadriven.io/problems/customer_address_history)
- [Social Platform Data Model](https://datadriven.io/problems/social_platform_data_model)
- [Ride Sharing Platform Schema](https://datadriven.io/problems/ride_sharing_platform_schema)

### Star schemas and warehouses

Fact and dimension tables, grain selection, conformed dimensions, star vs snowflake tradeoffs.

- [Online Retail Star Schema](https://datadriven.io/problems/online_retail_star_schema)
- [POS Sales Data Warehouse](https://datadriven.io/problems/pos_sales_data_warehouse)
- [Movie Streaming Analytics Schema](https://datadriven.io/problems/movie_streaming_analytics_schema)

## Pipeline Architecture (6)

### Batch vs streaming

Choosing between batch and streaming, handling late arriving data, designing for consistency and replay.

- [Hourly ETL Pipeline with Consistency](https://datadriven.io/problems/hourly_etl_pipeline_with_consistency)
- [Database Replication and Schema Normalization Pipeline](https://datadriven.io/problems/database_replication_and_schema_normalization_pipeline)
- [Gaming Event Pipeline: Streaming vs Batch Architecture Decision](https://datadriven.io/problems/gaming_event_pipeline_streaming_vs_batch_architecture_decision)

### ETL and connectors

CDC connectors, incremental sync strategies, schema drift handling, auto scaling for variable load.

- [CDC Connector: Log Based vs Trigger Based](https://datadriven.io/problems/cdc_connector_log_based_vs_trigger_based)
- [AWS Pipeline Auto Scaling for Variable Volume](https://datadriven.io/problems/aws_pipeline_auto_scaling_for_variable_volume)
- [City Wide Bicycle Demand Forecasting Pipeline](https://datadriven.io/problems/city_wide_bicycle_demand_forecasting_pipeline)

## How to use this list

| You have | Strategy |
|---|---|
| **4+ weeks** | Work through every question in order. Each pattern builds on the last. |
| **1 to 2 weeks** | Focus on SQL and pipeline architecture. The two highest weight rounds. |
| **48 hours** | Skim every pattern description. Solve only the patterns you have not seen before. |
| **Stuck on a question** | Read the prompt, attempt a solution, then check the discussion. |

## Companion repos

- [data-engineering-interview-questions](https://github.com/datadriven-io/data-engineering-interview-questions). The full 1418 question bank.
- [data-engineering-interview-handbook](https://github.com/datadriven-io/data-engineering-interview-handbook). The flagship handbook with chapters and study plans.
- [awesome-data-engineering-interview](https://github.com/datadriven-io/awesome-data-engineering-interview). Curated resource list (singular).
- [system-design-for-data-engineers](https://github.com/datadriven-io/system-design-for-data-engineers). 120 long form pipeline case studies.
- [data-engineer-interview-prep](https://github.com/datadriven-io/data-engineer-interview-prep). 8 week structured practice schedule.
- [data-engineering-cheatsheet](https://github.com/datadriven-io/data-engineering-cheatsheet). One page recall reference.
- [data-engineer-interview-handbook](https://github.com/datadriven-io/data-engineer-interview-handbook). 7 day sprint version of the handbook.

## Contributing

Curated list. To suggest a question, open an issue with:

1. The pattern the question tests
2. A real source (interview report, blog, your own experience)
3. Why it belongs in the 75 rather than the long tail

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
