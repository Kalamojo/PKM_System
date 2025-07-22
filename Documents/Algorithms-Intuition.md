---
type: podcast
tags: academic
---
# Algorithms-Intuition

Machine Learning steps:
1. Infer/Predict
2. Error/Loss
3. Train/Learn

The Error/Loss Function gives a measure of how poor a prediction is. When large error is detected, model weights are substantially reduced. When a good prediction is made with little to no error, weights are reinforced or increased.

Machine Learning models are pre-trained with data. The input data is uploaded to an algorithm and it begins training its model until it has a good sense of what determines the output. This first phase of uploading data and training the model is the training step of Machine Learning.

After initial model training, every re-training step is called online learning.

An algorithm is a piece of software or code that takes in data, discovers the relationships between each input, and determines which features contribute to the output. It saves that information on a disk or database but stays linked to the data.

A machine learning model is an algorithm plus the patterns the algorithm has learned.

A spreadsheet imported into an algorithm has rows and columns. Generally, the rows will be the main inputs, like different people or houses or items. The columns are the features of these inputs. These are characteristics of each item that may contribute to a prediction about all of them.

Features are the most crucial part of the learning process. Algorithms determine what coefficients belong next to each feature, creating an equation. By looking at each item and its features one at a time, the algorithm learns what numbers need to be multiplied by each feature to produce the correct prediction. In machine learning, these coefficients are called weights.

Linear Algebra allows you to take many equations, stack them on top of each other, and solve for them all together. When input data is imported into an algorithm, each row or item is an algebraic equation with unknown coefficients. The algorithm uses linear algebra to discover the correct coefficients for the optimal equation.

In a spreadsheet, the combination of all the rows and columns (in other words, the items and features) is a matrix in the mathematical sense. The machine learning algorithm works a matrix of features in order to compute a matrix of coefficients. It averages the coefficients for each feature together, shapes them into a single formula, and uses the formula to make a prediction of the desired output.


Machine Learning has 3 categories of algorithms:
- Supervised Learning
- Unsupervised Learning
- Reinforcement Learning

In Supervised Learning, you the programmer are training your model with lots of information. Algorithms for Supervised Learning Include Linear Regression and Logistic Regression.

Supervised Learning applies to fields like Computer Vision and Speech where an algorithm is trained on a ==corpus of dialogue==. The algorithm learns what makes up sentence structure from one sentence to another and enables the Machine Learning model to construct sentences on its own and hold conversations with humans.

Linear Regression is a continuous function that, given data, will produce a single number output.

Logistic Regression, given data, will predict the class of its inputs.

One of Unsupervised Learnings main algorithms is clustering. In clustering, a model will take its data inputs and toss each of them into a bin that has no class. The model's reasoning for placing each item in its bin is unclear and not easily explained. It finds abstract relationships between items in one bin that make them more similar to each other than items from seperate bins.

In Unsupervised Learning, the Machine Learning algorithm discovers relationships between inputs and segments the inputs into portions of the data population. Unsupervised Learning is commonly used in advertising where a business tries to discover which customers would appreciate similar items based on similar behavior.

Machine Learning Engineers and Data Scientists generally use a mix of both Supervised and Unsupervised Machine Learning Algorithms in their work. While the two types of algorithms are different, they are based on the similar mathematical equations.

Reinforcement Learning is a very "magical" type of Machine Learning that imitates real thought very closely. It reaches into Planning, Knowledge Representaiton, and the other fields of Artificial Intelligence.

Reinforcement Learning involves taking actions and learning their consequences. The algorithm is given a goal and a system of reward and punishment that reinforces certain correct actions. The algorithm figures out the rules of its "game", the actions it is allowed to take, and the best strategy to achieving its goal. The algorithm learns from its own behavior and trains itself.

In Reinforcement Learning, a policy is an algorithm's course of actions.

A common Reinforcement Learning algorithm is a Deep Q network. It uses Deep Learning Machine Learning algorithms to determine the best policy towards achieving a goal. Certain actions in an environment result in negative points while other actions are rewarded positive points.

The Reinforcement Learning "The floor is lava" concept allows algorithms to solve their puzzles faster and more efficiently. In it, every step the algorithm takes subrtacts points, driving the algorithm to solve its puzzle. In other words, being alive "hurts" the algorithm, so it is incentivised to reach its goal as fast as possible.

- Artificial Intelligence
	- Machine Learning
		- Supervised Learning
			- Linear Regression
			- Logistic Regression
		- Unsupervised Learning
			- Clustering
		- Reinforcement Learning
			- Deep Q Networks

## References
1. [[Documents/Annotations/Algorithms-Intuition]]