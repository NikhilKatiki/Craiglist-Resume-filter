# Craiglist-Resume-filter
  1. Introduction
  2. Objective 
  3. Methodology
  4. Data Sources
  5. Data Dictionary
  6. Data Pre-processing
  7. Feature Engineering 
  8. Model Development
  9. LSTM Data preprocessing 
  10. LSTM Modelling
  11.Results 
# Introduction 
  1.Craiglist is classified advertisement website with section devoted to jobs, housing, for sale, resumes and many more  <br>
  2.Given that the improved computational power recently, there is a lot of scope to improve the interfaces using unstructured data techniques <br>
  3.Resumes are one of those which dont have any segregation into categories <br>
  4.Advanced unstructured modelling techniques are used to improve the satisfaction of both adversiter and job seeker 
# Objective 
  1.Even though Craiglist is one of the biggest adverstising website, there are still a lot of improvement that needs to be done. One such improvement is to add a filter  <br>
  2.The primary motivation is to use the unstructured data and categorize the resumes into pre-defined categories<br> 
# Methodology 
<img width="600" alt="proces" src="https://user-images.githubusercontent.com/89437135/147396424-69c55a95-0bec-4146-898c-c1d0556b6143.png"> <br>
# Data Sources 
  1. Since the resumes in the Craiglist are unlabeled, it is imperative that resumes with labels are being used to train the model and then, test on the resumes' data from Craiglist <br>
  2. The training data consists of 32 different categories ranging from HR to Chef 
# Data Dictionary
  1.The dataset consists only resume and its corresponding label <br>
  2.The dataset contains the following information. Displaying the first 5 rows of the data <br>
  <img width="600" alt="head" src="https://user-images.githubusercontent.com/89437135/147396433-b2eb2fce-fa54-4fc5-aa78-f5caed56b29a.png">
   <br>
  3.Only the resumes column is transformed as features to model the labels in the training data  <br>
# Data Preprocessing  
   The reviews data is in string format which needs to be converted to numeric format to model the categories. Following are the steps <br> 
     1.Tokenization <br>
      &nbsp;&nbsp;&nbsp;&nbsp;    i.The sentences are being tokenized into words<br>
     2.Lammetization<br>
       &nbsp;&nbsp;&nbsp;&nbsp;   i.Words are converted to their basic words by applying Lemmatization<br>
     3.Stop words<br>
       &nbsp;&nbsp;&nbsp;&nbsp;   i.Stop words which are frequently used are being removed as these dont contribute to the overall sentiment of the customer <br>
     4.Numeric formats <br>
        &nbsp;&nbsp;&nbsp;&nbsp;  i.Numeric formats have been removed as these are not useful in understanding the review <br>
# Feature Engineering 
### Count Vectorizer
  1. Count Vectorizer is a method to convert the words into vectors <br>
  2. This is especially useful if we dont need to consider the different weights for different words based on their frequency in the whole collection <br>
  3. With min_df, the number of dimensions are further reduced by removing words which are very low in frequency
  4. n_gram can help include the order to n words as a phrase. However, it will tend to higher dimensionality 
### Tfidf Vectorizer
  1. Tfidf is another method to convert the words into corresponding vector
  2. In this method, the words which are repeated in less frequency are given higher weights as compared to others 
Image 
  4. With min_df, the number of dimensions are further reduced by removing words which are very low in frequency
  5. n_gram can help include the order to n words as a phrase. However, it will tend to higher dimensionality 
# Model Development 
  1. Once the preprocessing of data is done, the features are passed into different models and reported the following accuracies across different preprocessing techniques <br>
<img width="600" alt="Text" src="https://user-images.githubusercontent.com/89437135/147396425-7af322c0-c801-4d49-9a98-96b03a0543e5.png"> <br>
# Long Short-term Memory 
# Data Pre-processing 
  1. Once the data is imported, the input for LSTM is to be either One hot encoded or Label encoded of collection of documents
  2. With the data being labaled, the data is further split into train and test to ensure the model is not going to overfit 
# LSTM-Modelling 
  1. The LSTM model consider the order through which the words of a document are sent
  2. As the maximum number of words in a document is more than 500, Padding is done as it can make a great deal in performance and accuracies 
  3. The following layers have been used for the LSTM model
&nbsp;&nbsp;&nbsp;&nbsp;        a.First layer is just inputting the Sequential layer 
&nbsp;&nbsp;&nbsp;&nbsp;        b.Adding embedding layer so that the whole document is converted to a reduced dimensional vector 
  &nbsp;&nbsp;&nbsp;&nbsp;      c.Adding LSTM layer with dropout ratio of 0.2 and recurrent dropout of 0.2 to avoid overfitting (Just like random forests)
     &nbsp;&nbsp;&nbsp;&nbsp;   d.Adding another dense layer 
      &nbsp;&nbsp;&nbsp;&nbsp;  e.Compiling the model with loss function as "Binary entropy" 
  4. The Epoch of 5 and the batch size of 100 is considered. Both Epoch and Batch size influence the accuracy to some extent 

&nbsp;&nbsp;&nbsp;&nbsp; i.Finding the number of positive words and negative words for every review <br>
          &nbsp;&nbsp;&nbsp;&nbsp;ii.Storing number of positive words in positive and number of negative words in negative <br>
# Results 
  1.From the analysis, it is clear that Airbnb implemented strategies which makes them unique in responding to the pandemic <br>
  2.Sentiment dropped after March 2020, but as the company takes remedial steps, sentiment increased over time <br>
  3.Top positive and negative comments did not change much in pre and post Covid  <br>
  4.Dirty and Crowded are highlighted negative comments post-Covid which can be suggestion to Airbnb hotels which are having low sentiment scores <br>
