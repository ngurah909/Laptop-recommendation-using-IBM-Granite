# Laptop-recommendation-using-IBM-Granite

## Project Overview

This project implements a laptop recommendation system utilizing IBM Granite, a large language model (LLM) accessed via the Replicate API. The system classifies unique laptop products into categories such as Gaming, Productivity, Portable, and Budget. It then provides personalized laptop recommendations based on user preferences, enriched with summarized user reviews. The solution leverages advanced natural language processing capabilities of IBM Granite for data understanding, classification, and generating context-aware recommendations.

## Raw Dataset Link

The dataset used in this project is sourced from:
[Flipkart Laptop Reviews](https://www.kaggle.com/datasets/gitadityamaddali/flipkart-laptop-reviews)

## Insight & Findings

**Conclusion:**

1.  **Laptop Classification with IBM Granite (Unique Products):** The IBM Granite model (accessed via Replicate) proved effective in classifying each unique laptop product into categories such as Gaming, Productivity, Portable, and Budget. With improved prompt engineering and product-level classification, classification bias was successfully reduced, resulting in more accurate and logical categorization for each laptop model. This demonstrates the LLM's ability to understand and collectively categorize complex specifications and user reviews.

2.  **Patterns and Insights from Classification Categories (Unique Products):**
    * Laptops classified as 'Gaming' by Granite tend to have the highest average ratings and are characterized by superior GPU and RAM specifications. This shows a strong correlation between high-performance features and user satisfaction in this segment.
    * The 'Productivity' category shows a dominant distribution of 8GB and 16GB RAM, with the majority using SSDs as primary storage, affirming specification trends for everyday use.
    * 'Portable' laptops generally have smaller screen sizes and are often powered by energy-efficient processors like the Apple M-series, consistent with mobility needs.
    * The 'Budget' category exhibits greater variation in specifications and often more diverse ratings, reflecting the compromises made at this price point.
    * The aggregated average *overall rating* and *review rating* for each unique product also provide a more accurate dimension of user sentiment for each category.

3.  **Enhanced Recommendation System with Product Review Summaries:** Integrating IBM Granite-generated user *review* summaries into the recommendation process proved invaluable. The system not only recommends based on specifications and categories but also provides reasons enriched by the summarized user sentiments and experiences for that product. This enhances the relevance and trustworthiness of recommendations, making the user experience more personal and informative, and offering a comprehensive view of the product.

**Concrete Recommendations:**

1.  **For Consumers:**
    * When choosing a laptop, consider not only technical specifications and categories but also focus on "User Review Summary" and "Why Recommended" to get a complete picture of pros and cons from real user perspectives.
    * If on a tight budget, prioritize 'Budget' category laptops with the best average ratings and review summaries highlighting reliability or good value for money.
    * For specific uses like "gaming" or "video editing," look for recommendations in relevant categories and note how review summaries highlight performance in those tasks or aspects most valued by users.

2.  **For Sellers/Manufacturers:**
    * Analyzing sentiment from review summaries is a valuable asset for identifying features most appreciated or complained about by customers, aiding in future product development and marketing strategies.
    * Marketing can focus not only on specifications but also on positive user experiences captured in review summaries, especially for categories with high customer satisfaction.
    * For products with less positive review sentiment, review summaries will quickly highlight specific areas for improvement noted by users, allowing for faster and more targeted responses.

3.  **Future Enhancements:**
    * **Improved Feature Extraction from `product_name`:** While regex was used, LLMs can be further explored for more robust and nuanced feature extraction from `product_name` or more complex product descriptions, especially if there are large variations in naming.
    * **More Granular Sentiment Analysis:** Developing or utilizing more advanced sentiment analysis models (possibly also with LLMs) to measure sentiment from reviews more granularly (e.g., positive/negative sentiment towards battery, screen, keyboard) from review summaries.
    * **Hybrid Recommendation Systems:** Combining LLM-based approaches with traditional recommendation techniques (e.g., Collaborative Filtering if more user-item data is available) for stronger and more diversified recommendations.
    * **Interactive User Interface:** Creating a simple web application where users can interact with the recommendation system, view filters, and receive interactive explanations generated by the LLM.

## AI Support Explanation

* **AI Model Used:** This project exclusively leverages the capabilities of the large language model (LLM) **IBM Granite**, accessed through the **Replicate API**. The choice of Replicate allows for easy access to advanced models without heavy local infrastructure. The specific model ID used is `ibm-granite/granite-3.3-8b-instruct`.

* **How AI is Used:**
    * **Laptop Classification (Key Task on Unique Products):** IBM Granite serves as the primary classification engine for each **unique laptop product**. We provide IBM Granite with highly specific and structured prompts containing combined information from `product_name` (RAM, Storage, Processor, GPU, OS, Screen Size) and average ratings/review counts for the product. By providing clear criteria for each category (Gaming, Productivity, Portable, Budget), the model analyzes this rich input to assign the most appropriate single category to each laptop model. This effectively addresses issues of dual classification and bias, leveraging IBM Granite's deep natural language understanding (NLU) capabilities to interpret and categorize descriptive data at the product level.

    * **Product Review Summarization (Enhanced Recommendation Context):** IBM Granite is used to automatically summarize all user reviews associated with a single product. This is a crucial step for integrating user sentiment and experience into the recommendation process. By combining all unique review texts for each product and prompting Granite to generate a concise summary of sentiment and key points, we obtain rich qualitative context. These summaries then become essential additional input for the recommendation reason generation stage.

    * **Recommendation System (Understanding Preferences & Contextually Enriched Recommendation Reasons Generation):**
        * **User Preference Understanding:** IBM Granite processes user preferences input in natural language (e.g., usage needs, budget constraints, desired specifications) to identify the most suitable laptop category.
        * **Enriched Recommendation Reason Generation:** After relevant laptops are identified, IBM Granite generates explanations for why a particular laptop is suitable. These explanations are not only based on product specifications but intelligently *integrate the previously generated user review summaries*. This allows the recommendation reasons to include aspects such as user experience, reliability, or features highlighted most by the user community, resulting in recommendations that are much more technically accurate, nuanced, and trustworthy.

* **Benefits of Using AI (IBM Granite):**
    * **Leveraging Large-Scale Text Data:** IBM Granite enables this project to efficiently process and extract value from thousands of textual `product_name` and `review` entries, which would be extremely difficult and time-consuming with manual or simple rule-based methods, yielding meaningful features for classification and recommendation.
    * **Accurate and Contextual Classification:** With advanced language understanding and the ability to integrate detailed criteria, Granite can perform accurate classification at the unique product level, even for complex data, and reduce bias.
    * **More Personal and Trustworthy Recommendations:** Combining specification analysis with summarized sentiment from user reviews allows the system to provide recommendations that are not only technically sound but also convincing and relevant from a user experience perspective.
    * **Reduced Reliance on Manual Feature Engineering:** The use of LLMs significantly reduces the need for extensive feature engineering and separate classification model building, simplifying the data analysis workflow and allowing for a focus on higher-level insights.
    * **Understandable Explanations:** Granite's ability to generate recommendation reasons in natural language enhances system transparency and helps users make informed decisions.
