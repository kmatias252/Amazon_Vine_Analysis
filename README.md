# Amazon_Vine_Analysis

## Overview of Amazon Vine Analysis: 

The purpose of the Amazon Vine analysis was to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. In this project, I chose to analyze the video games dataset where I then used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, I used PySpark to determine if there is any bias toward favorable reviews from Vine members in your dataset. 

## Results:

### Deliverable 1: Perform ETL on Amazon Product Reviews 

Based on my knowledge of the cloud ETL process, I created an AWS RDS database with tables in pgAdmin based on the video games dataset. I then transformed the DataFrame into four separate DataFrames that match the table schema in pgAdmin. Lastly, I uploaded the transformed data into the appropriate tables and ran queries in pgAdmin to confirm that the data had been uploaded.

### Load Amazon Data into Spark DataFrame
![Screen Shot 2022-02-13 at 9 32 09 PM](https://user-images.githubusercontent.com/91925639/153790432-a50605fb-c6db-4758-acaa-882b53fe4e0c.png)

### Created the customers_table DataFrame
![Screen Shot 2022-02-13 at 9 32 20 PM](https://user-images.githubusercontent.com/91925639/153790439-10440f2c-0670-4823-8161-7359328a0532.png)

### Created the products_table DataFrame
![Screen Shot 2022-02-13 at 9 32 31 PM](https://user-images.githubusercontent.com/91925639/153790447-7518b279-576f-4e45-818e-b7f1d7e7d105.png)

### Created the review_id_table DataFrame
![Screen Shot 2022-02-13 at 9 32 42 PM](https://user-images.githubusercontent.com/91925639/153790475-e429f77e-3e24-42b2-ba4d-d3d1d848a13f.png)

### Created the vine_table DataFrame
![Screen Shot 2022-02-13 at 9 32 53 PM](https://user-images.githubusercontent.com/91925639/153790481-3edcba41-7b71-4982-8b23-6bbaaad25602.png)


### Deliverable 2: Determine Bias of Vine Reviews 

Using my knowledge of PySpark I determined if there was any bias towards reviews that were written as part of the Vine program. For this analysis, I had to determine if having a paid Vine review makes a difference in the percentage of 5-star reviews.

### Filtered the DataFrame on total_votes where the count was equal to or greater than 20
![Screen Shot 2022-02-13 at 9 44 22 PM](https://user-images.githubusercontent.com/91925639/153791460-a575eea2-4700-481c-b5e1-acf56f02ed35.png)

### Filtered the DataFrame so the amount of helpful_votes divided by total_votes is equal to or greater than 50%
![Screen Shot 2022-02-13 at 9 44 37 PM](https://user-images.githubusercontent.com/91925639/153791483-f7650b0e-ed93-4679-8ced-db3b8a796a5b.png)

### Filtered the DataFrame so all the rows where reviews written as part of the paid Vine program (vine== 'Y')
![Screen Shot 2022-02-13 at 9 44 48 PM](https://user-images.githubusercontent.com/91925639/153791488-f45c3b76-460e-46f0-91d2-35e72ff4c0fe.png)

### Filtered the DataFrame so all the rows where the reviews written as part of the unpaid Vine program (vine== 'N')
![Screen Shot 2022-02-13 at 9 44 57 PM](https://user-images.githubusercontent.com/91925639/153791495-227b4866-423c-43f9-ba95-1c1fdfc782ad.png)

### Results of the paid vs unpaid Vine review program
![Screen Shot 2022-02-13 at 9 45 08 PM](https://user-images.githubusercontent.com/91925639/153791508-a0b7913f-b179-47f8-a477-fbdb7142caa0.png)

* How many Vine reviews and non-Vine reviews were there?

  There were a total of 40,565 Vine reviews with 94 being paid Vine reviews and 40,471 being unpaid Vine reviews.
  
* How many Vine reviews were 5-stars? How many non-Vine reviews were 5-stars?

  There were a total of 15,711 5-star review with 48 being paid Vine reviews and 15,663 being unpaid Vine reviews.

* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

  51% of paid Vine reviews were 5-star reviews while 39% of unpaid Vine reviews were 5-star reviews.

## Summary: 

In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
