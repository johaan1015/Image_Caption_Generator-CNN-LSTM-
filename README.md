# Image_Caption_Generator-CNN-LSTM-

Created a next word predictor as the base for the image caption generating problem. We don't generate text, we predict the next word that is do a multiclass classification problem from the availabe set of words in our vocabulary.
### Dataset
Trained the model on the flickr8k dataset, where each image has five different captions given. Link to the dataset is given below:
https://www.kaggle.com/datasets/adityajn105/flickr8k

### MODEL CREATION
Used the VGG-16 pre-trained model without the last classification layer to extract features from the images. To process the textual data that is data from captions we created an Embedding layer, followed by an LSTM layer to process the sequential data. Both of these were then concatenated and passed through a final Dense Layer to do a multiclass classification(softmax) where the layer provided probabilities for every word in our vocabulary.

### Textual data format in Next Word Predictor
For every sequence, we run a loop through the length of the sequence and create input sequences till the position i and output sequence which is the next word i. In this way, we transformed the caption generator into a supervised learning problem of next-word prediction. All the input sequences were padded to the same length and all the output sequences were represented as one hot encoded vectors, where length of each vector, the size of our vocabulary.
