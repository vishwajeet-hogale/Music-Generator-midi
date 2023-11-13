# Generating Music with LSTM Neural Networks
## Introduction
Neural networks, particularly Recurrent Neural Networks (RNNs) with Long Short-Term Memory (LSTM) architecture, have found applications in various creative domains, such as text and image generation. 
However, there's a lack of information on using neural networks to create music. 
In this repo, we have built a solution to generate music using an LSTM network in Python, leveraging the Keras library.


## Background
Recurrent Neural Networks (RNN)
RNNs are a class of artificial neural networks designed for sequential information processing. LSTMs, a type of RNN, efficiently learn long-term patterns and are particularly useful for tasks involving remembering information over extended periods, such as music and text generation.

### Music21
Music21 is a Python toolkit for computer-aided musicology, allowing the study and generation of musical compositions. It simplifies the acquisition of musical notation from MIDI files and facilitates the creation of Note and Chord objects.

### Keras
Keras is a high-level neural networks API that simplifies interactions with TensorFlow. It's designed for fast experimentation and prototyping.

### Training
Data
In the provided GitHub repository, piano music, mainly from Final Fantasy soundtracks, is used. The data consists of Note and Chord objects, representing pitch, octave, offset, and simultaneous notes. A total of 352 different notes and chords are identified in the dataset.

### Preparing the Data
Data preparation involves loading MIDI files, extracting notes and chords, and creating input sequences for the LSTM network. The input sequences are then normalized, and the output is one-hot encoded for training.

### Model
The model architecture includes LSTM layers, Dropout layers for regularization, Dense layers for fully connected networks, and an Activation layer. The model is compiled with categorical cross-entropy loss and RMSprop optimizer.

### Training
The model is trained using the prepared input sequences and their respective outputs. Model checkpoints are used to save weights after each epoch.

### Generating Music
After training, the model can be used to generate music. The trained model is loaded, and a starting point is chosen. The model then predicts the next note in the sequence iteratively, generating 500 notes.
The generated encoded representations are decoded to create Note and Chord objects, considering varying offsets between notes. The result is a Music21 Stream object, which is written to a MIDI file.

### Results
The generated music shows some structural coherence, as observed in the sheet music representation. However, there may be occasional inaccuracies due to the network's limitations. The quality of predictions can be further improved by experimenting with the network structure and training parameters.

## Future Work
Several enhancements can be explored, including supporting varying note durations, adding piece beginnings and endings, handling unknown notes, and extending the dataset to include multiple instruments.






