# Store-Number-Extractor-Encoder-Decoder-BiLSTM-model-

## INTRODUCTION

The Store number extractor is a model that extracts the store number of an address when given the full address as input in text format. An accuracy of 93% was obtained on test dataset. This model was attempted because the use of regular expressions to extract these numbers did not do well for majorly the extreme cases. For example, in the case where we have several chunks of numbers in a store address: No. 21b clayton 7870, sandy springs.


**However, it is important to note that the dataset used was automatically generated (dummy data: random numbers placed at different locations of randomly generated text) and therefore contained some irregularities ( target numbers were different from the numbers actually present in the text provided)**. Therefore, this abnormality probably would have affected the learning process and hence the performace at inference.

It was also therefore posited that these model might do really well on real store address data because it would learn the patterns and positions of store numbers in the real addresses.


## INPUT
Store addresses (dummy text of numbers and some random strings in this training data case)

## OUTPUT
The numbers in the address (dummy text in this case)

# METHOD
An Encoder-Decoder system was used to model the training data at a character level. The encoder was a 3 layered Bi-directional GRU used to esxtract information about index characters and neighbouring characters. The decoder uses an attention mechanism to extract information about the next important digit from the encoded address and then passes it to a GRU model that outputs the next hidden representation of the next digit given the previous digit. The output of this GRU is then passed to a dense layer that makes final probabilities on the next digit.

# METRIC
Accuracy per digit, Accuracy per target.

For more info on the code, model architecture and explanations, read the .ipynb file attached to this repository.

