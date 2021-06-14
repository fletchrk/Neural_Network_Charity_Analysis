# Neural_Network_Charity_Analysis

## Overview of the Analysis
Using the knowledge of machine learning and neural networks, I will use the features in the Alphabet Soup Charity dataset that was provided to help create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup. The dataset that we received contains more than 34,000 organizations that has received funding from Alphabet Soup over the years. The dataset contains 11 columns that capture metadata about each organization. The following deliverables were completed for this project:
1.	Deliverable 1: Preprocessing Data for a Neural Network Model
2.	Deliverable 2: Compile, Train, and Evaluate the Model
3.	Deliverable 3: Optimize the Model
4.	Deliverable 4: Complete a written report on the Neural Network Model

## Results
### Deliverable 1: Preprocessing Data for a Neural Network Model
The following preprocessing steps were performed:
- EIN and NAME columns were dropped because they were neither targets or features of the dataset and since they had little to no impact on the outcome of the data.
- The columns with more than 10 unique values were grouped together 
![Unique_Values]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Unique_values.png)
- IS-SUCCESSFUL column was the variable that was considered as the target for my model.
- Categorial variables were encoded using one-hot encoding.
- Merged one-hot encoded features into a dataframe:
![Merged_dataframe]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Merged_dataframe.png)
- Preprocessed data was split into features and target arrays
- Preprocessed data was split into training and testing datasets
- Numerical values were standardized using StandardScaler()
### Deliverable 2: Compile, Train, and Evaluate the Model
The following steps were performed using Tensorflow Keras that contains working code:
•	An output of number of layers, the number of neurons per layer, and activation function was defined. 

![Model_Sequential]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Model_Sequential.png)

•	An output of the model’s loss and accuracy
![OutPut]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/OutPut.png)

•	Wrapping up Deliverable 2 by saving the results to an HDF5 file:

![Export_model_HDF5]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Export_model_HDF5.png)

### Deliverable 3: Optimize the Model
The following steps were taken to make three attempts to increase model performance:
- The original model was not able to reach 75%, which was the target. The accuracy for the model was 65%.

![OutPut]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/OutPut.png)

The following steps was taken to try to increase model performance:
- Attempt 1: Removed the “USE_CASE” column, while the rest of the model components stayed the same, however model accuracy went down to 46%.

![Attempt1_output](https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Attempt1_output.png)

- Attempt 2: Adding additional neurons to hidden layers and additional hidden layers are added. The accuracy went up to 54%.

![Attempt2_output]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Attempt2_output.png)

- Attempt 3: Changing activation function of output layer to “tanh” from “sigmoid”. The accuracy of the model was 54%.

![Attempt3_output]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Attempt3_output.png)

- The results are saved to an HDF5 file 

![Del_3_HDF5]( https://github.com/fletchrk/Neural_Network_Charity_Analysis/blob/main/Resources/Del_3_HDF5.png)

## Summary
The accuracy score for the model after optimization was 54%. The initial neural network had a accuracy score of 65%. The model overfitted which could be an explanation of why the loss in accuracy is explained. A recommendation is to remove more features or add more data to the dataset to increase accuracy. Another recommendation is to possibly use a Random Forest classifier because they are a robust and accurate model due to the sufficient number of estimators and tree depth. In addition, the performance of the random forest models are faster than neural networks which could have helped avoid the overfitting of the data.
