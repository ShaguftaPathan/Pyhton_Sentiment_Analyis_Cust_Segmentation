NLP project to analyze customer feedback for an e-Commerce client and classifies sentiments into Positive, Negative, Neutral, and Mixed Sentiments using the VADER algorithm.

Understanding customer feedback at scale is essential for improving products and services. Manual review of feedback is slow and subjective, so this project automates the process using a rule-based sentiment analyzer that is well-suited for short, informal text formats like:
* Product reviews
* Survey responses
* Social media comments
The goal is to quickly detect emotional tone, uncover problem areas, and enhance decision-making through data-driven insights.

# Dataset
The dataset consists of:
  * Customer_ID
  * Order_ID
  * Order_Date
  * Deliver_Date
  * Customer_Review(Review Text)
  * Delivery_status
  * Shipping_Partner
  * City
  * State

# Methodology
**VADER Sentiment Analysis**
  * Used SentimentIntensityAnalyzer from nltk.sentiment.vader
  * Extracted sentiment scores from Customer_Review(Review Text):
    o	pos: Positive score
    o	neu: Neutral score
    o	neg: Negative score
    o	compound: Aggregated score between -1 and +1

# Custom Classification Logic
Find out the polarity score for each Order.

![](https://raw.githubusercontent.com/ShaguftaPathan/Pyhton-NLP_Sentiment_Analysis/main/Images_Sentiment/Polarity_Score.png)

**Max Score 0.8047**
**Min Score -0.6369**

We used the compound score from VADER to classify each review into five sentiment categories:
* Positive: compound between 0.5164 and 0.8047
* Mixed Positive: compound between 0.2281 and 0.5164
* Neutral: compound between -0.0603 and 0.2281
* Mixed Negative: compound between -0.3486 and -0.0603
* Negative: compound less than -0.3486

![](/Images_Sentiment/Reviews.png)

This custom logic helps capture more detailed emotional tone.
For example:
“Great product, but delivery was late.” → Mixed Positive
“Nice features, but poor customer service.” → Mixed Negative

# Visualizations
Bar Chart: Count of reviews in each sentiment category (Positive, Mixed Positive, Neutral, Mixed Negative, Negative).
Helps identify which sentiments are most common among customers

![](/Images_Sentiment/Chart.png)

# Tools & Libraries
  * Python
  * NLTK – VADER sentiment analysis
  * Pandas – Data manipulation
  * Matplotlib / Seaborn - Visualization

# Key Outcomes
  * Classified 4356 reviews into 5 custom sentiment buckets (Positive, Mixed Positive, Neutral, Mixed Negative, Negative).
  * Identified top drivers of negative and mixed feedback
  * Helped prioritize operational improvements (e.g., delivery, support quality)
  * Enabled product teams to understand customer tone at a glance

<a href="https://github.com/ShaguftaPathan/Pyhton-NLP_Sentiment_Analysis/blob/main/Sentiment%20Analysis_CCTV.ipynb">View Complete Jupyter Notebook</a>

# Summary
This project demonstrates the power of lightweight, rule-based models like VADER for rapid and interpretable sentiment classification. While not deep-learning based, its transparency and speed make it highly effective for short-form feedback analytics.
