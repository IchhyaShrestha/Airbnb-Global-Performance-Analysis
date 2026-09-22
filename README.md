# Airbnb Global Performance Analysis

An interactive Power BI dashboard analyzing Airbnb's global marketplace performance across listings, cities, hosts, property types, customer reviews, ratings, pricing, seasonality, and host trust indicators.

The project focuses on transforming Airbnb marketplace data into business insights that can support decisions related to market growth, customer behavior, property performance, and host quality.


## 📊 Dashboard Preview

### Page 1 — Global Performance & Growth

![Global Airbnb Performance Dashboard](images/dashboard-overview.png)

This page provides an overview of Airbnb's marketplace growth and highlights changes in new listings over time.

Key areas analyzed:

- Total listings and hosts
- Geographic market coverage
- Property type diversity
- Review volume
- New listing growth over time
- Marketplace lifecycle stages
- Changes in entire-place, private-room, and shared-room listings

---

### Page 2 — Market Share, Pricing & Ratings

![Airbnb Market Share Dashboard](images/market-share-ratings.png)

This page examines differences across Airbnb's largest markets.

Key areas analyzed:

- Listing concentration by city
- Review concentration by city
- Superhost vs. non-Superhost listings
- Cumulative market share
- Average pricing by room type
- City-level ratings
- Rating dimensions including accuracy, cleanliness, communication, location, and value

---

### Page 3 — Customer Behavior, Seasonality & Trust

![Airbnb Customer Behavior Dashboard](images/customer-behavior-trust.png)

This page analyzes customer review behavior, seasonal demand patterns, and host verification.

Key areas analyzed:

- Reviews per reviewer
- Customer review frequency
- Seasonal review patterns
- Monthly activity by major cities
- Host identity verification
- Profile picture availability
- Potential data anomalies

---

# 🎯 Business Problem

Airbnb operates across a highly diverse global marketplace where performance can vary significantly by geography, property type, customer behavior, and host characteristics.

The objective of this project was to answer several business questions:

1. How has Airbnb's listing activity changed over time?
2. Which cities contribute the largest share of listings and reviews?
3. How concentrated is Airbnb's marketplace across major cities?
4. How do prices differ across property types?
5. Which cities demonstrate stronger or weaker customer ratings?
6. How frequently do customers leave reviews?
7. Are there seasonal patterns in customer activity?
8. What does host verification tell us about marketplace trust?
9. Are there unusual customer behavior patterns that may require further investigation?

---

# 🔎 Key Insights

## 1. Marketplace Growth

Airbnb experienced substantial growth in new listings during the early and mid stages of the marketplace lifecycle.

New listings reached a peak around 2015 before growth began to slow.

The dashboard also highlights changes around 2016–2019, followed by a significant decline in new listings during the COVID-19 period.

This provides a useful example of how external events and market maturity can affect marketplace growth.

---

## 2. Market Concentration

Paris, New York, and Sydney collectively account for nearly half of the listings and approximately 48% of total reviews in the analyzed dataset.

The cumulative market-share analysis shows that a relatively small number of cities account for a large proportion of Airbnb's marketplace activity.

This concentration suggests that geographic performance should not be evaluated solely at the global level.

---

## 3. Pricing Differences

Average pricing varies considerably by property type.

In the analyzed data:

- Hotel rooms: approximately $800
- Entire places: approximately $673
- Shared rooms: approximately $580
- Private rooms: approximately $462

The pricing gap between entire-place and private-room listings provides an opportunity to examine how accommodation type influences customer choice and marketplace positioning.

---

## 4. Customer Ratings

City-level ratings were compared across multiple dimensions, including:

- Accuracy
- Cleanliness
- Communication
- Location
- Value

Mexico City and Rio de Janeiro show relatively strong overall rating profiles in the dashboard, while Hong Kong and Istanbul appear weaker across several rating dimensions.

The analysis also shows that cleanliness and value for money tend to be among the lower-scoring dimensions across cities.

---

## 5. Customer Review Behavior

Review frequency is highly concentrated among one-time reviewers.

Approximately 98.8% of customers in the analyzed data left three reviews or fewer.

At the other end of the distribution, one reviewer left 283 reviews.

This extreme value was flagged as a potential data-quality issue or an example requiring further investigation rather than being treated as representative customer behavior.

---

## 6. Seasonality

Customer activity varies across months and markets.

Paris and Rome account for a larger share of review activity during the April–August period, which is consistent with stronger European summer travel activity.

New York shows increased review activity toward November and December, coinciding with the holiday travel period.

These patterns demonstrate the importance of considering seasonality when evaluating marketplace performance.

---

## 7. Host Trust & Verification

More than two-thirds of hosts in the analyzed dataset are identity verified.

The dashboard also compares identity verification with profile-picture availability.

The results indicate that verified hosts are substantially more likely to have profile pictures, while unverified hosts show a higher proportion without profile pictures.

These indicators can be useful when studying trust and transparency within a peer-to-peer marketplace.

---

# 📈 Key Metrics

| Metric | Value |
|---|---:|
| Listings | 279,712 |
| Cities | 10 |
| Hosts | 182,024 |
| Property Types | 144 |
| Reviews | 5.37M |
| Top 3 Cities by Listings | Paris, New York, Sydney |
| One-time / low-frequency reviewers | 98.8% |
| Highest observed reviews by one reviewer | 283 |

---

# 🛠️ Tools & Technologies

### Business Intelligence
- Microsoft Power BI
- Power Query
- DAX

### Data Analysis
- Data cleaning
- Data transformation
- Exploratory data analysis
- KPI development
- Customer behavior analysis
- Market-share analysis
- Trend analysis
- Seasonality analysis
- Data-quality investigation

### Data Visualization
- KPI cards
- Line charts
- Stacked bar charts
- Cumulative percentage analysis
- Heatmaps
- Matrix visualizations
- Combination charts
- Interactive filters

---

# 🧮 DAX & Analytical Techniques

The dashboard uses DAX to create calculated metrics and analytical views, including:

- Reviews per Reviewer
- Cumulative Reviewer Analysis
- Cumulative Market Share
- City Ranking
- Review and Listing aggregations
- Conditional calculations
- Context-aware calculations using `CALCULATE`
- Filter context manipulation using `ALLEXCEPT`
- Dynamic ranking and cumulative analysis

Example:

```DAX
Reviews per Reviewer =
CALCULATE(
    COUNT(Reviews[review_id]),
    ALLEXCEPT(
        Reviews,
        Reviews[reviewer_id]
    )
)
