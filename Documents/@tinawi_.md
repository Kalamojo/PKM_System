---
alias: Machine Learning for Time Series Anomaly Detection
authors: Ihssan Tinawi
year:
type: paper
tags:
  - academic
  - annotation
page(s): 55
---
> [!abstract] 
> In this thesis, I explored machine learning and other statistical techniques for anomaly detection on time series data obtained from Internet-of-Things sensors. The data, obtained from satellite telemetry signals, were used to train models to forecast a signal based on its historic patterns. When the prediction passed a dynamic error threshold, then that point was flagged as anomalous. I used multiple models such as Long Short-Term Memory (LSTM), autoregression, Multi-Layer Perceptron, and Encoder-Decoder LSTM.


* Mdnotes File Name: [[tinawi_]]

# Extracted Annotations (2022-02-28)

> "A model is said to learn when it is able to produce estimates of a data point based on whatever structure it has inferred from previous data." ([Tinawi :67](zotero://open-pdf/library/items/KBLMD2YA?page=13))

> "Time series anomaly detection is a field that has historically utilized several statistical methods in order to try to guess anomalies in sequential data." ([Tinawi :67](zotero://open-pdf/library/items/KBLMD2YA?page=13))

> "time series is used to refer to data that has values associated with timesteps. Examples of time series data are stock prices or temperature readings from a thermometer." ([Tinawi :67](zotero://open-pdf/library/items/KBLMD2YA?page=13))

> "Often, time series data exhibits patterns like periodicity, cyclic growth, exponential decay, to name a few characteristics." ([Tinawi :68](zotero://open-pdf/library/items/KBLMD2YA?page=14))

> "There are several ways to carry out anomaly detection, using statistical methods such as clustering, wavelet transforms, autoregressive models, and other machine learning and digital signal processing techniques." ([Tinawi :68](zotero://open-pdf/library/items/KBLMD2YA?page=14))

> "Within machine learning, the time series anomaly detection problem can be classified into two categories: supervised and unsupervised. The first category occurs when historic anomalies are known and models are fitted to identify similar anomalies, and this is known as "supervised learning" because data points are labeled with their true nature." ([Tinawi :68](zotero://open-pdf/library/items/KBLMD2YA?page=14))

> "In other settings, the labels are not known and the model tries to predict whether a point is anomalous based on how close it is to previously seen data, and these instances are referred to as "unsupervised learning" tasks." ([Tinawi :68](zotero://open-pdf/library/items/KBLMD2YA?page=14))

> "A good model is tuned so that is not strict leading to too few anomalies being noticed and not over-sensitive such that a lot of normal points are flagged as anomalies." ([Tinawi :68](zotero://open-pdf/library/items/KBLMD2YA?page=14))

*Anomaly detection with Unsupervised learning is more common because machines don't intuitively know whether anomalies have occurred or not. Supervised learning approaches would require experts to label data. ([note on p.68](zotero://open-pdf/library/items/KBLMD2YA?page=14))*

 

> "Machine intelligence programs can be built in order to monitor information from critical systems and flag anomalies as they occur. Human experts can then view these warnings, and decide to deal with them on a case-by-case basis." ([Tinawi :69](zotero://open-pdf/library/items/KBLMD2YA?page=15))

> "Statistical methods can be used to determine context anomalies, which are changes that shift across seasonal trends." ([Tinawi :69](zotero://open-pdf/library/items/KBLMD2YA?page=15))

> "For instance, the average temperature is much lower in the winter than in the summer. So, if you encounter a temperature of 80 degrees Fahrenheit in the winter, it's an anomaly, whereas in the summer it would be a normal temperature." ([Tinawi :69](zotero://open-pdf/library/items/KBLMD2YA?page=15))

> "The best system has a small number of false positives and negatives." ([Tinawi :69](zotero://open-pdf/library/items/KBLMD2YA?page=15))

*Companies struggle to hire enough people to analyze data. The data they receive increases at an exponential rate while they can only afford to hire personnel at a mere linear rate. ([note on p.70](zotero://open-pdf/library/items/KBLMD2YA?page=16))*

 

> "We study the performance of multilayer perceptrons (MLP), Long Short-Term Memory (LSTM), LSTM Encoder-Decoder, and linear autoregression models to contrast which architectures perform the best for time series data forecasting." ([Tinawi :70](zotero://open-pdf/library/items/KBLMD2YA?page=16))

> "We found that increasing the length of the input sequence to the models yielded improved results." ([Tinawi :71](zotero://open-pdf/library/items/KBLMD2YA?page=17))

> "in a paper titled "Detecting Spacecraft Anomalies Using LSTMs and Nonparametric Dynamic Thresholding" [2], researchers from NASA apply a stacked LSTM model to telemetry data obtained from two of their satellites. The signal is passed through the model and it generates a forecast for the next timestamp. The predicted value is then compared to the realized value to compute an error. After applying smoothing techniques, the error is passed through a dynamic threshold that determines whether the observed value is an anomaly, based on the previous errors of the model." ([Tinawi :73](zotero://open-pdf/library/items/KBLMD2YA?page=19))

> "a novel technique called dynamic error thresholding. This method is different from previously used error cutoffs such as fixed error thresholds like x-sigma or distance based approaches such as clustering [4]. Nonstationary data is characterized by having a mean and variance that shifts with time." ([Tinawi :73](zotero://open-pdf/library/items/KBLMD2YA?page=19))

*Data values can grow, decrease, or generally change over time, exhibiting normal cyclic behavior. This makes most data non-stationary. If a distribution of the data was mapped and analyzed for anomalies, future values that are considered normal could be labeled as anomalies instead. To combat this possibility, the distribution representing the data needs to be changed over time according to the data's cyclic behaviors. For example, if the mean of the data slowly increases over time, the machine learning model checking for anomalies should adjust it's model distribution to match it. ([note on p.73](zotero://open-pdf/library/items/KBLMD2YA?page=19))*

 

> "on the International Space System, there is the Inductive Monitoring System (IMS), built by NASA to deal with anomalous behavior. The IMS uses a clusteringbased approach to determine the health of signals, as compared to nominal performance." ([Tinawi :74](zotero://open-pdf/library/items/KBLMD2YA?page=20))

> "Clustering techniques are distance-based, meaning that clusters are formed based on how far a data point is from others. Clustering methods do not require the data to be labeled, making it a good fit for our unsupervised task." ([Tinawi :74](zotero://open-pdf/library/items/KBLMD2YA?page=20))

> "Clustering can be solved with an approximation algorithm that has two steps: assignment and update." ([Tinawi :75](zotero://open-pdf/library/items/KBLMD2YA?page=21))

> "To conduct time series anomaly detection, the signal is passed in as individual data points, and the number of clusters can be set to 2 (one anomalous and one normal). Alternatively, we can experiment with 3 clusters (anomalous, normal, and outliers) to see how that improves the performance of the system." ([Tinawi :75](zotero://open-pdf/library/items/KBLMD2YA?page=21))

> "The problem with a clustering approach is that typically algorithms assume that the data is equally distributed across the clusters, which is not a valid assumption to make in the case of anomalies. For instance, a signal might have little to no anomalies in a given sample." ([Tinawi :75](zotero://open-pdf/library/items/KBLMD2YA?page=21))

> "Another limitation of clustering-based approaches is that the data might go through multiple phases. For instance, if we are looking at a thermometer's signal, and the thermometer is on Earth, then data in the summer will be higher on average than data in the winter. This will lead the clustering algorithm to assign the temperature readings into one cluster in the summer and another in the winter. Thus, contextual anomalies are lost, where an unexpectedly high temperature in the winter is just assigned to the summer cluster." ([Tinawi :75](zotero://open-pdf/library/items/KBLMD2YA?page=21))

*K-means clustering serves to separate *n* observations into *k* clusters, where each new data point is assigned to the cluster with the closest mean. ([note on p.75](zotero://open-pdf/library/items/KBLMD2YA?page=21))*

 

> "With the advent of faster computing chips and the abundance of data, a new Golden Era of machine learning has started, making researchers interested in applying deep learning techniques to any decades-old statistical field." ([Tinawi :76](zotero://open-pdf/library/items/KBLMD2YA?page=22))

> "In deep learning, architectures such as Recurrent Neural Networks (RNNs) and Long Short-Term Memory (LSTM) networks were found to perform better compared to feed forward neural network architectures. Due to their ability to encode temporal properties, RNNs and LSTMs perform well in time series forecasting, speech recognition, and natural language processing tasks, since they both rely on modeling sequences." ([Tinawi :76](zotero://open-pdf/library/items/KBLMD2YA?page=22))

> "LSTMs have the ability to learn the relationship between past data and current values." ([Tinawi :76](zotero://open-pdf/library/items/KBLMD2YA?page=22))

> "In time series anomaly detection, you are implicitly assuming that all training data does not have any anomalies. Therefore, the train/test split will have a large effect on the outcome of the experiment." ([Tinawi :79](zotero://open-pdf/library/items/KBLMD2YA?page=25))

> "The first method is called 푡푖푚푒 푠푒푟푖푒푠 푎푔푔푟푒푔푎푡푖표푛, and it combines data across time intervals, thereby changing the frequency of the data." ([Tinawi :84](zotero://open-pdf/library/items/KBLMD2YA?page=30))

> "The other is called 푟표푙푙푖푛푔 푤푖푛푑표푤 푠푒푞푢푒푛푐푒푠, and it creates overlapping sequences that are used to predict in the time series forecasting models." ([Tinawi :84](zotero://open-pdf/library/items/KBLMD2YA?page=30))

> "The time series aggregation method takes in time series data and clusters data spanning a certain interval, using mathematical aggregation methods such as mean and median, to name a few. The method is useful because it reduces the size of data sets, by changing the frequency at which the data is sampled." ([Tinawi :84](zotero://open-pdf/library/items/KBLMD2YA?page=30))

*Time series aggregation takes the average of the next couple of values and marks it down at the timestamp of the first value of the set. For example, here is a time series of temperatures: [1: 32, 2: 47, 3: -8, 4: 87, 5: 74, 6: 56].Time series aggregation grouping 3 values would make this new time series: [1: 23.67, 4: 77.33]. ([note on p.85](zotero://open-pdf/library/items/KBLMD2YA?page=31))*

 

*Time series aggregation can be limiting when looking for individual anomalous events, but they do help to focus on long term trends. ([note on p.85](zotero://open-pdf/library/items/KBLMD2YA?page=31))*

 

> "Rolling window sequences is a method that is commonly used to prepare time series data for building models for forecasting." ([Tinawi :86](zotero://open-pdf/library/items/KBLMD2YA?page=32))

> "In many machine learning setups, the models perform better when they use normalization techniques" ([Tinawi :86](zotero://open-pdf/library/items/KBLMD2YA?page=32))

> "Multilayer perceptron (MLP) is a type of feedforward artificial neural network architecture that comprises of three layers at the minimum: an input layer, hidden layer(s), and an output layer." ([Tinawi :87](zotero://open-pdf/library/items/KBLMD2YA?page=33))

> "The hidden layer units have a non-linear activation function, and the output layer in the context of a time series forecasting problem is a single unit that predicts the value at the next time step." ([Tinawi :87](zotero://open-pdf/library/items/KBLMD2YA?page=33))

> "It acts as a linear perceptron, with the only difference being the nonlinearity introduced by adding activation functions such as tanh, rectified linear (RELU), and others." ([Tinawi :87](zotero://open-pdf/library/items/KBLMD2YA?page=33))

> "The hyperbolic tangent, 푡푎푛ℎ, function maps all the real numbers to an output range of [-1, 1]." ([Tinawi :87](zotero://open-pdf/library/items/KBLMD2YA?page=33))

> "This technique, called feature scaling, is important to be done in machine learning algorithms, because objective functions don't work properly without normalization." ([Tinawi :87](zotero://open-pdf/library/items/KBLMD2YA?page=33))

> "As classifiers compute the Euclidean distance between two data points, the distance is often skewed by features that have broad range of values. This normalization also helps with the faster convergence of training in stochastic gradient descent." ([Tinawi :87](zotero://open-pdf/library/items/KBLMD2YA?page=33))

*Multilayer perceptron Neural Networks are considered to be the "vanilla" neural networks because they don't include any recurrent, convolutional, or gated layers that are more common in newer networks. ([note on p.87](zotero://open-pdf/library/items/KBLMD2YA?page=33))*

 

> "The RELU is another type of activation function that we utilize in the training of our deep neural networks, where the function definition is 푓 (푥) = 푚푎푥(0, 푥)" ([Tinawi :88](zotero://open-pdf/library/items/KBLMD2YA?page=34))

> "RELUs apply a non-linear transformation to inputs, taking only the positive part of the input." ([Tinawi :88](zotero://open-pdf/library/items/KBLMD2YA?page=34))

> "RELUs are preferred over other activation functions like 푠푖푔푚표푖푑 and 푡푎푛ℎ, because they offer two benefits: sparsity and better learning." ([Tinawi :88](zotero://open-pdf/library/items/KBLMD2YA?page=34))

> "The second advantage, sparsity, can be observed when 푥 ≤ 0 and the values default to 0. This transformation leads to more dense representation of matrices, speeding up the learning process for the network and decreasing its size." ([Tinawi :88](zotero://open-pdf/library/items/KBLMD2YA?page=34))

> "Time series forecasting problems are in essence a supervised learning task. While the data initially is not "labeled", a few easy transformations, described in Data Preprocessing (section 4.2 of System Architecture), can allow us to treat the data as if it's supervised." ([Tinawi :88](zotero://open-pdf/library/items/KBLMD2YA?page=34))

*The slope of the tanh function becomes increasingly smaller the larger x gets. This means that (in a range of values from 1 to 1000), tanh(600) - tanh(400) would be much larger than tanh(1000) - tanh(800). This is known as the vanishing gradient problem. ([note on p.88](zotero://open-pdf/library/items/KBLMD2YA?page=34))*

 

*RELU functions avoid the vanishing gradient problem by using a constant gradient value, which results in faster learning. ([note on p.88](zotero://open-pdf/library/items/KBLMD2YA?page=34))*

 

> "In supervised learning settings, artificial neural networks are trained with a technique called gradient descent (GD). The aim of GD is to minimize an objective function, usually a heuristic cost function of how far the predictions were from the training value." ([Tinawi :89](zotero://open-pdf/library/items/KBLMD2YA?page=35))

> "In gradient descent, in order to find the best value of a parameter we subtract the gradient of the cost function with respect to that parameter" ([Tinawi :89](zotero://open-pdf/library/items/KBLMD2YA?page=35))

> "However, gradient descent turns out to be slow in training, so we use a variant called Stochastic Gradient Descent (SGD), where instead of using the cost gradient of all examples, we calculate it only for one example at each iteration." ([Tinawi :89](zotero://open-pdf/library/items/KBLMD2YA?page=35))

> "The SGD algorithm proceeds as follows. First, we choose an initial vector of parameters 푤 and a learning rate 휂. Next, we repeat the following until convergence (a minimum error is reached)" ([Tinawi :89](zotero://open-pdf/library/items/KBLMD2YA?page=35))


## References
1. [tinawi_](zotero://select/items/@tinawi_)
