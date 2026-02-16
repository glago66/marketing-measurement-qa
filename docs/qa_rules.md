# Marketing Measurement QA Rules (v0.1)

This repository is a practical QA toolkit for marketing + web/app measurement.

Goal:
- detect broken tracking quickly
- catch attribution lies early
- produce a clean “measurement health report” that stakeholders can trust

---

## What this repo is (and is not)

**This repo IS:**
- a repeatable QA process for event data + marketing reporting
- a set of SQL checks you can run daily/weekly
- a set of “rules” that prevent false confidence

**This repo is NOT:**
- a full MMM system
- a perfect multi-touch attribution model
- a replacement for data engineering

---

## QA categories

### Category A — Event integrity
Checks that raw event data is not broken.

Examples:
- sudden drop to zero in key events
- event schema changes (missing fields)
- duplicates or inflated events
- broken session stitching

---

### Category B — Funnel sanity
Checks that funnel behavior is not impossible.

Examples:
- purchases without product views
- checkout without add_to_cart
- conversion rate spikes without traffic changes

---

### Category C — Attribution reality check
Compares:
- platform-reported conversions (Meta/Google/etc.)
vs
- blended business outcomes (orders, revenue, customers)

Goal:
- detect when platform attribution is misleading
- detect tracking gaps that inflate/deflate channel performance

---

### Category D — Experiment integrity
Checks that A/B tests are not invalid.

Examples:
- sample ratio mismatch
- missing exposure events
- users switching variants
- mismatched date ranges

---

### Category E — Data freshness & completeness
Checks that the data pipeline is delivering expected volumes on time.

Examples:
- delayed ingestion
- missing partitions/dates
- partial loads

---

## Standard outputs (what this produces)

This repo will produce:

1) A daily QA scorecard (pass/fail checks)
2) A weekly “measurement health report”
3) A list of recommended fixes (tracking + pipeline)

---

## Rule philosophy (important)

The goal is not to prove data is perfect.

The goal is to:
- catch the biggest failures fast
- quantify uncertainty
- prevent false confidence in dashboards
