# customer_segmentation
study_case_project_for_clustering

## Data Preprocessing
In every data processing that involves machine learning models, a data processing process is required before selecting and building the algorithm to be used, this is done in order to adjust to the characteristics possessed by each model and get optimal results.
In this project, we will do modeling using unsupervised clustering technique. The algorithm that will be used is K-Prototypes. One of the main factors when using this algorithm is that we need to equalize the scale between the variables. Besides that, we also need to encode the categorical columns into numerical ones. Then combine the data processing results into one data frame to be used in modeling.
### Exploration Data Analysis
After entering the data, reading and understanding the data. Next we do data exploration to dig deeper information from the dataset. The data we will explore is numerical data and also categorical data.
#### EDA for numerical data
The first thing we need to do is look at the data distribution of the numerical data. Here we will use a boxplot and also a histogram to see the data distribution. Here we use the seaborn library to plot each of the numeric columns, namely 'Age' and 'AnnualSpenddingScore'.
#### EDA for categorical data
In addition to numerical data, we also need to see how the data is distributed in categorical columns such as Gender, Profession and Resident Type. Here we use countplot from seaborn library.
#### Exploration Results to see Data Distribution:
1. Rata the average age of customers is 37.5 years old
2. Rata the average annual spending value of customers is 7,069,874.82
3. The gender of customers is dominated by women as many as 41 people (82%) and men as many as 9 people (18%)
4. Profesi most are self-employed (40%) followed by professionals (36%) and others (24%)
5. Of all customers 64% of them live in clusters and 36% of them live in the sector.

### Data Standardization
In order to get maximum results in the application of this algorithm, we need to make numerical data on an equal scale. This can be done using data standardization. The goal is so that variables that have a large scale do not dominate how the cluster will be formed and also each variable will be considered equally important by the algorithm that will be used.
In the results of the standardization process that we have done, it can be seen that the value after standardizing the mean value and standard deviation of each variable becomes 0 and 1. This shows that our data is already on the same scale.
### Label Encoding
Next, we convert the categorical columns into numbers. We will use one of sklearn's functions, LabelEncoder. This step is to convert the customer data from text to numeric.
For example, for the Gender column, the text “Male” will be converted to the number zero (0) and the text “Female” will be converted to the number one (1). We need this change for all texts before using it in the K-Prototype algorithm.

Jenis Kelamin (Gender)
0: Pria (Male)
1: Wanita (Female

Profesi (Profession)
0: Ibu Rumah Tangga (Housewife)
1: Mahasiswa (Unversity Student)
2: Pelajar (Student)
3: Profesional (Professional)
4: Enterpreneur

Tipe Residen (Resident Type):
1: Sector
0: Cluster

## Determining the Machine Learning Algorithm
Categorical data types usually use K-Modes for cluster analysis, while numerical data types usually use K-Means. However, if the data base consists of both numeric and categorical data types, then we can use the K-Prototypes algorithm.

## Determining the Optimal Number of Clusters
A critical parameter in the kprototype algorithm is the determination of the optimal number of clusters. One approach to identifying this number is the "elbow method," which involves the visualization of the total distance of all data points to their respective cluster centers. The elbow method is then used to identify the point at which the pattern becomes optimal, thereby determining the optimal number of clusters.
To determine the optimal number of clusters, the kprototypes algorithm must be executed with different numbers of clusters.Additionally, the cost_value should be stored and graphically represented using a line plot or point plot.

## From the observations we have made, we can give the segment name of each cluster number:
- Cluster 0: Diamond Young Entrepreneurs, the contents of this cluster are entrepreneurs who have an average transaction value of nearly 10 million. In addition, the contents of this cluster have an age of about 18 - 41 years with an average of 29 years.
- Cluster 1: Diamond Senior Entrepreneur, the contents of this cluster are entrepreneurs who have an average transaction value of close to 10 million. The contents of this cluster have an age of about 45 - 64 years with an average age of 55 years.
- Cluster 2: Silver Students, the contents of this cluster are students with an average age of 16 years and an annual spending value of nearly 3 million.
- Cluster 3: Gold Young Members, the contents of this cluster are young professionals and housewives with an age range of around 20 - 40 years and with an average age of 30 years and an annual spending value of close to 6 million.
- Cluster 4: Gold Senior Member, the contents of this cluster are old professionals and housewives with an age range of 46 - 63 years old and with an average age of 53 years old and their annual spending value is close to 6 million.

After naming the cluster, we can add a new column with the segment name. Then this column will be filled with the segment name of each customer based on the cluster value and we can display the amount of data we want.

## Running the model and making predictions
Now that we have the data ready to use, it's time to call up the previously saved model and proceed with making predictions.
To do this, we need to turn the process into a function called Modeling, using the new data as input.

Here we will construct a function that can be used to call the model, make predictions, and store the results in a dataframe. If the call is successful, we will get the cluster from the data we input.
