# Musica

Musica is my AI Music Composer, which when given Midi files can produce music transcripts for pianists and MP3 files for listening to the music interpreted from the Midi file.

### Background on Midi Files

Unlike regular audio files like MP3s or WAVs, these don't contain actual audio data and are therefore much smaller in size. They instead explain what notes are played, when they're played, and how long or loud each note should be.

### Use It Yourself

#### Training

To train the network you run **lstm.py**.

E.g.

```
python lstm.py
```

It takes a while to train friendly FYI.

#### Running the code

Once you have trained the network you can generate text using **predict.py**

E.g.

```
python predict.py
```

You can run the prediction file right away using the **weights.hdf5** file

### Inspiration

I like music, especially listening to it. I dedicate a lot of time towards organizing my music into compact playlists, and am constantly open to listening to new genres/styles of music.

I also used to play piano when I was little. I performed in local competitions and won a few awards.

The only thing I hated about music is trying to decrypt what looked like hieroglyphics to a treasurer, music sheets.

So as a fellow engineer would, I created an AI model to do it for me, but extended upon this by making it essentially convert Midi files into playable and enjoyable music.

### Topics

- Languages: Python
- Frameworks/Libraries: Keras, NumPy, Music21, Pickle
- Architectures: LSTM-ANNs

It is as simple as cloning, installing the right python dependencies as prompted, and running the Python file in any IDE with the right interpreter.

The Juypter Notebooks follow the above, just run the entire file or any cell given the right IDE and environment.

### Architectures (In Detail)

It is for those who are are curious/interested, in the underlying architecture of each of the models used in Musica.

A Long Short-Term Memory (LSTM) Artificial Neural Network (ANN) is a type of recurrent neural network (RNN) architecture designed to handle sequential data and address the vanishing gradient problem that can occur in traditional RNNs. LSTMs are widely used in various applications, including natural language processing, speech recognition, time series analysis, and more. Let's break down the architecture, working principles, and industry applications of LSTM ANNs:

#### 1. Architecture:

The LSTM architecture consists of several interconnected cells, each with various components. The key components of an LSTM cell are:

Cell State (Ct): This represents the long-term memory of the network. It can store information over long sequences.

Hidden State (ht): This is the short-term memory or output of the cell, capturing relevant information from the current input and past hidden states.

Three Gates:

- Input Gate (i): Controls how much new information is added to the cell state.
- Forget Gate (f): Controls what information from the cell state should be forgotten.
- Output Gate (o): Controls how much information from the cell state should be used to compute the output.

The gates use a combination of sigmoid and tanh activation functions to control the flow of information. Sigmoid functions produce values between 0 and 1, regulating the flow of information, while tanh functions squash values between -1 and 1, controlling the magnitude of information.

LSTM-Based Neural Network Architecture to Infer Heterogeneous Model Transformations:

<img src="https://github.com/ReshiAdavan/Musica/blob/master/imgs/LSTM-ANN-Architecture.PNG" />

#### 2. How it Works:

LSTMs work by processing sequential data step by step, updating the cell state and hidden state at each time step. The core steps in the LSTM operation are as follows:

- Forget Gate: It calculates what information from the previous cell state should be retained and what should be discarded.
- Input Gate: It decides what new information is important to add to the cell state based on the current input and the previous hidden state.
- Update Cell State: It combines the output from the forget gate and the input gate to update the cell state.
- Output Gate: It determines what information from the updated cell state should be used to compute the output at the current time step.
- Hidden State: The hidden state is calculated based on the updated cell state and the output gate. It is used for making predictions and is also fed into the next time step.

The recurrent nature of LSTMs allows them to capture long-range dependencies in sequential data, making them well-suited for tasks where context matters over extended sequences.

LSTM Recurrent Unit:

<img src="https://github.com/ReshiAdavan/Musica/blob/master/imgs/LSTM-Recurrent-Unit.PNG" />

#### 3. Industry Applications:

LSTM ANNs find applications in various industries due to their ability to model and analyze sequential data. Some common use cases include:

- Natural Language Processing (NLP): LSTMs are used for tasks such as language modeling, machine translation, sentiment analysis, and text generation.
- Speech Recognition: LSTMs can be used to recognize speech patterns and convert spoken language into text.
- Time Series Analysis: LSTMs are valuable for predicting stock prices, weather patterns, and other time-dependent data.
- Autonomous Vehicles: LSTMs are employed for tasks like trajectory prediction and object tracking in self-driving cars.
- Healthcare: LSTMs are used for tasks like medical diagnosis, patient monitoring, and predicting disease outbreaks.
- Financial Forecasting: LSTMs help in predicting financial market trends and making investment decisions.
- Video Analysis: LSTMs can recognize patterns and activities in video sequences, making them useful in surveillance and video analysis applications.

Overall, LSTMs have proven to be a powerful tool in handling sequential data, making them a crucial component of many modern machine learning and artificial intelligence applications.

If you made it this far, congrats! That concludes Musica's README.
