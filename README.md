# CryptoClustering
In this challenge, you'll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

# Lets get started
    • Ensure you have the following installed on your system:
                •	Python 3.x
                •	Pandas library (pip install pandas)
    • Clone the repository to your local machine: [GitHub Link] (https://github.com/ToniMak70/CryptoClusterin.git)

# Prepare the Data in jupyter notebook
    • Import required libraries and dependencies:
    • Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
    • Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
        •	The first five rows of the scaled DataFrame should appear as follows:
<img width="998" alt="scaled_DataFrame" src="https://github.com/user-attachments/assets/343e0bed-80ed-4cf6-bb58-2ae9ff564907" />

![df_market_data](https://github.com/user-attachments/assets/b3667b8e-f872-401e-bb7a-313a77f7a2d6)

# Find the Best Value for k Using the Scaled DataFrame
    Use the elbow method on the PCA data to find the best value for k using the following steps:
        •	Create a list with the number of k-values from 1 to 11. 
        •	Create an empty list to store the inertia values. 
        •	Create a for loop to compute the inertia with each possible value of k. 
        •	Create a dictionary with the data to plot the Elbow curve. 
        •	Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k. 
        •	Answer the following question in your notebook: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?

# Cluster Cryptocurrencies with K-means Using the PCA Data
    •	Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
    •	Initialize the K-means model with the best value for k. 
    •	Fit the K-means model using the PCA data. 
    •	Predict the clusters to group the cryptocurrencies using the PCA data. 
    •	Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters. 
    •	Create a scatter plot using hvPlot as follows: Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d". 
    •	Color the graph points with the labels found using K-means. 
    •	Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

# Optimize Clusters with Principal Component Analysis
    •	Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
    •	Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
        •	What is the total explained variance of the three principal components?
    •	Create a new DataFrame with the scaled PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
        •	The first five rows of the scaled PCA DataFrame should appear as follows:

<img width="303" alt="PCA_DataFrame" src="https://github.com/user-attachments/assets/95bfc911-2ba7-43e8-9165-c44ac14aec68" />

# Findings
    Elbow curve comparison:
        •Compared to the original data, the PCA-transformed data (elbow curve 2) exhibits a lower inertia value. This suggests that dimensionality reduction through PCA allowed for tighter clusters with fewer features, potentially improving clustering performance.
        

    Cluster plot comparison:
        •	Cluster Graph 1 (using original data): Using the original data in Cluster Graph 1 resulted in overlapping, poorly defined clusters. This indicates that the original feature set obscured, rather than revealed, the data's underlying cluster patterns.
        •	Cluster Graph 2: Utilizing PCA-reduced data, produces four readily identifiable and distinct clusters. This result implies that PCA successfully extracted meaningful patterns, leading to significantly improved cluster separation compared to the original data.

# Conclusion
    By utilizing PCA-derived features, we achieved a marked improvement in the K-Means clustering of cryptocurrency data. The resulting clusters are more well-defined and easily differentiated, indicating that PCA effectively streamlined the data and revealed underlying structures.

    
## File Structure
CryptoClustering/
├── Images/
│   ├── /cluster1.png/df_market_data.png/Elbow_Curve1.png/Elbow_curve2.png/PCA_DataFrame.png/PCA_plot.png/scaled_DataFrame.png
├── Resources/
│   ├── crypto_market_data.csv/
├── Crypto_Clustering.ipynb
├── LICENSE
└── README.md


## Acknowledgements
- Classmates: I recieved coding and debuging help from multiple classmates during breakout sessions.
- Internet Search: I utilized Google Search and slack overflow to research coding concepts, algorithms, and best practices.
- Support Staff: I recieved help from my instructor and class TA during office hours for help with debugging errors and further explanation for complex code segments.
- AI support: I leveraged Gemini AI and ChatGPT to generate code suggestions, debug errors, and provide explanations for complex code segments.
- Please note: While these tools were invaluable in my development process, the final code is the result of my analysis, testing, and refinement.
