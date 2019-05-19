# Visual Question Answering

# Introduction

- Visual Question Answering comes with the potential to solve a plethora of real world problems.
- The ability to decode images and answer questions based on their elements is fascinating. A few examples could be - analysis of reports, knowledge bank, question answering engine, and so forth. 
- With the advent of deep learning, these seemingly intricate tasks have now become a possibility. 
- In this project, we aspire to build models that help us build a visual question answering system.

# Usage Steps


# Models 
- In this project, we experiment by implementing 4 models. 
- Our motivation to do so was to try and understand the effect of CNN based models, RNNs such as LSTMs and GRUs along with attention mechanisms on the various VQA tasks.

## Model 1 - Append Image as Word
- In this model, we first find word level embeddings using the Embedding layer provided by tensorflow.
- We then treat the input image as a word, and append it to the words corresponding to the corresponding question.
- The total input question tensor is then put in the RNN such as GRU.
- The output of the RNN is passed through a final dense layer with softmax activation. The output of this layer is the answer to the question.

## Model 2 - Prepend Image as word
- This model is similar to the model 1.
- The difference is that instead of appending the image as a word, we prepend it to the question tensor.
- This tensor is then passed through LSTM, the output of which is then passed through the final dense layer with softmax activation. The output of this layer is the answer to our question.

## Model 3 - Question through LSTM with image
- In this model, instead of making a total question input tensor including image as a word, we process only the question tensor through LSTM. 
- Once we have the processed question, we then append it to the input image.
- The combined tensor is then fed to the final dense layer with softmax activation. Again, the output of the final layer is the answer to our question.

## Model 4 - Attention Based Model
- As our final model, we implement an attention based model. 
- Our intuition is that an attention on the image along with its corresponding question at sentence level and word level should help us arrive at better answers.
- Thus, we build an alternating co-attention model where we apply attention at word level and sentence level, along with the corresponding image. 
- The prediction of the final layer then corresponds to the answer to our question.


# Observations, Analysis and Conclusions

# Sample Predictions

