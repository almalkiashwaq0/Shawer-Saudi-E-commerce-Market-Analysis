# Capstone Project🎓🥳
# Shawer شاور

### This project aims to analyze the e-commerce market in the Kingdom of Saudi Arabia using the Maroof website, which serves as the primary source of licenses for e-commerce stores.

### Project Roadmap
- Collecting data
- EDA (Exploratory Data Analysis) and data quality check
- Building topic and sentiment analysis models
- Evaluation

### Collecting Data
- Data was collected from the Maroof website using web scraping.
- The first set of data collected focused on store information, including the following fields:
  - Arabic Name
  - English Name
  - Localized Name
  - Business Type
  - Other Type Name
  - Is Popular Business
  - Total Reviews
  - Rating
  - Maroof ID
  - Active Status
  - Owner Allow Status
  - Certification Status
- The second set of data collected focused on each store's comments, including the following fields:
  - Business ID
  - Review ID
  - Rating
  - Comment
  - Creation Date
 
### EDA (Exploratory Data Analysis) and data quality check
- **Relevance:** For the store information dataset, we dropped the `OtherTypeName` column.
- **Completeness:** There were two columns in the store information dataset that contained null values (`OtherTypeName` and `English Name`). In the second dataset, which focused on store comments, there were missing values in the `Comment` field, as some ratings were provided without a corresponding written comment. In this case, we dropped the rows with missing comment values.
- **Uniqueness**: There were no duplicates in both datasets.
- **Accuracy**: For the store comments dataset, we changed the `creation_date` column to the datetime data type.
- **Data Cleaning:** The comments had various issues. We cleaned the data by removing newlines, stripping whitespace, and eliminating emojis, special characters, numbers, English words and sentences, and repeated characters.

### Insights
1. A bar chart showing the number of stores under each category.  
   According to the chart, there is a significant difference in the number of stores across categories. Business Services has around 14k stores, whereas Real Estate has approximately 500.
   
   <img src="newplot (1).png" alt="stores" width="500"/>


2. A bar chart showing the average rating for each category.  
   We can observe that the average ratings are between 4 and 5 across all categories.
   
   <img src="newplot 9.png" alt="average ratings" width="500"/>


3. A pie chart showing the percentages of gold and silver certificates for all stores.  
   Most stores (63.7%) have silver certification, compared to 27.4% with gold certification.
    
   <img src="newplot.png" alt="certificates" width="500"/>


4. A bar chart showing the average user interaction with stores under each category.  
   Electronics have more reviews, even though Business Services have more stores than Electronics, with around 7,000 stores.
   
   <img src="newplot7.png" alt="user interactions" width="500"/>


5. A scatter plot showing the top ten stores that received the most interaction from their customers.  
   The store "أنا تقني" received more reviews than any other store, connected to the fact that Electronics had the most reviews.
   
   <img src="newplot (2).png" alt="top stores interaction" width="500"/>


6. A bar chart showing the average rating of the top twenty stores in user interaction.  
   We observe that the top 20 stores have similar ratings, with the lowest at 4.4 and the highest at 4.98.
    
   <img src="newplot 8.png" alt="average ratings top stores" width="500"/>



### Model
**Topic**
- Before starting the topic modeling, we split each comment based on special characters (such as `.` and `,`) and Arabic words commonly used to combine two different sentences (e.g., "بس" and "لكن") to extract each sentence's relevant topic.
- After the model provided results, we selected the most prominent and meaningful topics.
- We then manually selected 20 comments for each topic across four category types.
- We used the SetFit transform model on the manually chosen data to train the model for predicting the topics for the entire stors comments dataset.
- We achieved an accuracy of 92% for the Business Services category, 90% for Food, 82% for Beauty, and 90% for Health.

**Sentiment Analysis**
- For each topic, we analyzed which comments were negative and which were positive.
- We manually selected 100 positive comments and 100 negative comments for SetFit training, and then applied the model to the entire store comments dataset.
- We achieved an accuracy of 91%.

### DashBoard Link
https://app.powerbi.com/view?r=eyJrIjoiZGQyYWUxNDgtMmQ1Yi00Y2NkLTk5ZWMtM2Q5ODk1MWU3ZjUzIiwidCI6ImI0NTNkOTFiLTZhYzEtNGI2MS1iOGI4LTVlNjVlNDIyMjMzZiIsImMiOjl9

### Team Members
- [Samer Gharbi](https://linkedin.com/in/samer-gharbi-5709402ba)  
- [Mohammed Alamri](https://www.linkedin.com/in/mohammed-alamri-40315827b)  
- [Abdullah Thabet](https://www.linkedin.com/in/abdullah-thabet-093056204)
- [Dania Alshehri](https://sa.linkedin.com/in/dania-alshehri) 
- [Ashwaq Almalki](https://www.linkedin.com/in/ashwag-almalki-981338307?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app)


