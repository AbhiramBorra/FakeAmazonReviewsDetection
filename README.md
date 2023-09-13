# FakeYelpReviewsDetection
We are changing the project dataset from Amazon reviews to Yelp reviews. The goal of our project is still the same to detect fake reviews. The YelpReviews.ipynb file has our latest work.                                                                                     
                                                                                                                                      
Dataset:
https://www.kaggle.com/datasets/abidmeeraj/yelp-labelled-dataset                                                                                                                                                                          
The dataset provided by Abidmeeraj on Kaggle is a list of over 35,000 Yelp consumer reviews about hotels located in North America. 


Preprocessing : 
Text to numerical conversion - For the preprocessing stage we are using TF-IDF to process the text into numbers.
Finally, we ran the TF-IDF metric, which scans through text and calculates the frequency of appearance of words within the text during the TF stage and measures global importance during the IDF stage. 

Data Cleaning - During the preprocessing stage, we dropped any data that didn't add any value, and cleared the rest of the data by removing any null entries.

Feature Engineering - We expanded characteristics through creating novel features from those that already exist, primarily through modifying data using polynomial, logarithmic, or feature multiplication operations.


Model Builing:
For our initial model we will run neural network based algorithm on 3 dimensions with the major goal to identify the real and fake reviews cluster within the dataset.


Evaluation:
We evaluate the performance of our model using accuracy and other metrics by employing the subsequent stages:

Training versus Test Error Comparison - In order to determine the model's performance and accuracy capabilities, we analyze the training and test errors.

Model Fitting Analysis - In order to determine insights into its bias and variance, we examine the models's positioning relative to the underfitting/overfitting graph. 


Features : 
Our feature for "rating" is straightforward, therefore we won't do any preprocessing. 
However, for our "recommended" feature, for simplification of representation and analysis we have converted it into binary, 1 for 'yes' and 0 for 'No'.

First model evaluate:
Epoch 48/50
71/71 [==============================] - 2s 31ms/step - loss: 0.2151 - accuracy: 0.9278
Epoch 49/50
71/71 [==============================] - 3s 41ms/step - loss: 0.1917 - accuracy: 0.9363
Epoch 50/50
71/71 [==============================] - 2s 28ms/step - loss: 0.2292 - accuracy: 0.9189

Training MSE: 0.07677777777777778                                                                                                                                                                                                    
Testing MSE: 0.1                                                                                                                                                                                             
From the MSE data above, we think the first model is a bit overfit because the testing MSE is 25% higher than the training MSE, the training error is lower.


Conclusion : 
Our research seeks to offer an approach for detecting false Yelp reviews. We anticipate that our attempts will contribute to strengthen customer trust in hotel management. 


**WRITE UP**      

Introduction:              

Yelp is a popular online platform and mobile app primarily used for discovering businesses that can include restaurants, cafes, bars, hotels, spas, salons, boutiques, and more. Yelp provides recommendations based on a user's location and preferences, users can read, rate, and write reviews about the quality of service, products, ambiance, and overall customer experience. These ratings and reviews are important for customers making their decisions. Yelp has more than 178 million unique visitors monthly across mobile and desktop in September 2018. USA visitors account for 90% of all visitors. It's important to note that while Yelp strives to maintain the integrity of its review system, not all reviews are necessarily authentic. The fake reviews can mislead users by providing inaccurate information about businesses, they may end up with a less-than-optimal experience and wasted time and money. Also, Yelp will lose the trust of its users. We decided to do the project by making a machine-learning model to find fake Yelp reviews. The model aims to help users to get real information and Yelp platforms maintain trust, fairness, and transparency in their review systems. The following part will go deep in about our model, describing every aspect of our model.

**Methods:** 

Libraries: 

      Pandas: Used to load the data set, and manipulate it
      NumPy: Numerical operations
      Matplotlib: Data visualization during preprocessing
      Seaborn: Data visualization during preprocessing
      Ntlk: Preprocessing textual data
      BeautifulSoup: Process HTML-based data
      TF-IDF Vectorizor: Conver textual data into numerical data
      Keras: Neural Network building
      Sklearn: Hyperparameter tuning and model evaluation

**Data Preparation and Exploration** 
     
**Data Loading**

        We began by loading our dataset titled "Labelled Yelp Dataset.csv" from Google Drive into a pandas DataFrame.
      
**Data Exploration**

        We employed Matplotlib and Seaborn libraries to visualize the data.
      
**Data Preprocessing**

**Data cleaning**

          Based on the relations discovered during Data Exploration, we used the pandas library to manipulate the data set and drop columns. 
          We employed the scikit-learn library's TfidfVectorizer class to convert text data(reviews) into TF-IDF features for machine learning. This process transformed the textual information into a matrix of TF-IDF characteristics
          suitable for analysis.
      
**Machine Learning Models**
      	
**Neural Network Model (Initial Model)**

        We constructed a neural network model using Keras. The model’s input layer had 20 neurons and the ‘relu’ activation function. The model included 2 dense hidden layers with neurons of 75 and 15 and the ‘relu’ activation
        function. The final layer used a single node and the ‘sigmoid’ activation function for binary classification, and we utilized stochastic gradient descent (SGD) optimization.
      
**Train-Test Split**

        We divided the dataset into training and testing sets using the train_test_split function. 90% of the data was allocated for training the machine learning model, and the remaining 10% was used to evaluate its performance.
      
 **Model Training and Evaluation**
 
        The neural network model was trained for 50 epochs on the training data. We evaluated the model's performance by calculating the Mean Squared Error (MSE) for both the training and testing datasets.
      
**Hyperparameter Tuning**

        We conducted hyperparameter tuning to optimize the neural network model's performance. Using GridSearchCV, we explored different combinations of hyperparameters such as the number of hidden layers, number of nodes per layer,
        activation functions, and optimizers.



Contributions :  
Group members -                                                                                                                                                    
Abhi Borra,	aborra@ucdavis.edu                                                                                                            
Rohit Singh,	rkssingh@ucdavis.edu                                                                                                              
Jaryd Bones,	jbones@ucdavis.edu                                                                                                                 
Jose Navarro,	janavarro@ucdavis.edu                                                                                                             
Zhixuan Qiu,	zxqiu@ucdavis.edu



