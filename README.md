# Online-Retail-Marketing-Analytics

## Business Problem: 
ShopEasy, a growing online retail business, is experiencing a decline in customer engagement and conversion rates despite investing heavily in new marketing campaigns. The business seeks a detailed marketing performance analysis to identify areas of improvement.

## Key challenges include:

1. **Reduced Customer Engagement:** Fewer interactions with the website and marketing content.

2. **Decreased Conversion Rates:** A lower percentage of visitors are completing purchases.

3. **High Marketing Costs:** Marketing campaigns are not delivering the expected returns.

4. **Need for Customer Feedback Insights:** Understanding customer sentiment is essential to optimize strategies and drive better engagement and conversions.

## Key Performance Indicators (KPIs):

1. **Conversion Rate:** Percentage of website visitors who make a purchase.
2. **Customer Engagement Rate:** Level of interaction with marketing content (clicks, likes, comments).
3. **Average Order Value (AOV):** Average amount spent by a customer per transaction.
4. **Customer Feedback Score:** Average rating from customer reviews.

## Project Goals:

### Increase Conversion Rates:

  **Goal:** Identify factors impacting the conversion rate and provide recommendations to improve it.  
  **Insight:** Highlight key stages where visitors drop off and suggest improvements to optimize the conversion funnel.
   
### Enhance Customer Engagement:

  **Goal:** Determine which types of content drive the highest engagement.  
  **Insight:** Analyze interaction levels with different types of marketing content to inform better content strategies.
  
### Improve Customer Feedback Scores:

  **Goal:** Understand common themes in customer reviews and provide actionable insights.  
  **Insight:** Identify recurring positive and negative feedback to guide product and service improvements.

## Data Understanding and Preparation

### Data Model Overview:

**Dimension Tables:**

    dim_customers
    
    dim_products
    
    dim_calendar

**Fact Tables:**

    fact_customer_journey
    
    fact_customer_reviews
    
    fact_customer_engagement_data

    fact_customer_reviews_with_sentiment (created after performing sentiment analysis in Python)

  Below is the Power BI Data Model Snapshot:
   

  The data model is structured in a star schema format, where dim_customers, dim_products, and dim_calendar serve as the dimension tables, providing descriptive attributes.
  All fact tables — fact_customer_journey, fact_customer_reviews, fact_customer_engagement_data, and fact_customer_reviews_with_sentiment — are connected to the respective dimension tables using primary keys      
  (like Customer ID, Product ID, Date ID).
  This structure ensures efficient slicing and dicing of data, enabling faster insights across customer behavior, engagement, and sentiment analysis.

  ### Data Cleaning and Transformation
  
1. Customers Table:

     Joined customers and geography tables in SQL (SSMS) to remove redundancy and avoid duplication.

2. Products Table:

     Created a Price Category column based on product prices:

      Low
    
      Medium
    
      High

3. Customer Reviews Table:

     Replaced extra spaces in customer reviews with a single space for consistency.

4. Customer Engagement Data Table:

    Standardized the Content Type column by converting all entries for Social Media Content type to uppercase.
  
    Split the combined Likes and Views data into two separate columns: Likes and Views.
  
    Filtered out entries where Content Type != 'Newsletter', as they were not relevant for marketing performance.

5. Customer Journey Records Table:

    Identified and removed duplicate records.
    
    Replaced missing (NULL) values in the Duration column with the average duration.

6. Sentiment Analysis on Customer Reviews:

    Performed sentiment analysis using Python to enrich the fact_customer_reviews table.

7. Generated:

    Sentiment Score (numeric score)
    
    Sentiment Bucket (Positive, Neutral, Negative)
    
    Sentiment Category (based on score range)

## Insights:

### Overview

  1. Conversion Rate Trends:  
     After experiencing a significant drop to 5.0% in October, the conversion rate recovered strongly, reaching 10.2% by December.

  2. Customer Engagement Patterns:  
     Overall social media engagement declined, with a steady decrease in views across the year.  
     Despite lower clicks and likes relative to views, the click-through rate remains healthy at 15.37%, indicating that the engaged audience is still interacting meaningfully.

  3. Customer Feedback Insights:  
     Customer ratings have remained stable, averaging around 3.7 throughout the year.  
     However, this is below the target rating of 4.0, highlighting an opportunity to improve customer satisfaction, especially for products rated below 3.5.

### Decreased Conversion Rates

  1. Overall Trend:
     Conversion rates fluctuated throughout the year, with stronger performance observed in months like February and July. This points to seasonal peaks for certain products and highlights opportunities to boost      conversions in lower-performing months through focused marketing efforts.

  2. Lowest Conversion Month:
     May recorded the lowest conversion rate at 4.5%, with no standout products. This suggests a need to reassess marketing campaigns and promotional strategies during this period to improve results.

  3. Highest Conversion Month:
     January achieved the highest conversion rate at 19.6%, largely driven by Ski Boots, which showed an exceptional 150% conversion. This reflects a strong seasonal demand combined with successful marketing     
     execution.

### Reduced Customer Engagement 

  1. Declining Views:  
     Views reached their highest points in February and July but began to drop starting in August, reflecting a decrease in audience engagement during the latter half of the year.

  2. Low Interaction Rates:  
     Clicks and likes remained consistently lower compared to views, indicating a need for more compelling content or more effective calls to action to increase user engagement.

  3. Content Type Performance:  
     Blog posts generated the most views, particularly in April and July, while social media and video content showed steady but slightly lower engagement levels.

### Customer Feedback Analysis

  1. Customer Ratings Overview:
     A significant portion of customer reviews fall within the higher ratings, with 140 reviews at 4 stars and 135 reviews at 5 stars, reflecting a generally positive reception. In contrast, lower ratings (1-2        stars) make up a smaller share, with 26 reviews at 1 star and 57 reviews at 2 stars.

  2. Sentiment Analysis:
     The majority of reviews display a positive sentiment, with 275 reviews indicating customer satisfaction. Negative sentiment appears in 82 reviews, while a smaller number of reviews show mixed or neutral   
     sentiments, pointing to some areas for improvement, but overall, customers are highly satisfied.

  3. Areas for Improvement:
     The presence of mixed positive and mixed negative sentiments highlights opportunities to turn these less certain experiences into more positive ones, which could lead to improved overall ratings. Addressing      the concerns raised in these mixed reviews could help further boost customer satisfaction.

## Goals and Actions

### Goals:

  1. Increase Conversion Rates:
     Goal: Identify factors impacting the conversion rate and provide recommendations to improve it.  
     Insight: Highlight key stages where visitors drop off and suggest improvements to optimize the conversion funnel.
     
  3. Enhance Customer Engagement:  
     Goal: Determine which types of content drive the highest engagement.   
     Insight: Analyze interaction levels with different types of marketing content to inform better content strategies.
     
  5. Improve Customer Feedback Scores:
     Goal: Understand common themes in customer reviews and provide actionable insights.  
     Insight: Identify recurring positive and negative feedback to guide product and service improvements.
     
### Actions:

  1. Boost Conversion Rates:  
     Leverage High-Performing Product Categories: Direct marketing resources towards products that have shown strong conversion rates, like Kayaks, Ski Boots, and Baseball Gloves. Launch seasonal promotions or        personalized campaigns during peak months (e.g., January and September) to take full advantage of these trends.

  2. Enhance Customer Engagement:  
     Revamp Content Strategy: To reverse the decline in views and engagement, experiment with more interactive content formats, such as videos and user-generated content. Additionally, improve engagement by           strategically placing calls to action in social media posts and blog articles, especially during months with historically lower engagement (September-December).

  3. Improve Customer Feedback Scores:  
     Address Mixed and Negative Reviews: Create a feedback loop to thoroughly analyze mixed and negative reviews, identifying recurring issues. Use this insight to develop targeted improvement plans. Follow up        with dissatisfied customers to resolve their concerns and encourage them to re-rate, aiming to bring average ratings closer to the target of 4.0.

## Acknowledgement

Special thanks to [Ali Ahmad] ([https://www.linkedin.com/in/aliahmaddata/]) whose project on marketing data analytics served as inspiration.

## Let's Connect

In case of any query, Please free to connect!  [http://www.linkedin.com/in/sadhanadubey28]
