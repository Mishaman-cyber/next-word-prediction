# next-word-prediction
This project predicts the next for a given input. It is based on python.


This code trains a text generation model using a LSTM (Long Short-Term Memory) neural network architecture in TensorFlow/Keras. Here's a breakdown of what each part of the code does:

Importing Libraries: The code imports necessary libraries including TensorFlow, Keras, NumPy, and regex.

Text Preprocessing: The file_to_sentence_list function reads text data from a file (info.txt) and preprocesses it into a list of sentences. It uses regular expressions to split the text into sentences.

Tokenization: The Tokenizer from Keras is used to tokenize the sentences and convert them into sequences of integers. Each unique word in the text is assigned a unique integer index.

Creating Input Sequences: The code generates input sequences for the LSTM model by sliding a window over each sentence, creating sequences of increasing length (1 to n) for each sentence. These sequences are stored in the input_sequences list.

Padding Sequences: The input sequences are padded to ensure uniform length using the pad_sequences function from Keras. This is necessary for batch processing in neural networks.

Preparing Input and Target: The input sequences are split into input (X) and target (y) data, where X contains all but the last token of each sequence and y contains the last token (the word to predict).

One-Hot Encoding: The target (y) data is one-hot encoded using tf.keras.utils.to_categorical to prepare it for training.

Model Architecture: A Sequential model is created with an Embedding layer, an LSTM layer, and a Dense layer with softmax activation.

Model Compilation: The model is compiled with categorical cross-entropy loss and the Adam optimizer.

Model Training: The model is trained on the input (X) and target (y) data for 500 epochs.

Text Generation: Starting with a seed text ("I am "), the model predicts the next 20 words using the trained LSTM network. The predicted word is appended to the seed text, and the process is repeated iteratively.

Printing Predicted Words: The final generated text is printed, showing the initial seed text followed by the predicted sequence of words.

To follow this code and understand its output in a well-structured format:

Ensure that you have a text file named info.txt containing the text data you want to train the model on.

Execute the code, and it will preprocess the text data, train the LSTM model, and generate text based on the provided seed text.

You can adjust parameters such as the number of epochs, the length of the generated text, and the architecture of the LSTM model to experiment with different configurations and improve text generation results.
