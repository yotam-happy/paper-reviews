# paper-reviews
some papers

# Unbiasing recsys via uniform-sampled data
This line of work asserts the data P(x) to train our recsys models is biased in various unknown ways. To ammend that, we assume we have a second dataset X' collected using a uniform strategy so P(x') ~ uniform. Using the unbiased data we can build an unbiased model, however we generally have a small unbiased dataset as it is expensive to collect (we might show users many non-relevant items, affecting sales).

Here are some papers on the topic:

1. Transfer Learning in Collaborative Recommendation for Bias
Reduction (https://dl.acm.org/doi/pdf/10.1145/3460231.3478860)
    - The idea is an interesting form of transfer learning: use the biased data to learn good but biased features and use the diff to the smaller uniform data to learn the bias. Then adjust the biased representation using the learn bias predictor.
    - Some things are not clear to me (such as the last loss function).
2. 
