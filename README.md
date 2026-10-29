# AI-Powered Digital Advertising Budget Optimizer

### Big Data Analytics | Machine Learning | Sentiment Analysis | Clustering | Marketing Intelligence

## Project Overview

The **AI-Powered Digital Advertising Budget Optimizer** is a Big Data Analytics project designed to analyze customer sentiment, advertising engagement, product performance, and marketing campaign data to support better advertising decisions.

The project initially focuses on Pakistani clothing brands, including Khaadi, Sapphire, Gul Ahmed, Alkaram Studio, Nishat Linen, and others.

The ultimate goal is to develop an intelligent marketing analytics system that identifies patterns in customer feedback and campaign performance, segments products and campaigns using machine learning, and recommends effective advertising budget allocations.

## Business Problem

Businesses invest substantial amounts of money in digital advertising platforms such as:

- Facebook
- Instagram
- Google Ads
- TikTok
- YouTube

However, deciding which platforms deserve the most investment can be challenging.

**The central question is:**

*If a business has PKR 1,000,000 to spend on digital advertising, how should that budget be distributed to achieve better results?*

This project aims to address that question through data analytics, clustering, performance metrics, and a planned budget recommendation engine.

## Project Objectives

- Develop a scalable data collection pipeline.
- Collect customer feedback and engagement data.
- Analyze customer opinions through sentiment classification.
- Identify discussion topics using unsupervised learning.
- Analyze product-related information and pricing concerns.
- Cluster products, videos, and advertising campaigns.
- Evaluate advertising performance through marketing KPIs.
- Compare Pandas, MapReduce, and Apache Spark.
- Develop an advertising budget recommendation engine.
- Visualize marketing insights through an interactive dashboard.

## 1. Data Collection — YouTube Data API v3

The initial implementation uses the YouTube Data API v3 to collect publicly accessible video metadata and comments related to Pakistani clothing brands.

### Collected Information

- Brand search term
- Video ID and URL
- Video title and description
- Channel information
- Publication date
- Video views and likes
- Public comments
- Comment likes and timestamps
- Potential product categories
- Price mentions, when available

### Data Collection Features

The pipeline includes:

- API pagination
- Batch processing
- Duplicate prevention
- SQLite-based incremental storage
- Resumable collection
- CSV export
- Support for large-scale processing workflows

### Dataset Output

`youtube_clothing_ONE_FILE.csv`

The dataset combines customer comments with associated video and potential product information.

**Note:** The pipeline is designed to support million-row datasets, but an actual collection of one million comments has not yet been independently verified.

## 2. Sentiment Analysis

The sentiment analysis component is designed to classify customer comments into:

- Positive
- Negative
- Neutral

### Model

**Multilingual DistilBERT**

The selected model is:

`lxyuan/distilbert-base-multilingual-cased-sentiments-student`

This model is intended to process multilingual customer feedback.

Since Pakistani comments frequently contain English, Urdu, Roman Urdu, and mixed-language expressions, manual evaluation is required to assess classification accuracy.

### Purpose

Sentiment analysis can help identify customer satisfaction, negative feedback, and common complaints about products and brands.

## 3. Comment Topic Clustering

### Algorithm

**TF-IDF + MiniBatch K-Means**

TF-IDF converts customer comments into numerical feature vectors.

MiniBatch K-Means groups comments based on textual similarity.

Potential clusters may represent discussions related to:

- Product prices
- Clothing designs
- Product quality
- Delivery questions
- Purchase inquiries

Actual cluster meanings must be determined by examining the resulting keywords and comments.

## 4. Video Performance Clustering

The project also includes video-level clustering based on engagement-related features.

### Features

- Video views
- Comment volume
- Like rate
- Comment-topic distribution

### Techniques

- Numerical feature transformation
- StandardScaler
- MiniBatch K-Means

This analysis aims to identify videos with similar engagement and audience discussion patterns.

## 5. Product and Price Analysis

The product intelligence component is designed to connect customer feedback with clothing products.

Relevant attributes include:

- Product name
- Brand
- Product category
- Verified price in PKR
- Product URL
- Customer sentiment
- Price-related complaints

Price mentions extracted from YouTube descriptions are treated as unverified until matched with an authorized or official product catalog.

### Planned Product Clustering

Product clustering will use features such as:

- Verified product price
- Positive sentiment percentage
- Negative sentiment percentage
- Price complaint percentage
- Customer engagement

The objective is to identify product segments with different pricing and customer-response characteristics.

## 6. Digital Advertising Campaign Analytics

The next major module focuses on advertising performance across:

- Facebook
- Instagram
- Google Ads
- TikTok
- YouTube

### Required Campaign Dataset

The planned dataset includes:

`date, campaign_id, platform, impressions, clicks, spend, conversions, revenue, age_group, gender, city, device`

Actual demographic and advertising performance information requires authorized data access or clearly labelled simulated records.

### Marketing KPIs

| Metric | Formula |
|---|---|
| CTR | (Clicks / Impressions) × 100 |
| CPC | Spend / Clicks |
| CPA | Spend / Conversions |
| Conversion Rate | (Conversions / Clicks) × 100 |
| ROAS | Revenue / Spend |

These metrics will support campaign performance comparisons and budget planning.

## 7. Big Data Analytics

To demonstrate scalability, the project plans to evaluate datasets of increasing sizes:

- 10,000 records
- 100,000 records
- 1,000,000 records
- 10,000,000 records

### Technologies for Comparison

**Pandas:** Traditional single-machine data processing.

**MapReduce:** Batch-oriented large-scale data aggregation.

**Apache Spark:** Scalable data processing and analytical workloads.

### Evaluation Criteria

- Execution time
- Memory usage
- Processing scalability
- Output correctness

The benchmarking experiments are part of the planned development work.

## 8. Advertising Campaign Clustering

The planned advertising clustering module will identify groups of campaigns with similar performance characteristics.

### Features

- Click-through rate
- Cost per click
- Cost per acquisition
- Conversion rate
- Return on ad spend

### Machine Learning

**K-Means Clustering**

Clustering will help analyze campaign efficiency, cost patterns, and possible growth opportunities.

The resulting clusters will be interpreted using actual performance metrics rather than assuming that a particular cluster number automatically represents a successful campaign.

## 9. Marketing Budget Recommendation Engine

The final objective is to recommend advertising budget allocations based on campaign performance and machine learning insights.

### Example Business Scenario

**Available advertising budget: PKR 1,000,000**

| Advertising Platform | Example Allocation |
|---|---:|
| Facebook | 25% |
| Instagram | 30% |
| Google Ads | 35% |
| TikTok | 10% |

This allocation is illustrative and does not represent an actual optimized result.

The planned recommendation engine will consider performance history, platform constraints, and marketing objectives when generating allocation suggestions.

## 10. Technology Stack

**Programming:** Python

**Data Collection:** YouTube Data API v3

**Data Processing:** Pandas, NumPy, SQLite

**Big Data:** Apache Spark, MapReduce (planned)

**Machine Learning:** Scikit-learn, K-Means, MiniBatch K-Means

**Natural Language Processing:** TF-IDF, Hugging Face Transformers, Multilingual DistilBERT

**Visualization:** Matplotlib, Seaborn, Streamlit (planned)

**Development:** Google Colab, Jupyter Notebook, GitHub

## 11. Project Progress

### Developed or Prepared

- YouTube API-based data collection pipeline
- Video and comment pagination
- Large-scale collection architecture
- SQLite storage and duplicate prevention
- Single-CSV export
- Product category and price mention extraction
- Comment topic clustering notebook
- Video performance clustering notebook
- Multilingual sentiment model integration
- Initial campaign analytics and clustering code

### In Progress / Planned

- Validation of the full collected dataset
- Manual evaluation of sentiment predictions
- Verified product price enrichment
- Product performance clustering
- Authorized or simulated cross-platform advertising dataset
- Pandas vs MapReduce vs Spark benchmarking
- Campaign performance clustering evaluation
- Marketing budget recommendation engine
- Interactive dashboard
- Final performance evaluation

## 12. Current Limitations

- YouTube comments do not directly provide advertising spend, conversions, or revenue.
- YouTube Data API does not expose individual commenters' age, gender, or city.
- Product prices extracted from video text require verification.
- Roman Urdu sentiment classification requires manual evaluation.
- Million-row processing capability does not guarantee that one million real comments are available or have been collected.
- Accurate advertising budget recommendations require comparable campaign performance data.

## 13. Expected Outcomes

The completed system aims to provide:

- Large-scale customer feedback analytics
- Multilingual sentiment insights
- Topic and engagement clustering
- Product pricing and satisfaction analysis
- Advertising campaign performance evaluation
- Scalable big data processing benchmarks
- Intelligent budget allocation recommendations
- An interactive marketing analytics dashboard

## Conclusion

The AI-Powered Digital Advertising Budget Optimizer combines Big Data Analytics, Natural Language Processing, unsupervised machine learning, and digital marketing intelligence.

The project begins with customer feedback and YouTube engagement analysis and progresses toward product intelligence, advertising performance segmentation, and budget optimization.

Its ultimate goal is to support more informed, data-driven marketing investment decisions.

---

## GitHub Repository

**Repository:** `digital-advertising-budget-optimizer`

**Repository Link:** Add your GitHub repository URL here.
