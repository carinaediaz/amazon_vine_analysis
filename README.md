# Amazon Vine Analysis
## Overview
##### We were tasked with performing an analysis of Amazon reviews and any impact of participating in the Vine Review Program. The Vine Review Program was in incentive program that would send out gift products to select good reviewers at a cost to the vendor, in an effort to incentivize more good reviews. The purpose of this task was to help our client determine if participating in the Vine Review Program would be beneficial for their new launch. We utilized Python, PySpark, PostgreSQL, AWS's RDS and S3. 
## Results
##### Our client sells pet products, so we selected the Amazon review dataset pertaining to pet products to analyze (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz). Below is a snapshot of the initial dataframe we imported from the S3 link. 
![complete_df.PNG](https://github.com/carinaediaz/amazon_vine_analysis/blob/main/Images/complete_df.PNG)
##### We then grouped and filtered the dataframe to produce the customers_table, products_table, review_id_table, and vine_table. From here, we filtered the vine_table to only include reviews with 20 or greater total votes, greater than or equal to 50% helpfulness, and then dividing the dataframe by paid vs unpaid five-star reviews. Summaries of our findings are below. 
![paid_reviews.PNG](https://github.com/carinaediaz/amazon_vine_analysis/blob/main/Images/paid_reviews.PNG)
![unpaid_reviews.PNG](https://github.com/carinaediaz/amazon_vine_analysis/blob/main/Images/unpaid_reviews.PNG)
Paid Five-Star Reviews:
- Total count of paid reviews: 170
- Count of paid reviews with five-stars: 65
- Percentage of paid reviews with five-stars: 38.2% 
Unpaid Five-Star Reviews:
- Total count of unpaid reviews: 37840
- Count of unpaid reviews with five-stars: 20612
- Percentage of unpaid reviews with five-stars: 54.4%
## Summary
##### Based on our findings, there does not appear to be a bias between paid vs unpaid five-star reviews, as a higher percentage (54.4%) of unpaid reviews were five-stars vs paid reviews (38.2%). This could be due to the considerably smaller count of reviews that were paid vs unpaid. It seems that vendors who sell pet products do not heavily participate in the Vine Review Program. Additional analysis on how other departments compare to the pet products department would be beneficial to put our paid vs unpaid five-star reviews analysis into a large-scale context. Additionally, we could use National Language Processing models to help analyze the text of the reviews rather than just their star rating was. This would help venders collect more insight into what aspects of a product/service experience customers prefer more than others.
