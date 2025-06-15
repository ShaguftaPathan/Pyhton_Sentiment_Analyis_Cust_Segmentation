
# Customer Behavior Analysis using Python (Sentiment Analysis + RFM Segmentation)

<a href= "https://shaguftapathan.github.io/Pyhton_Sentiment_Analyis_Cust_Segmentation/">View Project</a>

# <span style="color:#4a89c2; font-size:26px;"><b>Motivation</b></span>  

Understanding customer behavior is vital for any e-commerce business aiming to improve user experience, increase retention, and boost sales. While customer reviews provide emotional feedback, transactional data reveals behavioral patterns. This project combines both:

- **Sentiment Analysis** to assess customer emotions from reviews
- **Customer Segmentation (RFM + K-Means)** to group customers based on purchasing behavior

By integrating these perspectives, we deliver actionable insights for improving product offerings, delivery experience, and personalized marketing.

---

# <span style="color:#4a89c2; font-size:26px;"><b>Dataset</b></span>  

The dataset is a blend of transactional and textual feedback, consisting of the following key features:

* `Customer_ID`
* `Order_ID`
* `Order_Date`, `Delivery_Date`
* `Customer_Review` (Review Text)
*  `Delivery_Status`
*  `Shipping_Partner`
*  `City`, `State`
*  `Quantity`, `Unit Price`, `Total`

Source: Google Analytics API and customer review systems  
Time Period: Dec 2023 – May 2025

---

# <span style="color:#4a89c2; font-size:26px;"><b>Project verview</b></span>  

We approached this analysis in two major parts:

1. **Sentiment Analysis with VADER**  
   To automatically classify thousands of customer reviews into detailed emotional categories.

2. **Customer Segmentation with RFM & K-Means**  
   To profile customers based on their purchase recency, frequency, and monetary value.

Together, these methods offer a 360° view of customer behavior — what they feel and how they act.

---

# <span style="color:#4a89c2; font-size:26px;"><b>Methodology</b></span>  

# <span style="color:#4a89c2; font-size:22px;">Sentiment Analysis (NLP-VADER)</b></span>  

* Used `SentimentIntensityAnalyzer` from `nltk.sentiment.vader`
* Extracted four sentiment scores
* `pos` (positive), `neu` (neutral), `neg` (negative), `compound` (overall)
* Applied custom thresholds on compound score to classify reviews into:
* Positive, Mixed Positive, Neutral, Mixed Negative, Negative

## Example
* "Nice product but delivery was delayed" → **Mixed Positive**
* "Good features, poor customer service" → **Mixed Negative**

![](/Images_Sentiment/Reviews.png)

## Visualizations
### Polarity distribution

**Max Score 0.8047**  
**Min Score -0.6369**

We used the compound score from VADER to classify each review into five sentiment categories:
* Positive: compound between 0.5164 and 0.8047  
* Mixed Positive: compound between 0.2281 and 0.5164  
* Neutral: compound between -0.0603 and 0.2281  
* Mixed Negative: compound between -0.3486 and -0.0603  
* Negative: compound less than -0.3486

![](/Images_Sentiment/Polarity_Score.png)

### Sentiment category bar chart
Bar Chart: Count of reviews in each sentiment category (Positive, Mixed Positive, Neutral, Mixed Negative, Negative).  
Helps identify which sentiments are most common among customers

![](/Images_Sentiment/Chart.png)

---

# <span style="color:#4a89c2; font-size:22px;">Customer Segmentaion (RFM + K-Means)</b></span>  
## Engineered RFM metrics:
* **Recency**: Days since last purchase
* **Frequency**: Count of orders
*  **Monetary**: Total spend
* Scored customers using quantiles
* Standardized values and applied **K-Means Clustering**
* Used Elbow Method and Silhouette Score to determine optimal `k`
* Labeled segments:
* Top Customers
* Average Customers
* Lapsed Customers

## Visualizations
### RFM score

![](/Images_Cust_Seg/RFM.png)  

### Cluster distribution
 * Standardized RFM values using StandardScaler
 * Applied K-Means Clustering
 * Chose optimal k using Elbow Method and Silhouette Score  

![](/Images_Cust_Seg/Clusters.png)
![](/Images_Cust_Seg/Status.png)  

### Segment-wise count chart
 * Cluster distribution using Seaborn
 * Bar charts to interpret segments
 * Labeled clusters ("Top Customers", "Average Customers", "Lapsed Customers")  

![](/Images_Cust_Seg/Chart.png)  

---

# <span style="color:#4a89c2; font-size:26px;"><b>Tools & Libraries</b></span>  

| Sentiment Analysis            | Customer Segmentation         |
|------------------------------|-------------------------------|
| Python                       | Python                        |
| NLTK (VADER)                 | Pandas, NumPy                 |
| Pandas                       | Scikit-learn (KMeans)         |
| Matplotlib, Seaborn          | Matplotlib, Seaborn           |
| Jupyter Notebook             | Jupyter Notebook              |

---

# <span style="color:#4a89c2; font-size:26px;"><b>Key Outcomes</b></span>  

* Classified 4,356 reviews into 5 detailed sentiment categories using custom VADER logic
* Identified major pain points in delivery and service through textual analysis
* Segmented customers into high-, medium-, and low-value groups
* Informed campaign strategies to re-engage lapsed customers and retain top spenders

---

# <span style="color:#4a89c2; font-size:26px;"><b>Conclusion</b></span>  

This combined project showcases how **textual feedback** and **purchase behavior** can be jointly analyzed to drive customer-centric decisions. The sentiment layer surfaces emotional trends, while RFM clustering uncovers structural segments in the customer base.

