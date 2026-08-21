# Customer Data Platform — Real-Time Intent & Predictive Sales

> **Portfolio lens:** Zero-ETL CDP, identity resolution, data product strategy, predictive intelligence, and responsible commercialization.

## Executive snapshot

Led product and architecture strategy for a 15 TB customer-data modernization spanning seven systems. The program deliberately sequenced identity integrity before real-time pipelines and predictive scoring, preventing faster ingestion from amplifying duplicate profiles and poor decisions.

## Resume-ready impact

- Led a customer-data platform modernization that reduced peak signal latency from 26 hours to under 15 minutes and infrastructure cost 30%.
- Made golden-record identity resolution the first product requirement after stress tests exposed duplicate profiles and roughly $2M in projected media waste.
- Launched behavior-based propensity scoring that reduced CAC 20%, increased lead conversion from 1.8% to 5.4%, and raised recruited-seller first-year sales from $12K to $28K.

## Interview story

### Situation

A large commerce business used stale signals and duplicate customer records during peak events. Sales prioritized static lists, marketing duplicated targeting, and the original roadmap emphasized ingestion speed before data trust.

### Task

Create a resilient data product that delivered current, trusted intent and demonstrated business value across engineering, marketing, sales, finance, and operations.

### Actions

- Used a two-week regional pilot to show that live intent produced three-times-higher conversion before approving the broader rebuild.
- Recommended a three-week launch delay when a game day exposed ghost profiles and conflicting targeting.
- Implemented direct connectors, raw backup, streaming events, schema contracts, entity resolution, and a golden customer record.
- Maintained a random 20% control group around predictive lead scoring to protect unconventional but valuable sellers.

### Results

- Latency fell below 15 minutes, and infrastructure cost fell 30%.
- CAC declined 20%, and lead conversion tripled to 5.4%.
- First-year seller sales increased from $12K to $28K.
- The peak event ran with zero downtime and finished $25M above the Q4 sales target.

## Decisions and trade-offs

- Choose identity integrity over the original launch date.
- Sequence identity, then pipelines, then predictive intelligence.
- Use architecture game days and control cohorts to separate causal value from correlation.

## Leadership signal

Created one commercial and technical scorecard across five functions, translating data quality from an engineering concern into customer trust and revenue quality.

## Skills and keywords

customer data platform · Zero-ETL · identity resolution · golden record · streaming data · predictive scoring · data governance · product analytics · CAC · conversion

## Source

[Original Notion project page](https://app.notion.com/p/2f8f9e255f218045a721df236a1c6508)

