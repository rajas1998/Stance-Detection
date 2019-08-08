# Stance Detection in Tweets

Course Project for COL772 (Natural Language Processing).

See the report at https://www.overleaf.com/read/hzcbwghksvxv.

Stance Detection is the task of ascertaining
the stance of a text (tweet in this case) with
respect to a given target. Stance can, in the
most basic sense, be for or against the target. This problem can be challenging as the
target may not be present in the given text,
and training data with respect to the test target may not be present. We focus on this more
challenging subset of the task. We build upon
a previous work [1] on the same which used
Bi-Directional LSTMs with conditional encoding, which encodes the tweet dependent on the
target. We demonstrate the shortcomings of
their model, and find that they used a test specific magical post-processing step, which helps
then achieve an F1-score of 0.564. On removing this, their model achieves 0.348. We find
that their model does not handle the skew in
the data. Modifications to the loss function in
this respect, and specific to the metric helped
increase our F-score to 0.542. Further, using
an ensemble model helped us achieve an Fscore of 0.551. This model is robust to changes
in post processing and works across different
test targets as it is more general. We test our
model on the SemEval 2016 Task 6 Twitter
Stance Detection corpus.

Our main contribution was to increase the metric in the case of no target specific preprocessing from 0.348 in the original model to 0.542 in our model. This was done through changing the loss function to optimize the metric and handle skewness, and using an ensemble of model.

[1] https://www.aclweb.org/anthology/D16-1084
