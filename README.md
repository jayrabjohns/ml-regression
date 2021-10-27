<style>
    h3 {
        /* font-weight: bold; */
        font-style: italic;
    }
</style>

<h2>Understanding the task</h2>
We want to apply these steps:

1. Get the dataset
2. Understand the data, the attributes and their correlations
3. Split the data into training and test set
4. Apply normalisation, scaling and other transformations to the attributes if needed
5. Build a machine learning model
6. Evaluate the model and investigate the errors
7. Tune your model to improve performance

<h3><br/>'Does the task suggest a supervised or an unsupervised approach?'</h3>
Since the data set is labeled, a supervised approach would be appropriate.

<h3><br/>'Are you trying to predict a discrete or a continuous value?'</h3>
We're predicting median house price of some block group, a continuous variable.

<h3><br/>'Which ML algorithm is most suitable?'</h3>
As we are predicting a continuous variable, so we should use regression.
Whether we should be using a linear or non-linear model is yet to be determined. Before we make the decision we need to experiment with the data.
<hr>

<h2>Understanding the data</h2>
<h3><br/>'How is the data represented?'</h3>
Flat csv file. All bar one of the features are stored as floats, ocean distance is stored as one of 5 strings.

<h3><br/>'What do the attribute types suggest?'</h3>
Each feature represented by a float is continuous; ocean distance is discrete as it's represented by one of a predefined set of strings.

<h3><br/>'Are there any missing values in the dataset? If so, should you do anything about them?'</h3>
Yes, total_bedrooms is missing some entries when compared with the other features. The three ways of handeling this are:

1. remove the corresponding housing blocks from the dataset (i.e., remove the rows in the dataset)
2. remove the whole attribute (i.e., remove the column)
3. set the missing values to some predefined value (e.g., zero value, the mean, the median, the most frequent value of the attribute, etc.)
<hr>
<h2>Understanding data preparations</h2>
<p>When splitting the data into training & testing sets, stratified sampling gives us a much better representation of the data in comparison with random sampling.</p>
<p>Since several of the features are tail heavy (households, population, total_bedrooms, total_rooms, even median income toa  degree), it may be usefull to use the logs of these values to help better spread them out. This would improve oru RMSE in the end result.

<hr>
<h2>Understanding preliminary results</h2>
The notebook starts out with training a linear model with all 