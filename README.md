# XG boost
Data Analysis examples

### reference link
https://www.analyticsvidhya.com/blog/2016/01/xgboost-algorithm-easy-steps/#comment-116591

#### Preparation of Data for using XGBoost
XGBoost only works with numeric vectors. Yes! you need to work on data types here.

Therefore, you need to convert all other forms of data into numeric vectors. A simple method to convert categorical variable into numeric vector is One Hot Encoding. This term emanates from digital circuit language, where it means an array of binary signals and only legal values are 0s and 1s.

In R, one hot encoding is quite easy. This step (shown below) will essentially make a sparse matrix using flags on every possible value of that variable. Sparse Matrix is a matrix where most of the values of zeros. Conversely, a dense matrix is a matrix where most of the values are non-zeros.

Let’s assume, you have a dataset named ‘campaign’ and want to convert all categorical variables into such flags except the response variable. Here is how you do it :

##### sparse_matrix <- sparse.model.matrix(response ~ .-1, data = campaign)

Now let’s break down this code as follows:

1. “sparse.model.matrix” is the command and all other inputs inside parentheses are parameters.
2. The parameter “response” says that this statement should ignore “response” variable.
3. “-1” removes an extra column which this command creates as the first column.
4. And finally you specify the dataset name.
To convert the target variables as well, you can use following code:

##### output_vector = df[,response] == "Responder"
Here is what the code does:

1. set output_vector to 0
2. set output_vector to 1 for rows where response is "Responder" is TRUE ;
3. return  output_vector.
 
