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
1- A bar chart showing the number of stores under each category.
  <img src="newplot (1).png" alt="stores" width="500"/>
  
2- A scatter plot chart showing the average rating for each category.
  <img src="newplot 10.png" alt="stores" width="500"/>

3- A pie chart showing the percentages of gold and silver certificates for all stores.
  <img src="newplot.png" alt="stores" width="500"/>

4- A bar chart that shows the average user interaction with stores under each category.
   <img src="newplot7.png" alt="stores" width="500"/>

5- A scatter plot Chart shows the top ten stores that received the most interaction from their customers.
   <img src="newplot (2).png" alt="stores" width="500"/>





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


### Team Members

