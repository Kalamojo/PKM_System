---
type: podcast
tags: academic
---
# Algorithms-Intuition

- Machine Learning is broken down into three steps: Infer/Predict, Error/Loss function, Train/Learn.
- The Error/Loss function tells me how badly I did. Then I train myself/learn from my mistakes. If the error function said that was a really bad move, then I am going to update my model by substantially reducing some numbers which are called weights.
- If I made a good move, then the error function might tell me to reinforce my weights. Good job.
- The way that the machine learning process works is that you typically pre-train your model uploading a giant spreadsheet. We upload this to our algorithm.
- In machine learning there are many algorithms dedacated to specific tasks, like linear regression. You import your spreadsheet into your linear regression algorithm, for example, and the algorithms trains its model until it thinks it has a very good sense of what it takes to determine the output.
- That first phase of uploading your spreadsheet and training your model, that sort of pre-training phase, thats just called training. Every new step where you retrain your model is called online learning.
- An algorithm is a piece of software, written in python and tensorflow typically, that takes inputted data and finds what is in common with all inputs that determines the output. It saves that information, on disk or in a database or in memory, but kind of tied to the algorithm itself.
- The the algorithm plus the saved data is called the model. The model is the algorithm plus the pattern it has learned.
- The spreadsheet that you import into your algorithm has rows and columns. The rows may be the inputs, like house 1, house 2, house 3, etc.
- The columns are features. Features are peices of the inputs that contribute to a prediction. For example, number of bedrooms, number of bathrooms, square footage, and distance to downtown. Each one of those pieces of a house is called a feature.
- Features can be multiple types of information. Pure numbers are called numeral features. Nominal features are categorical.
- Features are the most important part of the learning process. The algorithms determines what coefficient to put next to what feature, and what you get is an equation. The algorithm will look at a single row at a time, and what it learns is what number to multiply each of the features by. These are called coefficients in mathematics, but in machine learning they are called weights.
- The features are your variables x, y, and z in algebra. In fact, algebra is a primary math of machine learning. What linear algebra does is it allows you to take a bunch of equations and stack them on top of each other and then solve for all of them together.
- When you pipe your spreadsheet into your algorithm, each row is basically an algebraic equation where the machine learning algorithm is learning the coefficients next to each feature.
- The whole combination of rows and columns, the entire spreadsheet, is called a matrix in mathematics. Your machine learning algorithm is working with a matrix of features in order to compute a matrix of coefficients. It averages them all together, boils them down to a single formula that can then be used to make a prediction for your desired output.
- Machine learning is actually broken down into 3 categories of algorithms: supervised learning, unsupervised learning, and reinforcement learning.
- In Supervised learning, you are training it with a bunch of information. Examples are Linear Regression and Logistic Regression.
- Linear Regression will give you a number output. It is a continuous function. Based on the inputs, it gives you a number. Logistic Regression predicts a class. Is what I'm looking at a cat or a dog?
- In Unsupervised learning, the machine will take your examples and will toss it into a bin. This is called clustering, a sub-branch of unsupervised learning. 
- Unsupervised Learning will put it into a bin, but that bin doesn't have a class. For example, it looks at a ball and its blue and kind of misshapen. Ball #1 goes into one bin. It then picks up a new ball and its red has spikes. Ball #2 goes into another bin. When the human asks it why it made its decisions, it cant really explain it. Its just that some balls have a lot more in common than compared to some other balls elsewhere.
- So in Unsupervised Learning, the machine learning algorithm figures out what is in common between this and that and segments portions of a data population. An example where unsupervised learning might be used is in user segmentation in advertising. Based on user actions on a site, like what they click, it determines what kind of ads to show them.
- As a machine learning engineer or as a data scientist, you are probably going to use a mix of supervised and unsupervised learning algorithms on a day-to-day basis. They are different, but generally use the same type of mathematical equations.
- Reinforcement learning is currently seen as the real AI in machine learning. It makes you think, "Is this thing actually thinking". It reaches into planning and searching and reasoning and knowledge representation and the other fields of Artificial Intelligence.
- Supervised learning applies to fields like Vision and Speech where you are training a machine learning algorithm on a corpus of dialogue. It learns what makes sentence structure common from one sentence to the next so that it can actually construct a sentence on its own and have a conversation with you.
- Reinforcement learning is involved in taking actions, taking steps. For example, robots taking a step in an environment. Or an Artificial Intelligence bad guy in a video game trying to figure out how best to kill you. The way reinforcement learning works is that you give it a goal and you give it a system of reward and punishment. That is the reinforcement step.
- The Reinforcement machine learning algorithm will figure out on its own what are the rules of the game, what are the actions it can take, and the best strategy to achieving its goal.
- Unlike Supervised learning, where you the programmer train the algorithm with a bunch of data and it learns the equation for what all this data has in common in order to predict a numeric value or a class, a reinforcement algorithm learns from its own behavior what actions to take in an environment.
- Reinforcement Learning is action oriented and it sort of trains itself.
- A common Reinforcement Learning algorithm is Deep Q networks. So it uses Deep Learning Machine Learning algorithms in order to determine the best course of actions (a course of actions is called a policy in reinforcement learning) towards achieving a goal. You give it negative points for certain things in an environment and positive points for certain things in an environment.
- The key to the puzzle for making reinforcement learning algorithms solving their puzzle quickly and effectively is this thing called the floor is lava. Basically, every step the algorithm takes subtracts points, so it wants to reach its goal as fast as possible. "The floor is lava," so being alive hurts and it is in the algorithm's best interest to solve its puzzle fast.
- Artificial Intelligence. A subfield of AI is Machine Learning. Machine Learning is broken down into 3 subfields: Supervised Learning, Unsupervised Learning, and Reinforcement Learning. In each subfield of ML, there are multiple algorithms.
- In Supervised Learning, there is Linear Regression, Logistic Regression, etc.

## References
1. https://ocdevel.com/mlg/4