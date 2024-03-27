LSTM network to predict future trends of stock prices in time steps of 15 minutes based on the price history, alongside technical analysis indicators. On average, 55.9% accuracy was achieved in predicting whether the price of a particular stock may increase or not shortly in the future.

Selvin, Menon, Soman et al. in [7] experimented on three different deep learning models, namely CNN, RNN, and LSTM with a sliding window approach.

- Out of the three, CNN gave more accurate results than the other two models which is due to the reason that CNN uses only the information on the current window for predicting stock price. This allows CNN to understand the dynamic changes and patterns occurring in the current window.
- Conversely, RNN and LSTM use information from previous lags for predicting future instances.

Bansal, Hasija et al. in [9] proposed an Intelligent decentralized Stock market model using the convergence of machine learning alongside DAG based cryptocurrency. The ML model which is based on LSTM achieved an accuracy of 99.71% in prediction. The feature vector of stock for the company contained 4 parameter values i.e., ‘open’, ‘close’, ‘low’, and ‘high’ with batch size as 50 for 100 epochs.

We decided to go on with CNN-LSTM Neural Network (Convolutional Neural Network and Long Short-Term Memory Neural Network) approach because CNN helps in tracking the features of the dataset and LSTM helps in tracking the patterns, allowing to train on them.

Since this is a regression type of problem where we had to train with time-series data, we used Mean Square Error as the standard metric rather than accuracy.

[https://github.com/Circle-1/Stock-X](notion://github.com/Circle-1/Stock-X)

![Untitled]('../Images/Architecture for Deep Learning Model.png')

- Stored fill data in CSV format for testing phase
  - Stock data of a company ranging since 10 years
- Exploratory Data Analysis on the Data

- In the preprocessing phase, we first cleansed the data by removing NULL values from the dataset and taking the mean of data and replacing it if necessary using the Pandas library. Then we took the four columns of any stock market dataset, namely ”Open”, ”Close”, ”High”, ”Low”. These are the columns which mainly involve in training the dataset especially the ”Close” column (shown in Fig. 2). The graphs are plotted using the matplotlib and seaborn library in Python.

![Untitled]('Images\Architecture of CNN-LSTM model.png')

- For the CNN model to parse the dataset, we made a function where the 1-D arrays are made to convert to [100,1] tensors (precisely, a vector). Tensors are a type of data structures that describe a multilinear relationship between sets of objects in a vector space. So, for converting 1-D array to tensor, every 100 rows are taken and from that the mean of the values are calculated and made to store in a separate column. This process is done for the entire dataset. In our case, we did this on the ”Close” column as it's the main column where we would decide the prediction of the stock data. After this step, we would obtain tensors for the CNN side of the model to train. Then, we split 80% for training and 20% for testing. Finally, we reshaped the data and sent it to the training phase.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c8da9359-ea64-4587-80e4-0f1bf2fc14b5/032e934f-561d-40b2-9807-e4534c83d5af/Untitled.png)

3 layers of neuron size 64,128,64 with kernel size=3 along with MaxPooling layers in between. Finally, we added a Flatten layer at the end of the CNN section to convert the tensors back to a 1-D array. All CNN layers are added with TimeDistributed function in order to train every temporal slice of input, as we’re approaching a Time-Series problem in this case. Then, the processed data is sent to the LSTM layers. For the LSTM section, we made 2 Bi-LSTM layers to detect the features and train them forward & backward. For each layer, the neuron size is 100. Additionally, dropout layers are added in between with a value of 0.5 to drop some features for stability. Lastly, we added a dense layer with a linear activation function and at the final layer, we used the "adam" optimizer ("sgd" also worked in this case but we found "adam" optimizer to be more accurate after analysis), Mean Squared Error (mse) as the loss function and "mse" and "mae" as metrics. The architecture for the model is shown in Fig. 4.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c8da9359-ea64-4587-80e4-0f1bf2fc14b5/94483918-6b48-4acf-95cb-aff318055837/Untitled.png)

[2305.14378.pdf](https://prod-files-secure.s3.us-west-2.amazonaws.com/c8da9359-ea64-4587-80e4-0f1bf2fc14b5/4b4a8453-0f16-469e-bd7a-62f00650bea0/2305.14378.pdf)
