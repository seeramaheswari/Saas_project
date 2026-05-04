# 📊 SaaS User Analytics Project — End-to-End Behavioral & Revenue Insights

## 🔍 Project Overview

### This project simulates a real-world SaaS environment to analyze user growth, engagement behavior, revenue patterns, and churn dynamics.The goal is to extract actionable insights that can support product decisions, marketing optimization, and retention strategies.

## 🗂️ Dataset Design & Structure
```
 Users Table

Captures user acquisition and demographic attributes.
Columns:

user_id — Unique user identifier
signup_date — Date of user registration
country — User location
device — Device used for signup
acquisition_channel — Source of user acquisition (e.g., Ads, Organic, Referral)
```
```
2. Events Table

Tracks user activity and engagement over time.
Columns:

user_id — User reference
event_type — Type of action (login, purchase, feature usage, etc.)
event_time — Timestamp of event
revenue — Revenue generated (if applicable)
session_id — Session identifier
cohort_month — Month of user signup
activity_month — Month of activity
cohort_index — Time difference between signup and activity (used in retention)
```
```
3. Subscriptions Table

Represents subscription lifecycle and churn behavior.
Columns:

user_id — User reference
plan — Subscription plan type
start_date, end_date — Subscription duration
last_activity_date — Last recorded engagement
days_inactive — Days since last activity
churned — Churn status (Yes/No)
```
## 1. 🌍 Regional Plan Performance

### Objective: Understand how subscription plans perform across different countries.

#### Operations Performed:
```
Grouped users by country and plan
Applied COUNT() aggregation to measure distribution
Visualized using Seaborn count plots

Insight:
Identifies high-performing regions for specific plans → useful for localized pricing and marketing strategies.
```
## 2. 📊 Signup Trends (Growth vs Drop-off)

### Objective: Analyze user acquisition and inactivity trends over time.

#### Operations Performed:
```
Extracted signup_month from signup_date
Derived last_activity_month from last_activity_date
Grouped by months and applied COUNT()
Visualized using Matplotlib line charts

Insight:

Tracks active vs inactive users over time
Helps detect seasonality, growth spikes, or churn signals
```
## 3. 🎯 Acquisition Channel Performance

### Objective: Measure effectiveness of marketing channels.

#### Operations Performed:
```
Grouped data by acquisition_channel and plan
Calculated:
Total users (COUNT)
Total revenue (SUM(revenue))

Insight:

Identifies high ROI channels
Supports budget allocation decisions
```
## 4. 👤 Customer Behavior Analysis

### Objective: Understand how users interact with the product before becoming inactive.

#### Operations Performed:
```
Filtered events between:
signup_date and last_activity_date
Analyzed:
Frequency of event_type
Relation with days_inactive

Insight:

Detects engagement patterns leading to churn
Helps identify critical features that retain users
```
## 5. 🔁 Cohort Retention Analysis

### Objective: Measure how well users are retained over time.

#### Operations Performed:
```
Created cohorts using cohort_month
Calculated cohort_index (months since signup)
Aggregated active users per cohort over time
Built retention matrix

Insight:

Reveals user retention decay patterns
Helps evaluate product stickiness and onboarding effectiveness
```
