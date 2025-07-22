---
type: paper
tags: academic
---
# Machine Learning for Time Series Anomaly Detection

A model can "learn" when it can estimate a data point by inferring some structure from previous data. In other words, it can learn patterns based on previous data that will help calculate new data.

In many machine learning setups, models perform better with the use of normalization techniques.

Regularization techniques result in better performance in Neural Networks. By regularizing training data, Neural Networks can avoid overfitting.

In Machine Learning, an autoencoder is a kind of artificial neural network used to learn codings of patterns in an attempt to recreate them (kind of like a signal generator). Autoencoders are unsupervised, so input sequences don't require labels. Autoencoders aim to replicated input sequences based on data representations learned from previous sequences. They have the ability to compress data in the input layer into some temporary representation, and then decode this representation back to the original data. It's kind of cryptography in the sense that you can use some key to make words difficult to understand, but by using that key again, you can translate the words back to normal.

The LSTM Encoder-Decoder takes in a time series sequence. The output is the recreated sequence, encoded and then deconstructed by the LSTM Decoder layer. To measure the accuracy of the model, the ==mean squared error== is used.

Mean squared error (MSE) is an average of the squares of the errors between predicted values and the real ones. The larger the Mean Squared error, the worse the predictions were, and there is no theoretical bound on how large erro can get. The minimum error is 0, where predicted values are identical to real ones. Here is the formula: $M S E=\frac{1}{n} \sum_{i=1}^{n}\left(Y_{i}-\hat{Y}_{i}\right)^{2}$, where $\hat{Y}$ is the predicted value.

Types of Autoencoders:
- Regular Autoencoders
- Denoising Autoencoders
- Spare Autoencoders
- Variational Autoencoders

A Multilyer perceptron (MLP) is a type of feedforward artificial ==neural network== architecture comprised of at least 3 layers:
1. An input layer
2. Hidden layer
3. Output layer

MLP hidden layers have a non-linear activation function.

Multilayer perceptron Neural Networks are considered to be the vanilla neural networks because they don't include any recurrent, convolutional, or gated layers that are more common in newer networks. They are basically standard linear ==perceptrons== but with nonlinearity introduced.

Multilayer perceptron activation functions:
- The Hyperbolic tangent ($\tanh$)
	- Maps all real numbers to an output range of [-1, 1] for ==feature scaling==.
	- The slope of the $\tanh$ function becomes increasingly smaller the larger x gets. This means that (in a range of values from 1 to 1000) $\tanh(600) - \tanh(400)$ would be much larger than $\tanh(1000) - \tanh(800)$. This is known as the ==vanishing gradient== problem.
- Rectified Linear (RELU)
	- Used in the training of ==Deep Neural Networks==.
	- Function definition: $f(x)=\max (0, x)$
	- Applies a non-linear transformation to inputs, taking only the positive parts of inputs.
	- RELUs are preferred over other activation functions because of its ==sparsity== and better learning. They also avoid the ==vanishing gradient== problem by using a constant gradient value, which results in faster learning.
- Sigmoid

Time series ==anomaly== detection uses various statistical methods to try and find anomalies in ==sequential data==. In time series anomaly detection, you are implicitly assuming that all training data has no anomalies whatsoever. Therefore, you should be intentional with how you split your training and testing sets.

Data pre-processing methods:
- Time series forecasting
	- Time series aggregation
		- Combines data across time intervals, thereby changing the frequency of the data.
		- Takes in time series data and clusters data spanning a certain interval, then uses mathematical aggregation methods like mean and median of new clusters. This method is useful because it reduces the size of data sets by changing the frequency at which the data is sampled.
		- For example, here is a time series of temparatures: [1: 32, 2: 47, 3: -8, 4: 87, 5: 74, 6: 56]. Time series aggregation grouping 3 values would make this new time series (using the mean): [1: 23.67, 4: 77.33].
		- Can be limiting when looking for individual anomalous events, but helps to focus on long-term trends
	- Rolling window sequences
		- Is a method commonly used to prepare time series data for building forcasting models.
		- Creates overlapping sequences used for prediction in time series forecasting models.

In a time series forecasting problem, the output layer is a single unit that predicts the value at the next time step.

Time series forecasting problems are in essence a supervised learning task. While data is not initially "labeled", after data pre-processing transformations, data can be treated as if it is ==supervised==.

Machine Learning Anomaly detection methods:
- Clustering
	- Clustering techniques are distance-based, meaning that clusters are formed based on how far a data point is from others. These methods do not require data to be labeled (==Unsupervised==).
	- To conduct time series anomaly detection with the clustering technique, a signal is passed in as individual data points. The number of clusters is set to 2 (for one anomalous and one normal cluster) or 3 (anomalous, normal, and outliers).
	- The problem with a clustering approach is that the algorithm assumes that the data is equally distributed across the clusters. For instance, a given signal may have little to no anomalies, but the clustering technique will still attempt to find a set number of them.
	- Another issue with clustering-based approaches is that contextual anomalies are lost. For example, an unexpectedly high temperature in the winter is just assigned to the summer cluster instead of being flagged as an anomaly.
	- Example: the Inductive Monitoring System built by NASA (IMS)
- Wavelet transforms
- Autoregressive models
	- Autoregressive (AR) models are a type of ==linear regressions== where the independent variables are a time lag of the previous dependent variables.

Linear regressors often use a method called ==Ordinary Least Squres== to determine the coefficients of variables and the intercept. Linear regression written in matrix notation is $y=X\beta + \epsilon$ where:
$$y=\left[\begin{array}{c}\mathrm{y}_{1} \\ \mathrm{y}_{2} \\ \vdots \\ \mathrm{y}_{n}\end{array}\right], X=\left[\begin{array}{cccc}1 & \mathrm{x}_{11} & \ldots & \mathrm{x}_{1 p} \\ 1 & \mathrm{x}_{21} & \ldots & \mathrm{x}_{2 p} \\ 1 & \vdots & \ddots & \vdots \\ 1 & \mathrm{x}_{n 1} & \ldots & \mathrm{x}_{n p}\end{array}\right], \beta=\left[\begin{array}{c}\beta_{0} \\ \beta_{1} \\ \vdots \\ \beta_{p}\end{array}\right], \epsilon=\left[\begin{array}{c}\epsilon_{0} \\ \epsilon_{1} \\ \vdots \\ \epsilon_{n}\end{array}\right]$$

In Ordinary Least Squares (OLS), the objective is to minimize the ==squared error== between the predicted values $y$ and the observed dependent values $X \beta$. Here is the equation:
- $\hat{\beta}=\operatorname{argmin}_{\beta}\left(\|y-X \beta\|^{2}\right)$ where:
	- $$\begin{gathered}
X \hat{\beta}=y \\
X^{T} X \hat{\beta}=X^{T} y \\
\hat{\beta}=\left(X^{T} X\right)^{-1} X^{T} y
\end{gathered}$$

Independent variables are multicollinear if the output variables can be predicted from the independent variables with a substantial degree of accuracy.

K-means ==clustering== serves to separate n observations into k clusters, where each new datapoint is assigned to the cluster with the closest mean.

Deep Learning Anomaly detection architechtures:
- Recurrent Neural Networks (RNNs)
- Long Short-Term Memory (LSTM) networks
	- A recurrent architecture, meaning that the output at one step is fed back into the system, creating a loop.
	- Have the ability to learn the long-term relationship between past data and current values, which makes it capable of doing ==classification== and prediction problems.
	- An LSTM unit doesn't automatically apply previous signals to the current step (in other words, doesn't necessarily use all previous information to influence future predictions). Instead, it uses a set of cells to predict which previous time steps would be useful to predict the current one.
	- An LSTM unit is comprised of a cell, an input gate, an output gate, and a forget gate. All components work together to forecast the next step. The cell remembers values over time while the three gates regulate the flow of information in and out of the cell.

A good anomaly detection model is not strict in identifying cases, leading to too few anomalies being noticed, but is also not too over-sensitive such that many normal points are flagged as anomalies. The best system has a small number of false positives and false negatives.

Anomaly detection is commonly accomplished with ==Unsupervised learning== because machines don't intuitively know whether anomalies have occurred or not. Supervised learning approaches would require experts to label data first.

Machine Intelligence programs for anomaly detection can monitor information from critical systems and flag anomalies as they occur. Human experts can then view these flags and make decisions on a case-by-case basis.

Context ==anomalies== are changes that shift across seasonal trends. For example, the average temperature is much lower in the winter than in the summer. If you encounter a temperature of 80 degrees Fahrenheit in the winter, it is most likely an anomaly, whereas in the summer it would be a normal temperature (==Nonstationary data==).

To deal with context anomalies in a machine learning system, the distribution representing the data needs to be changed over time according to the data's cyclic behaviors. For example, if the mean of the data slowly increases over time, the machine learning model checking for anomalies should adjust its model distribution to match it.

Nonstationary data is characterized by having a mean and variance that shifts with time. Dynamic error thresholding makes uses of this information to establish accurate error cutoffs that change with the data.

In ==supervised learning== settings, ==Neural Networks== are trained with a technique called Gradient Descent. 

Gradient Descent can minimize an objective function by calculating how far it is from the training value and then making the necessary changes to weights. In order to find the best value of a parameter (weight), the ==gradient== of the cost function is subtracted from that parameter:
>$$\theta_{j}=\theta_{j}-\alpha \times \frac{\partial}{\partial \theta_{j}} J(\theta)$$
>where $\alpha$ is the learning rate, $\partial$ is #⌛TBC 

A faster variant of ==Gradient Descent== is Stochastic Gradient Descent (SGD), where instead of calculating the best value for one parameter at a time, it calculates the optimal values of a vector of all parameters at once. The SGD algorithms proceeds as followed:
1. First, we choose an initial vector of parameters $w$ and a learning rate $\eta$.
2. Next, the following are repeated untill minimum error is reached (==convergence==):
	1. Randomly shuffle examples in the training set
	2. $\text { For } i=1,2, \ldots, n \text { do } w=w-\eta \nabla Q_{i}(w)$ (where $\nabla$ is the gradient vector of a function, and $Q_i$ is the loss function)

## References
1. [[@tinawi_|Machine Learning for Time Series Anomaly Detection]]