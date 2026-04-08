# Awesome Data Engineering Interviews

> A curated list of 75 real data engineering interview questions, with public solutions, ordered by topic. Maintained by [datadriven.io](https://datadriven.io).

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

Data engineering interviews test a different skill set than software engineering interviews: SQL fluency under pressure, the ability to reason about data quality, knowing when to use a window function vs a self-join, and being able to talk about a pipeline that breaks at 3 AM. The questions in this list are real patterns asked at companies that hire data engineers at scale.

Every problem links to a public, runnable version on datadriven.io with sample data and a built-in SQL or Python sandbox. No login required.

## Contents

- [The 75](#the-75)
  - [SQL](#sql) (53 questions)
  - [Python and PySpark](#python-and-pyspark) (18 questions)
  - [Data Modeling](#data-modeling) (4 questions)
- [How to use this list](#how-to-use-this-list)
- [What gets tested in a data engineering interview](#what-gets-tested-in-a-data-engineering-interview)
- [Related resources](#related-resources)
- [Contributing](#contributing)
- [License](#license)

## The 75

The DataDriven 75 is a curated set of the most-asked patterns in data engineering interviews, drawn from interview reports across FAANG, fintech, and data infrastructure companies. Work through them in order, or jump to the section you need.

### SQL

SQL questions test your ability to express set logic, handle null and duplicate edge cases, and reason about query execution. Most data engineering interviews are 60% SQL.

| # | Question | Topic |
| --- | --- | --- |
| 1 | [Unmatched Credit Complaints](https://datadriven.io/problems/unmatched_credit_complaints) | The support team is investigating users who claim unreceived credits by cross-referencing  |
| 2 | [The Duplicate Detection Sprint](https://datadriven.io/problems/the_duplicate_detection_sprint) | Find duplicate email addresses with occurrence counts and signup date ranges using GROUP B |
| 3 | [Weekend Warriors](https://datadriven.io/problems/weekend_warriors) | Compare event volumes on weekdays vs weekends using CASE WHEN pivot pattern. |
| 4 | [The Dormant Accounts](https://datadriven.io/problems/the_dormant_accounts) | Find paying customers inactive for 90+ days with their subscription tier and lifetime spen |
| 5 | [30-Day Page View Counts](https://datadriven.io/problems/30_day_page_view_counts) | Product analytics wants a quick engagement snapshot. |
| 6 | [Above Average Interactions](https://datadriven.io/problems/above_average_interactions) | Find users exceeding average activity count. |
| 7 | [Above Category Average](https://datadriven.io/problems/above_category_average) | Find rows whose value exceeds a joined reference. |
| 8 | [Active API Tokens](https://datadriven.io/problems/active_api_tokens) | The admin team needs all API tokens that have actually been used. |
| 9 | [Active Campaigns](https://datadriven.io/problems/active_campaigns) | The ad team needs to know which campaigns are worth the spend. |
| 10 | [Active User Revenue for April](https://datadriven.io/problems/active_user_revenue_for_april) | Total revenue from active users in a single month |
| 11 | [Active Users With April Transactions](https://datadriven.io/problems/active_users_with_april_transactions) | The monetization team wants to know how many active users made at least one transaction in |
| 12 | [Activity Histogram](https://datadriven.io/problems/activity_histogram) | Two level GROUP BY to build a frequency histogram. |
| 13 | [Alert Hotspots by Service and Severity](https://datadriven.io/problems/alert_hotspots_by_service_and_severity) | The infrastructure team is mapping alert hotspots. |
| 14 | [All Infra Regions](https://datadriven.io/problems/all_infra_regions) | The data catalog team needs a list of all distinct regions present in the infrastructure n |
| 15 | [Annual Cloud Spend](https://datadriven.io/problems/annual_cloud_spend) | The cloud finance team needs total annual cloud spending. |
| 16 | [Annual Cloud Spend Summary](https://datadriven.io/problems/annual_cloud_spend_summary) | The finance team wants total cloud spending and the number of distinct services billed in  |
| 17 | [Annual Pipeline Failures](https://datadriven.io/problems/annual_pipeline_failures) | The data platform team is auditing pipeline failures. |
| 18 | [April and May Active Users](https://datadriven.io/problems/april_and_may_active_users) | The analytics team needs a list of users who were active in April or May. |
| 19 | [Auth Endpoints](https://datadriven.io/problems/auth_endpoints) | The platform team needs all API endpoints that contain the word 'health' (case-insensitive |
| 20 | [Authors With Successful Deploys](https://datadriven.io/problems/authors_with_successful_deploys) | The delivery team tracks successful deployment authors. |
| 21 | [Auth Service Health Checks](https://datadriven.io/problems/auth_service_health_checks) | The compliance team needs a full audit trail for the 'auth-service'. |
| 22 | [Average Brand Campaign Revenue](https://datadriven.io/problems/average_brand_campaign_revenue) | The ad analytics team needs a quick benchmark. |
| 23 | [Average Build Duration by Repo](https://datadriven.io/problems/average_build_duration_by_repo) | The platform team is benchmarking build performance. |
| 24 | [Average DQ Fail Rate](https://datadriven.io/problems/average_dq_fail_rate) | The data quality team computes average check fail rates per table. |
| 25 | [Average GPU Node CPU Usage](https://datadriven.io/problems/average_gpu_node_cpu_usage) | The infra team is sizing capacity for GPU nodes. |
| 26 | [Average Headcount by Department](https://datadriven.io/problems/average_headcount_by_department) | HR analytics is benchmarking compensation. |
| 27 | [Average High-Range Accuracy](https://datadriven.io/problems/average_high_range_accuracy) | The ML platform team needs the average accuracy for models scoring between 91 and 100 incl |
| 28 | [Average Latency by Health Status](https://datadriven.io/problems/average_latency_by_health_status) | For a quarterly reliability review, the team needs the average latency broken out by healt |
| 29 | [Average Latency by Status](https://datadriven.io/problems/average_latency_by_status) | The SRE team wants the average latency for each API call status. |
| 30 | [Average Node CPU by Region](https://datadriven.io/problems/average_node_cpu_by_region) | Average infrastructure node CPU usage broken down by region |
| 31 | [Average Node Utilization](https://datadriven.io/problems/average_node_utilization) | The cloud finance team needs average CPU and memory utilization broken down by region and  |
| 32 | [Average Rating by Category](https://datadriven.io/problems/average_rating_by_category) | The product analytics team wants the average rating for products in each category. |
| 33 | [Average Response Time by Hour](https://datadriven.io/problems/average_response_time_by_hour) | The SRE team needs average response time broken down by hour of day, sorted chronologicall |
| 34 | [Average Search Endpoint Latency](https://datadriven.io/problems/average_search_endpoint_latency) | The performance team wants the average latency for the '/api/search' endpoint. |
| 35 | [Average Search Results Per User](https://datadriven.io/problems/average_search_results_per_user) | The search relevance team is benchmarking query volume per user. |
| 36 | [Average Session Duration by Device](https://datadriven.io/problems/average_session_duration_by_device) | The performance team wants to benchmark session lengths by device. |
| 37 | [Bargain Bin](https://datadriven.io/problems/bargain_bin) | Procurement wants floor prices before the next vendor negotiation. |
| 38 | [Best-Selling Reps Each Month](https://datadriven.io/problems/best_selling_reps_each_month) | The marketplace team needs the top 3 sellers by total amount in each product category for  |
| 39 | [Big Spenders](https://datadriven.io/problems/big_spenders) | Marketing wants a whale list for the loyalty program launch. |
| 40 | [Budget Flag](https://datadriven.io/problems/budget_flag) | Join tables and label rows as over or under budget. |
| 41 | [Budget-Friendly Products](https://datadriven.io/problems/budget_friendly_products) | The product team wants all distinct product names that are budget-friendly, meaning priced |
| 42 | [Campaign Revenue Totals](https://datadriven.io/problems/campaign_revenue_totals) | The finance team needs total ad revenue grouped by campaign. |
| 43 | [Cart Sizes](https://datadriven.io/problems/cart_sizes) | Product is hunting for power buyers to beta-test the new bulk checkout flow. |
| 44 | [Category Census](https://datadriven.io/problems/category_census) | The warehouse wants to know which aisles are worth restocking. |
| 45 | [Category Sales Summary](https://datadriven.io/problems/category_sales_summary) | The merchandising team is reviewing category performance for {{YEAR}}. |
| 46 | [Category-Specific Product Volume](https://datadriven.io/problems/category_specific_product_volume) | Sum transactions for a specific payment type. |
| 47 | [CDN Image Request Paths](https://datadriven.io/problems/cdn_image_request_paths) | The networking team needs all CDN log entries related to image requests. |
| 48 | [CDN-Related DNS Lookups](https://datadriven.io/problems/cdn_related_dns_lookups) | The DNS team is filtering lookup records. |
| 49 | [Character Position in Endpoint](https://datadriven.io/problems/character_position_in_endpoint) | The growth team is debugging URL patterns. |
| 50 | [Chat Activity](https://datadriven.io/problems/chat_activity) | The community lead wants to know which channels are ghost towns. |
| 51 | [Cheapest Cost Per Region](https://datadriven.io/problems/cheapest_cost_per_region) | The cost optimization team is finding the lowest cloud spend per region. |
| 52 | [Cheapest Transaction per User](https://datadriven.io/problems/cheapest_transaction_per_user) | The commerce team wants to identify each customer's cheapest purchase. |
| 53 | [Clean Cache CDN Edges](https://datadriven.io/problems/clean_cache_cdn_edges) | The network team needs to identify CDN edges that serve cached content with no errors. |

### Python and PySpark

Python questions in DE interviews focus on PySpark transformations, dataframe manipulation, and the kinds of one-off scripts you write to debug a broken pipeline. Less algorithmic, more practical than a SWE interview.

| # | Question | Topic |
| --- | --- | --- |
| 54 | [The Dominant Signal](https://datadriven.io/problems/the_dominant_signal) | Hottest items in the transaction log. Ties included. |
| 55 | [The Original Keeper](https://datadriven.io/problems/the_original_keeper) | Clean up duplicate events without losing the timeline. |
| 56 | [The Forward Fill](https://datadriven.io/problems/the_forward_fill) | Patch the gaps in a noisy sensor stream. |
| 57 | [The Word Mismatch](https://datadriven.io/problems/the_word_mismatch) | Some text does not match. |
| 58 | [The Social Graph](https://datadriven.io/problems/the_social_graph) | Everyone knows someone. |
| 59 | [The Sequel Spotter](https://datadriven.io/problems/the_sequel_spotter) | Spot the sequels hiding in the catalog. |
| 60 | [The Numbered Chair](https://datadriven.io/problems/the_numbered_chair) | A standing list. Position n holds one entry. |
| 61 | [The Character Encoder](https://datadriven.io/problems/the_character_encoder) | Squeeze a string down to its tightest form. |
| 62 | [The One-Way Street](https://datadriven.io/problems/the_one_way_street) | Monotonic time-series. Direction only. |
| 63 | [The IP Validator](https://datadriven.io/problems/the_ip_validator) | Real and fake, mixed together. |
| 64 | [The Log Pulse](https://datadriven.io/problems/the_log_pulse) | Some lines repeat themselves. |
| 65 | [The One-of-Each](https://datadriven.io/problems/the_one_of_each) | Strip the repeats, keep the originals. |
| 66 | [The Config Blender](https://datadriven.io/problems/the_config_blender) | Config collision. The surviving values after a merge. |
| 67 | [Flatten the Feed](https://datadriven.io/problems/flatten_the_feed) | Nested lists, all the way down. |
| 68 | [Activity Time Ledger](https://datadriven.io/problems/activity_time_ledger) | Matching activities. One runtime. |
| 69 | [Batch With Metadata](https://datadriven.io/problems/batch_with_metadata) | The list gets chopped. |
| 70 | [Caesar Shift Check](https://datadriven.io/problems/caesar_shift_check) | The key turns. Does it open? |
| 71 | [Character Occurrence Map](https://datadriven.io/problems/character_occurrence_map) | Character frequency as a map. |

### Data Modeling

Data modeling questions ask you to design schemas (star, snowflake, slowly-changing dimensions) and reason about tradeoffs between normalization, query performance, and storage cost.

| # | Question | Topic |
| --- | --- | --- |
| 72 | [Customer Address History](https://datadriven.io/problems/customer_address_history) | People move. Sometimes twice in a month. How do you remember where everyone was, and when? |
| 73 | [B2B Invoicing Data Model](https://datadriven.io/problems/b2b_invoicing_data_model) | Invoices go out, partial payments trickle in, and some customers are three months overdue. |
| 74 | [Fitness Studio Membership Schema](https://datadriven.io/problems/fitness_studio_membership_schema) | Classes fill up, waitlists grow, members no-show, and billing happens monthly. Keep it all |
| 75 | [A Number for the Seller](https://datadriven.io/problems/a_number_for_the_seller) | They want a total. Give them the right schema first. |

## How to use this list

**If you have 4 or more weeks before your interview**: work through all 75 in order. The list is sequenced so each question introduces a pattern you will reuse later.

**If you have 1 to 2 weeks**: focus on the SQL section. SQL is the highest-leverage prep because it appears in nearly every data engineering screen and onsite.

**If you have 48 hours**: skim every question prompt, identify the patterns you have not seen before, and solve only those. The goal is pattern recognition, not muscle memory.

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

## Related resources

- [datadriven.io](https://datadriven.io) - Interactive practice for all 75 questions plus 200+ more, with a built-in SQL and Python sandbox.
- [datadriven.io/interview](https://datadriven.io/interview) - Mock interview practice with company-specific question packs.
- [datadriven.io/learn](https://datadriven.io/learn) - Foundational data engineering concepts (query structure, data modeling, pipeline architecture).
- [datadriven.io/daily](https://datadriven.io/daily) - One new data engineering interview question every day.

## Contributing

This list is curated. To suggest a question for inclusion, open an issue with:

- The pattern the question tests
- A real source (interview report, blog, or your own experience)
- Why it belongs in the top 75 rather than the long tail

## License

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). You may share and adapt this list for any purpose, including commercially, as long as you give appropriate credit to datadriven.io.
