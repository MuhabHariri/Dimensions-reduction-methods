# Introduction:
Technological development, spread of social media and increase in machine learning applications have led to an increase in the amount of available data. The large amount of available data that can be used to solve a particular problem in machine learning applications is not always valuable as excessive data may cause several problems such as long training time, overfitting and what is known as the curse of dimensionality.
In many problems there may be tens or hundreds of features that describe the input of the algorithm and sometimes it may be necessary to reduce these features as much as possible to avoid the previously mentioned problems and make the data understandable.
Dimension reduction methods are divided into two categories: feature selection and feature extraction.
Feature selection is the process of selecting important dimensions.
Feature extraction is the process of finding new features by selecting or combining existing features to create a smaller space of the features while keeping as much information as possible from being lost.
The methods that can be used to reduce the dimensions differ according to the data type as some methods are dedicated to the labeled data where the supervised learning technology is used. Other methods are specific to the unlabeled data where the unsupervised learning technology is used.
Many methods can be used to reduce dimensions such as Factor Analysis, Backward Feature Elimination, Independent Component Analysis, Principal Component Analysis, Relief and Maximum Relevance — Minimum Redundancy. In this work, the last three methods will be discussed and applied.
Principal Component Analysis (PCA) is an unsupervised linear transformation technique, it is commonly used to extract the features (feature extraction) and reduce the dimensions. This technique tries to identify the patterns by extracting the correlation between the features in the data. Relief is a feature selection technique works to estimate the quality of features depending on how well the feature can distinguish between instances that are near to each other. The core idea behind MRMR algorithms (Maximum Relevance — Minimum Redundancy) is to find low number of the features that together have maximum possible predictive power and achieve the best accuracy.
# MATERIALS AND METHODS:
## Datasets Description
In this work three datasets of different sizes were used to evaluate the algorithms and compare the results.
The first and largest dataset was taken from “Mendeley Data” website and includes information from approximately 2978 respondents. This information includes 94 features like age, gender, sources of Covid-19 updates, financial status, race and education level all of which were collected through a survey.
The survey was conducted on the assumption that socio-demographic factors can affect the decision about accepting a vaccine or not. The features in the dataset were used as input while “covid_vaccine” feature was used as output. “covid_vaccine” feature represents the answer of the question: Would you like to get COVID-19 vaccine, If available?

Second dataset belong to lung cancer and includes information about 1000 people. This information includes 23 features like age, obesity, smoking and air pollution. The output determines if the risk of developing lung cancer is high, medium or low.
The third and smallest dataset includes information about the wine. This information is divided into 11 features and the output is numbered between 3 and 8, where 8 represents the best quality.
## Data Processing
The first and largest database that was used in this project was not ideal as it had many flaws such as misinformation. In addition, there are many features which have object type and must be converted into numeric to allow computer interpretation.
Initially, the data was checked to get idea about the null cells for each feature. The features which have a high number of null cells were dropped. Most of the dropped features are not important and don’t affect the prediction task (i.e. US_State, child and nasal_spray). For example, the state where the respondent lives doesn&#39;t affect his decision to accept or refuse the vaccine. The number of remaining features is 74.

Many of these 74 features also have null cells but they were treated in a different way; however, the null cells in these features were filled with the most frequent integer, float or object. For example, the most frequent integer in “healthcare_worker” feature was 0. This feature describes if the respondent is healthcare worker (1) or not (0).
The same procedure was applied to the features which have object components where the null cells were filled with the most frequent object. After filling the null cells, object values in the features were replaced by integers to present it which is an important step for prediction task. For example, the components of the feature “Gender_string” were replaced as follows: Male=0 and Female=1. In addition, some features like “your_race” were encoded as a one-hot numeric array. The number of remaining features after applying previous measures are 79.
## Dimensionality reduction methods:
### Principal Component Analysis (PCA)
PCA is an unsupervised feature projection (feature projection) technique, it commonly used to reduce the dimensions in large data. PCA tries to reduce the dimensionality of the data by creating new uncorrelated variables while preserving the information as much as possible. PCA projects the data onto a set of orthogonal axes. This technique can be used to reduce the dimensions in images and textual contents. PCA use covariance to understand the multi-collinearity in the features.
Before applying PCA, mean normalization approach is important this is because it helps to make all the features have same range and give each feature a mean of zero.
PCA can improve model efficiency, reduce overfitting and improve visualization.
In PCA, choosing the right number of dimensions is important to ensure no loosing in the information. PCA has some disadvantages such as it has lower interpretability because the features become principal components which are not like the original. In addition, it preserves
global shapes rather than local shapes.

### Maximum Relevance — Minimum Redundancy
MRMR is a supervised feature selection technique. The algorithm is based on only selecting a low number of a great number of features to achieve the maximum level of accuracy. The process can be described as the way to find the “minimal-optimal” subset of features.
The method of “minimal-optimal” is based on finding a small number of features that can together achieve the best accuracy. On the other hand, the similar algorithms are based on determining the features that can individually perform the best accuracy. This algorithm can be summarized as it is the process of finding the best N features not the N best features.
MRMR works iteratively, it adds one feature for each iteration. The algorithm selects.

### Relief
Relief is a supervised feature selection technique. This algorithm works to estimate the quality of features depending on how well the feature can distinguish between instances that are near to each other. Relief algorithms don&#39;t assume conditional independence of the features to estimate the quality of the features. Relief algorithms described as efficient algorithms and can deal with problems with strong dependencies between features.
Relief technique have three types:
- Basic Relief algorithm which works with classification problems with two labels.
- ReliefF algorithm which works with multi-labels classification problems.
- RReliefF is extension of ReliefF after adopting it for continuous class problems.
The previous types of Relief technique work according to the same core idea of the algorithm mentioned earlier. In this work ReliefF algorithm was used as the problems are multiclass.
class.
