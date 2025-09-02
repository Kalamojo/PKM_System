---
type: podcast
tags:
  - academic
  - annotation
---
# What is AI, ML, DS

- AI means the theory and development of computer systems able to perform tasks that normally require human intelligence, such as visual perception, speech recognition, decision-making and translation between languages. So basically AI is automated intelligence automation of things that normally require human intelligence.
- As a discipline, AI is broken down into multiple sub-disciplines, straight from Wikipedia. These are reasoning and problem solving, knowledge, representation, planning, learning, natural language processing, perception, motion, and manipulation, social intelligence, and general intelligence.
- NLP is the subdiscipline of AI dedicated to language, anything that is simulated language Is natural language processing.
- Reasoning and problem solving though, are more typically dealing with probabilistic models about the world in order to solve problems.
- So planning is more about taking actions in an environment, whether that be playing video games or driving a self-driving car. where the car needs to be able to take turn by turn actions on the roads.
- It may also need to be able to hear the road hear horns blaring or cars, screeching. And so that would be using microphones, so this is perception. and it also needs to be able to perform actions inside of its environment. This is the subdiscipline called motion and manipulation, which is basically just robotics.
- Social intelligence is the concept of AI being tuned into human emotions. So we may be trying to follow a human's emotional flow through time.
- And then finally, general intelligence or artificial general intelligence. AGI AGI is the pot of gold at the end of the rainbow. It's a pipe dream. It's a pie in the sky. it's the goal of creating an artificial intelligence. That is not only good at its particular tasks, but it's also generalizable to all other domains, so that it is as effective at those as a human, if not better.
- And that's the generality of artificial general intelligence weak means it's dedicated to a specific sub domain, Not necessarily that it's weak at its task, but just that it can only handle specific domain and general means that it can handle all domains And generalize across contexts, universally like a human could.
- The layers by which the software becomes removed from the programmer adds elements of magic to the concept of AI. So a handwritten script is not very magical. A machine learning model, which we'll discuss later that learns, let's say the rules of the game of chess or go, or how to drive a self-driving car down the road. well that's some number of layers removed from the original programmer and that removal adds an element of magic. That magic is the sense by which the concept of AI can be defined subjectively.
- Turing says If you're chatting with this agent and you can't tell if it's a human or an AI then it is intelligent, whether it's the human or the AI, if an AI can sufficiently convince you that it is intelligent through a chat bot, where you're poking and prodding and trying to find the holes and you can't find them, then it is intelligent in the magical sense.

- machine learning is learning on data to make predictions it's pattern recognition over data. So that future predictions can be made.
-  Well, deep reinforcement learning models, not only learn how to play a game or drive on a road by taking actions in an environment and observing the point value. Consequences downstream at the end of the game in order to modify its behavior. But it also learns how the game is played in general. What game is even being played?

- data science, like I said, is the umbrella term that encompasses artificial intelligence and machine learning more than that data science is the umbrella term that encompasses anything related to data. If you're a professional and your daily job is dealing with data, then you are a data scientist.
- Because the typical roles dealing in data science fall, somewhere in this pipeline, a pipeline from left to right beginning to end, the beginning of the data pipeline gets the data from somewhere and pipes it into the machine. And the output of the pipeline is either data analytics, business intelligence, or machine learning.
- The first step of the pipeline is data ingestion ingestion, which is to get your data from somewhere. This data can be in a spreadsheet like Microsoft Excel, Excel, SX, or CSV files. It can be in a database like PostgreSQL or my SQL. Those are relational database management systems.
- A stream means that the data is coming at you so much and so fast that you don't want to store it anywhere. You just want to process it real-time and route You want to receive your data, do stuff to it, and then probably throw it away.
- data set typically means file formatted data. Like a spreadsheet. A data store typically means database formatted data, like on Postgres or my SQL. And then we have a stream or fire hose.
- You want to aggregate all of the data, common, to some use case all together in what's called a data lake. A data lake is the aggregation of various data sets data stores into one repository, one umbrella, and that data's going to be dirty. It's going to not be cleaned up yet.
- A feature store is the phase at which you take the data from the data lake and you clean it up and you store it and it's cleaned up state.
- The first step down the pipe towards data analytics is to store what we've already cleaned up in the data, in something called a data warehouse, a data warehouse, a data warehouse is separate from a data lake. it's a little different. Typically what a data warehouse will do is take a slice of historical data from the recent past, transform that data to be represented in column format rather than row format, and then maybe apply some additional transformations on the data.
- A data analyst is more of a technical role. A data analyst is actually likely to be involved in the entire data science pipeline up until this point, everything we've already discussed such as Ingestion into a data lake feature engineering and working with a data warehouse is likely to also be tasks performed by a data analyst. in addition to the actual analytics task of charting and graphing, looking at the data in order to come up with human decisions.
-  Whereas a business intelligence person, a BI professional is typically a less technical role. They're less likely to be involved in the entire data science pipeline up until this point. And instead is likely to be working with the data from the data warehouse as a consumer, as a user And the giveaway difference between these two roles is the tooling.
- Machine learning is automated predictions. it's predictions and decisions made by robots. now when I say robots, of course I'm being colloquial by machine learning models. So rather than charting and graphing data, as an analyst would do a machine learning engineer will design a model using machine learning

## References
1. https://ocdevel.com/mlg/2