The best model is an LSTM which takes as input the Glove embedding of a sequence of tokens and outputs the mean each the hidden states assumed by the LSTM while processing the sequence.
The output of the LSTM for the claim sentence and the evidence sentence is merged with concatenation, then given as input to a linear layer which classifies the pair Claim-Evidence as
"SUPPORTS" if the claim is true in the evidence, "REFUTES" otherwise.

About the notebook:
The class "ClaimProver" retrieves a model which is a combination of an encoder and a classifier. The encoder can be: an MLP with any number of layers, an LSTM optionally bidirectional 
with any number of layers, a bag of vectors. The classifier is an MLP. We compared the baselines using the whole training set and validation set respectively to train and evaluate them.
According to our experiments the best baseline model is the "RNNAverage", the best merging strategy is the concatenation and the cosine similarity improves the performance.
Extras: oov dealing with weighted mean, weighted loss based on the label frequency, mixed precision to speed up the training, error analysis (some mistakes in the dataset have been found).


Results on the test set, with both kind of evaluations:  accuracy = 0.73%, f1_score = 0.72%.


