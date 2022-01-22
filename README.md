# Topic_Modelling

#### Dataset: 20 Newsgroups

#### Pre-processing:
1. Removed all non-ASCII characters, extra spaces, and newline characters using
regular expressions.
2. Removed punctuation and performed lowercasing using lambda function. 
3. Removed stopwords and tokenized sentence into words using simple_preprocess
function.
4. Implemented the bigrams and trigrams models using Gensim’s phrases model.
5. Then, performed lemmatization keeping only Noun, Adj, Verb, and Adverb.


#### Model Codes: Gensim LDA

#### Experimental Setting: Classification

#### Hyperparameters: alpha = 0.10 and beta = 0.09 

#### My Experiments:
1. Performed the tf-idf vectorizer using TfidfVectorizer function to convert raw 
documents into matrix.
2. Split the dataset into Train, Tune and Test using train_test_split package from 
sklearn.model_selection into 70/15/15 percentage by setting train_size as 0.7 between 
train and test. The test_size as 0.5 between test and tune.
3. Built a Latent Dirichlet Allocation (LDA) model by calling fit_transform function to 
build it. We get the topic model (get_documet_topics) which we use as an input into 
Support Vector Machine (SVM) classifier as a feature vector after scaling the vectors
and used as ‘X’ with ‘y’ being my targets where I am using document topic matrix (7919, 
20) with all my parameters (alpha, beta and topics) and then tuning the machine 
learning model using tuning set where the GridsearchCV is used to tune the parameters
and to find the ideal number of parameters. Here, using perplexity as a metric to tune 
the number of topics.
4. Evaluating the classifier performance using the tune set by GridsearchCV which will 
tune to find the best parameters of the model i.e. the number of topics and repeating the 
process by varying the number of topics in steps of 10 as shown in the below table.

| Train        | Perplexity on Tuning Set |
| ------------- |:-------------:| 
| 10 | 1564.30 |
| 20 | 1433.63 |
| 30 | 1389.65 |
| 40 | 1598.57 |
| 50 | 1682.73 |

 
 
 


