# CGM Product Analysis
This project analyzes a sample of over 37K social media posts related to Continuous Glucose Monitoring (CGM) for diabetes management. The goal is to answer several questions related to patient expectations, benefits, and unmet needs of CGMs, as well as a product analysis of Dexcom and Freestyle Libre.
This project aims to provide insights into patient expectations, benefits, and unmet needs of CGMs, as well as a product analysis of Dexcom and Freestyle Libre. The report and presentation will highlight key findings and provide recommendations for improvement for each brand.


## The Data
A market researcher based out of Pittsburgh provided the sample of over 37K social media posts related to CGMs, available in the data folder as Diabetes Continuous Glucose Monitoring – Data Export.xlsx. Each row of the Excel file consists of a field of text called Sound Bite Text, along with a variety of other more structured metadata fields such as the source and when the Sound Bite Text field was extracted.


## Exploratory Data Analysis
Before starting with our Exploratory Data Analysis, we looked at the columns in our data. We saw that the data set had 37844 rows and 63 columns. As a part of preprocessing, we identified five relevant columns- Post ID, Sound Bite Text, Title, Sentiment, and Post Type. We also noticed that the remaining columns had mostly nulls, including some columns like Author Gender, Professions, and Interests that could’ve been used for segmentation.

## Steps
We followed these steps in our Exploratory Data Analysis:

Step 1: Understand the dataset
To start, we quickly checked our data to find any nulls. We found 1571 nulls in the Title column and 2679 nulls in the Post Type column. In the initially tagged sentiment, there were four distinct values- Neutrals, Positives, Mixed, and Negatives, with the most count for Negatives (approximately 24,000). We found that the Post Type column had two distinct values- Replies and Comments and Original. We filtered our data and kept only relevant rows where the Sound Bite Text column had either of the keywords: 'cgm', 'dexcom', 'libre', 'freestyle', 'continuous glucose monitoring', and 'continuous glucose monitor'. After filtering, our dataset had 36,481 rows.

Step 2: Reassign sentiments
We performed our sentiment analysis on the Sound Bite Text and Title using two models- TextBlob and Vader. We calculated the mean of both columns as the final sentiment score. Upon performing manual sentiment analysis on a sample data set, we concluded that the sentiments assigned by the Vader model are more accurate.

Step 3: Data cleanup
Data cleansing helps remove noise from the data. It allows for accurate, defensible data that generate reliable conclusions, visualizations, and models and are essential for making precise business decisions. We performed the following steps to clean our data and ensure that we had the best possible data set to perform the further analysis:

Remove posts unrelated to CGM: We limit our analysis to only relevant data. To do this, we only keep posts about CGM, Dexcom, or Freestyle Libre.

Convert the text to lowercase: By converting our text to lowercase, we ensure that we do not cause any discrepancies when we perform data comparisons.

Remove stop-words: Stop-words are words that do not add much meaning to a sentence. We can ignore these words and not sacrifice the meaning of the sentence.

Remove mentions: These words do not add any value to the context of the post. So, we have removed them.

Remove URLs: URLs are not fit for sentiment analysis; hence, removing them will help us perform a more accurate analysis.

Remove numerical values: Numbers are not significant for the sentiment analysis of this data set.

Remove punctuations: Punctuations are used to divide the text into sentences and are unhelpful to our sentiment analysis.

Remove single characters: They are not significant as they do not add value to sentiment analysis.

Step 4: Tokenization
Tokenization is a process of breaking up a text into units called tokens. Tokens can be individual words, phrases, or sentences. It helps in interpreting the reader with the help of a sequence of words. In this process, we split the text into a set of words.

Step 5: POS Tagging
After tokenization, we used the Natural Language Toolkit (nltk) library to perform part-of-speech tagging. This process identifies the nouns, verbs, adjectives, and adverbs in the text, which can be useful for customer segmentation and identifying user expectations and knowledge gaps. However, we found that an alternative approach of using phrases like "I wish" or "I expect" worked better for our analysis.


## The project will answer the following questions:

## General CGM Analysis
1. What are patient expectations of CGMs? What are patient knowledge gaps with CGMs?

2. What benefits are most important to diabetes patients?

3. What unmet needs do patients have related to CGMs (something patients want but are not getting)?

## CGM Product-related Analysis
1. What are praises & complaints and features of Dexcom & Freestyle Libre?

2. What product features are being talked about?

3. How do consumer opinions of Dexcom and Freestyle Libre compare?

4. What is the overall sentiment regarding the two products?

5. Based on your analysis, which one would you recommend?

6. What would you tell each of these brands to improve?

## CGM Consumer-related Analysis
1. Can you identify different types (segments) of consumers or create segments?

2. Are different benefits more important to different consumer types?


The intention behind the assignment is to use tools for text preprocessing and analysis (e.g. stemming, POS tagging, topic modeling, sentiment analysis, etc.) combined with manual review/interpretation of the outputs. The project allows for outside research to validate/supplement the findings, especially if unfamiliar with the domain, and to apply other more sophisticated text analysis techniques. However, these techniques should not be required.
