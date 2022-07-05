# Covid19-Prediction-with-RNN
This notebook is a big assignment of Komputasi Matematika 3 when I were studying at mathematics department of Institut Teknologi Sumatera. I share this notebook to public in order to share my understanding and obtain if any feedback in order to improve my skills.

So, I assigned by my lecturer to predict a case with one of deep learning methods that we have learned before. I have chosen 3 datas about Covid-19 in Lampung Province, those are active case, recovered case, and death case. Besides that, i have chosen Recurrent Neural Network (RNN) Method because RNN is a fprm of artificial neural network architecture designed specifically for processing time series data. RNN can store memory (feedback loop) so that it can recognize data patterns well and then use then to make accurate prediction.

I have done in this notebook such as:
- Loading the data and save it into appropriate variables
- Converting the array of data into xTrain, yTrain, xTest and yTest
- Normalizing the data from 0 to 1 to achieve consistency in dynamic range for a set of data, signals or images to avoid mental distraction and reduce the data redundancy
- Building the simple RNN model to predict the test_data using Adam as an optimizer
- Building the RNN model architecture and get 99.9568357% for data train and 98.5259620% for data test
- Using EarlyStopping to minimize the overfitting and check the interactive dashboard from Tensorboard to see the epoch_loss and epoch_accuracy

### Task in the assignment
- [Step 1 - Loading Data](#step-1---loading-data)
- [Step 2 - Pre-processing](#step-2---pre-processing)
- [Step 3 - Preparing Model](#step-3---preparing-model)
- [Step 4 - Data Normalization](#step-4---data-normalization)
- [Step 5 - Training the model](#step-5---training-the-model)
- [Step 6 - Prediction](#step-6---predictions)

### Step 1 - Loading Data
In this section, you will unzip the data from google drive and load the data into your notebook
```
from google_drive_downloader import GoogleDriveDownloader as gdd
```

### Step 2 - Pre-processing
In this section, you have to set the pixel into 256 256, covert_to_tensor, reshape and normalize it.
- convert to tensor `tf.convert_to_tensort(data_test, np.float32)`
- reshape `tf.reshape(data_test_tf, [910, 256, 256, 3])`
- normalize `np.divide(data_test_tf, 255.0)`

To load the training data, I use the Image Data Generator 
```
from keras.preprocessing.image import ImageDataGenerator
```

### Step 3 - Preparing Model
In this section, you have to build your own model version to predict the data. I have build 3 hidden layers such as
- First hidden layer, I use 512 perceptrons and relu activation
- Second hidden layer, I use 256 perceptrons and relu activation
- Third hidden layer, I use 128 perceptrons and relu activation

### Step 4 - Data Normalization
In this section, you have to create your own optimizer.
Here I use `adam` for simple CNN model and `SGD` for the ResNet50 Model

### Step 5 - Training the model
In this section, you have to set the tensorboard and earlystopping in your model fit. Tensorboard is a dashboard of our result of training and earlystopping to stop the running model to overcome over fitting.

### Step 6 - Prediction
In this section, you will predict the test_data and copy the result into DPHI Deep Learning Bootcamp to check the accuracy

### Resources
- **Python Version:** 3.7.6
- **Tensorflow Version:** 2.3.0
- **Dataset:** (https://data.covid19.go.id)

### Achievement
The result of my submission in Komputasi Matematika published as study journal in Indonesian Journal of Applied Mathematics. 

I thank to Dr. Rifky Fauzi, S.Si., M.Si. and all teams in this class. I do appreciate for your effort to share deep learning knowledge. I recommend for all learners whether you are beginner or intermediate level, you may choose this class as one of your resources to enhance your skill and make your hands dirty. Thank you so much.
