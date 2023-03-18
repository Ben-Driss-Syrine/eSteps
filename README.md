# eSteps
Stay Estimate : using IMU sensor data to predicate the time needed for a patient to stay in the hospital
DataSet : In-hospital physical activity measured with a new Bosch accelerometer sensor system

Extracted from the PhysioNet repository, that is operated by the MIT Laboratory for Computational Physiology with assistance from the National Institute of Biomedical Imaging and Bioengineering (NIBIB) of the National Institutes of Health.

What Does the Dataset provides ? 

—> The dataset contains physical activity of 58 patients of different age groups over the period of 30 days measured by accelerometry ( wrist-worn Bosch sensor platform ) to develop algorithms to predict duration of hospitalization.
It observe th e mobility and physical activity (PA) as surrogate parameter of the surgical patients health to predict patient outcomes ( traditional risk factors such as admission diagnosis, age, comorbidities, polypharmacy … are limited data to describe the overal health of the hospitilized paitents ). 

How data is collected ?

—> Through an observation study that took place in 3 internal medical that has the capacity of 100 beds, 30- bed oncology ward in 1100-bed referral center at the Robert-Bosch hospital in Stuttgart, Germany for 20 days, with the support of the Medical Faculty of the Eberhard Karls University and at the University Hospital Tübingen, Germany. 


Potential applications of this dataset 
Analyzing hospital activity patterns to identify trends and patterns in patient demographics, diagnoses, and procedures. 
Developing predictive models to forecast hospital activity and resource needs. 
Evaluating the impact of changes in hospital management and resource allocation on patient outcomes and resource utilization. 
Comparing hospital activity patterns across different regions, countries, or time periods.

How does the model works ? 

First, we load and preprocess our dataset, which consists of two separate CSV files containing information about patients and their hospitalization times.
We merge these two datasets based on a common patient ID column and drop any rows with missing values.
We split the data into training and testing sets, with 80% of the data used for training and 20% used for testing.
We define our neural network model using the Keras Sequential API. Our model consists of three layers: an input layer with 11 neurons (representing our 11 features), a hidden layer with 128 neurons and a ReLU activation function, and another hidden layer with 64 neurons and a ReLU activation function. Finally, we have an output layer with a single neuron (representing our predicted hospitalization time).
We compile our model using the Adam optimizer and mean squared error (MSE) loss function, with mean absolute error (MAE) used as a metric for evaluation.
We train the model on our training data for 100 epochs, using 20% of the training data as a validation set to monitor for overfitting.
After training, we evaluate the model on our testing data, calculating the loss and MAE.
Finally, we use the model to make a prediction on new data, consisting of a single patient's information, and print the predicted hospitalization time.
