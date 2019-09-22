# Serverless Machine Learning with TensorFlow and BigQuery

This one day workshop provides a hands-on introduction to designing and building machine learning models on structured data on Google Cloud Platform. You will learn machine learning (ML) concepts and how to implement them using both BigQuery Machine Learning and TensorFlow/Keras. You will apply the lessons to a large out-of-memory dataset and develop hands-on skills in developing, evaluating, and productionizing ML models.

## Audience
- Data Engineers
- Data Scientists
- Data Analysts

## Prerequisties 
- Familiarity with [SQL](https://en.wikipedia.org/wiki/SQL)
- Basic familiarity with [Python](https://en.wikipedia.org/wiki/Python_(programming_language))

## Coursework: Slide Presentations
- [Student PDF version](https://storage.cloud.google.com/cloud-training/serverlessml/1.0/slides/Serverless%20ML%20with%20TensorFlow%20and%20BigQuery.pdf?folder=true&organizationId=true)
- [Instructor Google Slides version](https://docs.google.com/presentation/d/1ZLEK1aQOUXjly1tTDKrY_1YvRciGbW6WF8ipXCEk_Kw/edit)

## Coursework: Hands-On Labs

Note: If you are an instructor teaching this class via [Qwiklabs](https://www.qwiklabs.com) you can ignore the Pre-work as the student Qwiklabs will automatically create new GCP accounts and walk them through how to clone this repository. 

Each folder in this repository represents one lab and will contain:
  * labs/ <-- partially completed ipynbs with TODOs for you to complete
  * solution/ <-- full solution answers for reference
  
 What follows is a recommended list of labs for this workshop in order:

__Pre-work: [Create a Cloud AI Platform Notebook instance](http://console.cloud.google.com/mlengine/notebooks/create-instance)__
   * Choose TensorFlow 2.0.  This installs the beta version. However, we will have you upgrade to nightly version.
   * Choose 2 vCPUs and no GPUs.
   * On the instance, use the Git menu to clone https://github.com/GoogleCloudPlatform/training-data-analyst
   * Navigate to quests/serverlessml and open the install_nightly.ipynb notebook
   * Run the cell that installs the nightly version of TensorFlow.

__0. [Classify Images of Clouds with AutoML](https://www.qwiklabs.com/focuses/1779?parent=catalog)__ students will use the GCP UI to train multiple image classification models using [AutoML Vision](https://cloud.google.com/vision/automl/docs/) without having to code. 
   * Optional lab - 30 minutes
   * Upload a labeled dataset to Google Cloud Storage and connecting it to AutoML Vision with a CSV label file.
   * Train a model with AutoML Vision and evaluating its accuracy
   * Generate predictions on your trained model

__1. [Explore data](01_explore/) corresponding to taxi rides in New York City__ to build a Machine Learning model in support of a fare-estimation tool.
   * 20-30 minutes
   * Launch a hosted iPython notebook using AI Platform Notebooks
   * Access and explore a public BigQuery dataset on NYC Taxi Cab rides
   * Visualize your dataset using the Seaborn library
   * Inspect and clean-up the dataset for future ML model training
   * Create a benchmark to judge future ML model performance off of

__2. Use BigQuery ML [to build our first ML models](02_bqml/) for taxifare prediction.__
   * 20-30 minutes
   * Train a model on raw data using BigQuery ML in minutes
   * Evalute the forecasting model performance with RMSE
   * Create a second Linear Regression model with cleaned up data
   * Create a third model using a Deep Neural Network (DNN)
   * Evaluate model performance against our initial benchmark

__3. Learn [how to read large datasets](03_tfdata/) using TensorFlow.__
   * 20-30 minutes
   * Use tf.data to read CSV files
   * Load the training data into memory
   * Prune the data by removing columns
   * Use tf.data to map features and labels
   * Adjust the batch size of our dataset
   * Shuffle the dataset to optimize for deep learning

__4. Build a [DNN model](04_keras/) using Keras.__
   * 20-30 minutes
   * Use tf.data to read CSV files
   * Build a simple Keras DNN using its Functional API
   * Train the model using model.fit()
   * Predict with the model using model.predict()
   * Export the model and deploy it to Cloud AI Platform for serving

__5. Improve the basic models through [feature engineering in BQML](05_feateng/)__
   * 20-30 minutes
   * Apply transformations using SQL to prune the taxi cab dataset
   * Create and train a new Linear Regression model with BigQuery ML
   * Evaluate and predict with the linear model
   * Create a feature cross for day-hour combination using SQL
   * Examine ways to reduce model overfitting with regularization
   * Create and train a DNN model with BigQuery ML

__6. Carry out equivalent [feature engineering in Keras](06_feateng_keras/)__
   * 20-30 minutes
   * Use tf.data to read the CSV files
   * Apply feature engineering techniques to transform the input data
   * Create new feature columns for better predictive power
   * Build, train, and evaluate a new Keras DNN
   * Make example predictions
   * Export the model in preparation for serving later

__7. [Productionize the models](07_caip/)__
   * 20-30 minutes
   * Export training code from a Keras notebook into a trainer file
   * Create a Docker container based on a DLVM container
   * Deploy a training job to a cluster on Cloud AI Platform
   * Export [larger dataset](07_caip/solution/export_data.ipynb)
   * OPTIONAL: Train Keras model by [submitting notebook](07_caip/solution/run_notebook.sh)
   * Train [using container](07_caip/solution/train_caip.ipynb) on Cloud AI Platform Training


   
   
