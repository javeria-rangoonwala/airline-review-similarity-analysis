# Airline Review Similarity Analysis

This project analyzes customer reviews of various airlines by calculating similarity scores based on predefined attribute categories such as **service**, **amenities**, **pricing**, and **logistics**. The goal is to gain insights into customer feedback and compare how airlines perform in different aspects.

## Project Overview

This project involves:
- Grouping and calculating similarity scores for different attributes found in customer reviews.
- Segmenting reviews based on **service**, **amenities**, **pricing**, and **logistics** attributes.
- Visualizing the results to compare airlines across various dimensions.

## Table of Contents
- [Data](#data)
- [Attributes](#attributes)
- [Methodology](#methodology)
- [Visualization](#visualization)
  

## Data

The project analyzes customer reviews from various airlines. Each review is categorized based on key attributes related to **service**, **amenities**, **pricing**, and **logistics**. The primary goal is to calculate similarity scores between reviews and predefined attribute segments.

### Data Format

The airline reviews are stored in a DataFrame with the following columns:

- `airline`: The name of the airline.
- `header`: The customer review text.
- `similarity_score`: The calculated similarity score for the review against a specific attribute segment.

An example of the data structure:

| airline  | header                                     | similarity_score |
|----------|--------------------------------------------|------------------|
| United Airline | "Great customer service and comfortable seats" | 0.85             |
| Southwest Airline | "Affordable but poor customer service"      | 0.62             |

---

## Attributes

The analysis is based on a set of predefined attribute categories. Each category contains multiple keywords that describe certain aspects of the airline's service. These attributes are grouped into four main segments:

1. **Service Attributes**:
   - Customer service
   - Welcoming
   - Warm
   - Respect
   - Friendly

2. **Amenities Attributes**:
   - Entertainment
   - Wi-Fi
   - Comfort
   - Seat

3. **Pricing Attributes**:
   - Affordable
   - Cheap

4. **Logistics Attributes**:
   - Safety
   - Baggage
   - On-time performance

These attributes are used to measure the similarity of each review against different airline qualities, helping to assess the performance of each airline across various dimensions.

---

## Methodology

1. **Data Preprocessing**:
   - The airline reviews are cleaned and preprocessed by converting them into string format.
   - The **spaCy** library's `en_core_web_lg` model is used to convert both the reviews and the attribute categories into vector representations (word embeddings).

2. **Similarity Score Calculation**:
   - For each review, the similarity score is calculated by comparing the review’s vector representation with the vectors of each attribute category (e.g., **service**, **amenities**, **pricing**, **logistics**).
   - The similarity score is computed using **cosine similarity**, which measures the angle between two vectors to determine how similar they are.

3. **Aggregation**:
   - After calculating the similarity scores for all reviews, the data is grouped by `airline` to compute the average similarity score for each attribute segment (e.g., the average score for all **service** reviews).

4. **Results**:
   - The resulting data gives insights into how well each airline performs in different attribute categories based on customer reviews.

---

## Visualization

The results of the similarity analysis are visualized using **Matplotlib** to help compare airlines across different attributes. A grouped bar chart is used to show the average similarity score for each airline and attribute segment.
