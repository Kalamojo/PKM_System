# Learning From Failure Report

## LFF Background

The Learning From Failure Paper is based on a primary assumption:

- Biasing features are easy to learn than desired features for image classification

For example, given the task of classifying the animal in an image, it is much easier to learn how to make decisions based on the texture of the animal alone, as opposed to looking at the general shape to make decisions. Given this assumption, it would be logical to conclude that if you trained a model to learn to use more difficult features to make predictions, then that model would likely be more accurate in real-world scenarios.

The way this is accomplished is by first training a biased model that learns easy features quickly. Then, a debiased model will look at the biased model and see what features *not* to learn, ensuring that it focuses on difficult features first.

## Experiements

To see if this assumption always holds, we are trying both a simple Multilayer Perceptron vs a De-biased Multilayer Perceptron on an image classification task. The feature we are making the model predict is whether or not a person is wearing lipstick. My assumption is that the if a person has makeup, a de-biased model may opt to ignore a simple feature like the pixel colors of someone's lips and opt for the more difficult task of determining whether they are wearing makeup or not.

The training data was imbalanced to ensure that the condition of wearing lipstick occurs frequently with the condition of wearing makeup. However, for evaluation, the model is tested on balanced classes.

## Results

Here are the accuracies of each model's predictions on the balanced testing data:

| Model        | Lipstick with Makeup | Lipstick with no Makeup | No Lipstick with Makeup | No Lipstick with no Makeup |
| ------------ | -------------------- | ----------------------- | ----------------------- | -------------------------- |
| Basic MLP    | 75.2%                | 100%                    | 42%                     | 0%                         |
| Debiased MLP | 86.8%                | 100%                    | 42.4%                   | 0%                         | 

While the Debiased MLP managed to perform slightly better than the basic model, its results on the balanced data suggest that it still suffers from the same biases. It is far more likely to predict the lipstick condition and performs better on no-lipstick images when there is makeup present.

While there is no certainty as to what the debiased model really understands from the data, it is apparent that it did not learn in a way that generalized to "in the wild" data. It, too, suffered from the biases that resulted from training on images with closely correlated features, and its method of training on the more difficult features didn't seem to help. It seems that my assumption that the model would learn a somewhat difficult task that isn't beneficial seems to have held true, though it does not perform worse than the basic model at the very least.

## Conclusion

This approach of debiasing certainly has promise in many scenarios of classification, or maybe even other tasks. However, I believe the assumption that it will just automatically make your model "better", regardless of the data you are training on, has been shown to be unjustified. In situations where a biasing feature is more difficult to learn than the key feature, a "debiased" may not offer many performance improvements at all. Maybe with an alternative set of features for prediction, the debiased model may have even performed worse than a basic approach.

This just goes to show that approaches like the one presented in the Learning from Failure paper should be researched carefully and that the data being predicted upon has a high influence on the effectiveness of certain models.