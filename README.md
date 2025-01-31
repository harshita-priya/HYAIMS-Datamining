# Documentation for AI Data Mining System (HYAIMS Analytics)

## Overview
The AI Data Mining System, developed as part of Hyundai's HYAIMS Analytics, is a scalable web-based platform that automates data collection, processing, and sentiment analysis from multiple online sources. This project enhances decision-making for enterprises by providing insightful, categorized, and customizable datasets.

## Problem Statement
Organizations require data-driven insights from diverse online sources like social media, video platforms, and websites. Traditional manual data collection methods are inefficient and prone to error. An automated, robust system capable of handling large-scale data with advanced analytics was essential.

---

## System Architecture
The system follows a modular architecture comprising the following components:

### 1. Data Collection Module
- Tools Used: Selenium, BeautifulSoup, XPath, Requests.
- Functionality:
  - Scrapes data from platforms such as:
    - X (formerly Twitter)
    - YouTube
    - Facebook
    - Google
    - Customizable organizational websites.
  - Fetches metadata, user comments, and relevant content.
  - Handles dynamic content with Selenium for JavaScript-heavy websites.

### 2. Data Processing Module
- Tools Used: Python, Pandas, NumPy.
- Functionality:
  - Cleans and normalizes raw data.
  - Removes duplicates and irrelevant information.
  - Standardizes formats for date, location, and text.

### 3. NLP and Sentiment Analysis Module
- Tools Used: HuggingFace, TensorFlow, Scikit-learn.
- Functionality:
  - Uses pre-trained large language models (LLMs) for sentiment analysis.
  - Classifies text into categories like Positive, Negative, and Neutral.
  - Performs keyword-based topic extraction.

### 4. Data Storage and Retrieval Module
- Tools Used: AWS S3, ElasticSearch, Kibana.
- Functionality:
  - Stores structured data in cloud storage for scalability.
  - Indexes data for quick retrieval.
  - Uses Kibana for interactive dashboards and visualizations.

### 5. Frontend and Backend Development
- Frontend Tools: JavaScript, HTML, CSS.
- Backend Tools: Django, Flask.
- Functionality:
  - User-friendly interface for defining queries and downloading results.
  - Supports output in formats like CSV and Excel.

---

## Key Features
- Customizable Keyword Search: Users can input specific keywords and configure data sources.
- Multi-Platform Compatibility: Handles diverse platforms and websites seamlessly.
- Categorized Outputs: Results include parameters like OEM, year, location, sentiment, etc.
- Scalable Infrastructure: Uses cloud services to manage large datasets efficiently.

---

## Key Projects and Use Cases
### 1. EV Charging Door Module Overview
- Objective: Analyze trends in EV charging module features.
- Approach:
  - Mined user feedback and technical reviews.
  - Categorized results by manufacturer and region.

### 2. Voice Recognition Trends in OEMs
- Objective: Track the evolution of voice recognition technology across Original Equipment Manufacturers (OEMs).
- Approach:
  - Identified major trends in VR adoption.
  - Conducted sentiment analysis on user feedback.

### 3. Car Seating Analysis
- Objective: Evaluate seating comfort and features in vehicles.
- Approach:
  - Collected reviews and ratings from platforms.
  - Categorized data by seating arrangement, comfort level, and space utilization.

### 4. Infotainment Reviews
- Objective: Assess infotainment system performance in vehicles.
- Approach:
  - Extracted reviews on cluster design, leg space, and boot space.
  - Highlighted user-preferred features and pain points.

---

## Workflow (Pseudocode)
```python
# Step 1: Data Collection
for platform in platforms:
    if platform.requires_dynamic_loading:
        data = scrape_with_selenium(platform.url, keywords)
    else:
        data = scrape_with_beautifulsoup(platform.url, keywords)
    save_to_temp_storage(data)

# Step 2: Data Processing
raw_data = load_temp_storage()
clean_data = clean_and_normalize(raw_data)

# Step 3: Sentiment Analysis
for entry in clean_data:
    entry['sentiment'] = perform_sentiment_analysis(entry['text'])
    entry['category'] = extract_keywords(entry['text'])

# Step 4: Data Storage
upload_to_s3(clean_data, bucket_name)
index_data_in_elasticsearch(clean_data)

# Step 5: Visualization
create_kibana_dashboard(elasticsearch_index)
```

---

## Impact and Achievements
- Efficiency: Reduced manual data collection time by over 80%.
- Accuracy: Achieved 95% precision in sentiment classification.
- Scalability: Processed over 1TB of data seamlessly using cloud solutions.
- User Adoption: Successfully deployed across multiple organizational units.

---

## Future Enhancements
- Real-Time Analytics: Implement streaming data pipelines.
- Integration with BI Tools: Enable direct export to Tableau and Power BI.
- Advanced Sentiment Analysis: Incorporate emotion detection and context-aware models.

