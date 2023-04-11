# paper-reviews
some papers

# Unbiasing recsys via uniform-sampled data
This line of work asserts the data P(x) to train our recsys models is biased in various unknown ways. To ammend that, we assume we have a second dataset X' collected using a uniform strategy so P(x') ~ uniform. Using the unbiased data we can build an unbiased model, however we generally have a small unbiased dataset as it is expensive to collect (we might show users many non-relevant items, affecting sales).

Here are some papers on the topic:

1. Transfer Learning in Collaborative Recommendation for Bias Reduction (https://dl.acm.org/doi/pdf/10.1145/3460231.3478860)
    - The idea is an interesting form of transfer learning: use the biased data to learn good but biased features and use the diff to the smaller uniform data to learn the bias. Then adjust the biased representation using the learn bias predictor.
    - Some things are not clear to me (such as the last loss function).

2. Causal Embeddings for Recommendation (https://dl.acm.org/doi/pdf/10.1145/3240323.3240360)
    - A multitask collaborative filtering approach for debiasing, which causality inspired motivation.
    - They factorize both biased and unbiased datasets into dense vectors simultaneously, and add use a regulazation term to enforce a degree of similarity between the same item/user similar in both factorization tasks.
    - They show that one should optimize the task for the unbiased case using a causality based approach, showing that one should simply model the unbiased data well. Not sure I like the long motivation for coming up with a trivial result. Perhaps the interesting thing is providing a theoretic basis for their regularization approach. 

3. A General Knowledge Distillation Framework for Counterfactual Recommendation via Uniform Data (https://dl.acm.org/doi/pdf/10.1145/3397271.3401083)
    - interestingly: show via an a/b test that even a simple strategy of collecting 1% unbiased data, and training a model over both biased and unbiased together produces a model that is better than the baseline, and the lift outweights the cost of obtaining the 1% unbiased dataset. 
    - Propose 4 'distilation' methods for using biased and unbiased data together, however the term 'distilation' is used quite broadly...
    - Label distilation: 2 approaches. (1) Training biased and unbiased models, and using a 'bridge' dataset, which are random set of items, and encouraging the models to predict the same for these. (2) training an unbiased model using the small unbiased training set and imputing the labels for the biased model
    - Feature distilation: train a teacher model to have good unbiased features and use that to train a student model.
    - Sample distilation: use models from other works and another heuristic approach to train a model.
    - Model distilation: ... some other stuff
    - This is a catch-all paper with too much methods in it. An attempt at classifying different 'distilation' methods that I didn't like and a big evaluation table that does not give a clear insight...
