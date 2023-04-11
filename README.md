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
