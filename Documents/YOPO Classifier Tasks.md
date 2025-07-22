# YOPO Classifier Tasks

## Current DISCA

1. Take subtomograms, give them to YOPO Feature Model, and it spits a list of features that are vectors
2. Take those vectors and cluster them, could be as simple as K means clustering
3. Now initialize a YOPO Classification Model and have it train by predicting which cluster each feature vector belongs to
4. We then train that classification model further by having it predict which cluster an entire subtomogram belonged to, given the labels of the associated feature vectors
5. Finally, extract the new feature vectors from the trained model, and repeat the process from step 2

## New DISCA

1. Run Current DISCA steps 1-4 for 1 or more iterations
2. Change the output of the trained YOPO model for binary classification
3. Select `n` random points from subtomograms as false positives, and select `m` picked particles as true positives. Use both to train the model
4. Repeat steps 1-3 until convergence
5. Run YOPO binary classifier on all picked particles and filter out those predicted as false positives
