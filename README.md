# Human-activity-recognition-using-smartphones-sensors


Introduction


These days we can't imagine our lives without Smartphones.Smartphone sensors use various
sensors to enhance user experience. Two of the sensors are Accelerometer and Gyrometer.
Accelerometer measures acceleration while Gyroscope measures angular velocity. So we
decided to make this project as it helps us to detect activities of a human wearing a smartphone
on their waist. So by using the features built using readings provided by accelerometer and
gyroscope we will try to predict one of the six activities by human beings.
Data Source(Here is how we took the data and used it for our project)
To make something sensible,we need some data to process. To make this project work, we
have taken datas from UCI’s official sources. The dataset basically provides the information
about various activity parameters like: Walking,Walking upstairs,Walking Downstairs,Sitting
Down,Standing up,Laying down.Also linear and angular accelerations have been calculated in
the directions of all the three axes(X,Y&Z). After getting these well-arranged datasets, we
performed our HAR(Human Activity Recognition) analysis by implementing the corresponding
functions embedded in our code. Also it has to be noted that the obtained dataset has been
randomly partitioned into two sets,whereas 70% of the volunteers have been selected for
generating the training data and 30% for preparing the test data


Link for data sources:
https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones



MODEL FORMULATION

We make an LSTM model to predict the Human Activities.LSTM works well on time-series data,
so we have decided that we apply LSTM of Recurrent Neural Networks on 128 sized raw
readings that we obtained from accelerometer and Gyroscope signals.
Metrics To Be Used To Check Performance’s Precision:
We use Accuracy as one of the metric.We use Confusion-Matrix to check that in which two
activities our model is confused and predicting incorrect activity. For example ,between
Standing-Up and Sitting-Down. Between Walking -Upstairs and Walking-Downstairs.


Detailed Action Plan:


● So first we started with importing all the important libraries required for the project. These
libraries were namely:
numpy,pandas,seaborn,matplotlib.pyplot,sklearn.manifold,warnings,datetime,GridSearch
CV,confusion_matrix,accuracy_score,Logistic_Regression,LInear
SVC,SVC,DecisionTreeClassifier,RandomForestClassifier,GradientBoostingClassifier,Se
quential,LSTM,Dense,Dropout,Trials,STATUS_OK,tpe,optim,choice,uniform.
● Then we extracted features from Features.txt file
● Then we read the training and test data as training data is used to train the model to get
accurate predictions and test data is used to test the model.
● Then we looked for removing the duplicate and null values in data(if present).Also we
checked if there is any imbalance in data.
● We visualized the balance in data by plotting the graphs like Count v/s Subject ID and
Count v/s Different Human Activities.
● Then we explored feature information from our previous knowledge. We categorised the
motion into two categories - Static and Dynamic.
Static includes Sitting,Standing,Lying and Dynamic includes Walking Upstairs,Walking
Downstairs and normal walking.
● Then we plotted two graphs which observed that the magnitude of the mean of the
body's acceleration in the time domain measured by the accelerometer is able to
separate static activity from dynamic activity.
● So we applied the TSNE plot to data for better visualization and to get a better
perplexity. So using this, we obtained different sets of data points corresponding to
different human activities. From T SNE plots, we can observe that except Standing and
Sitting all other activities are separated fairly well.
● For better understanding, we applied following models and compared their accuracies
accordingly:-
❏ We first applied Logistic Regression and made three matrices namely Confusion
Matrix, Precision matrix and Recall Matrix.
❏ Then we applied Linear SVM and also made three matrices for this model also:
namely Confusion Matrix, Precision matrix and Recall Matrix.
❏ Also we applied Decision Tree and made three matrices Confusion,Precision and
Recall Matrix.
❏ Then we applied the deep learning LSTM Model where we used raw readings
obtained from accelerometer and gyroscope signals and tuned Hyper-parameters
using Hyperas and used the best Hyper Parameters.
● Then we compared the accuracies of all the models used and found that the LSTM
Model gave the good predictions even when we didn't have domain expert engineered
features.
Also we noticed that when we used the best Hyper parameters, the accuracy of the
model was improve
