# Project-English-German-Translator

This description was taken from my blog post [Neural machine translation with attention – Project: English-German translator](https://mathchine-learning.blogspot.com/2020/09/neural-machine-translation-with.html).

## Neural machine translation
Neural machine translation, or NMT for short, is the use of neural network models to learn to translate an input sentence in a source language into an output sentence in a target language. The strength of NMT lies in its ability to learn directly, in an end-to-end fashion.

The first NMT models relied on dense neural networks, although these models were limited by a fixed length input and output sequence. Later, these early models were greatly improved through the use of recurrent neural networks (LSTMs and GRUs are typically used) organized into an encoder-decoder architecture, which allowed for variable length sequences (Seq2Seq models).

## Seq2Seq – Encoder-Decoder architecture
The Encoder–Decoder architecture idea is simple: the encoder neural network reads and encodes a source sentence into a fixed length vector, then the decoder outputs the translation from the encoded vector. The whole encoder-decoder network is jointly trained to maximize the probability of a correct translation given a source sentence.

The main strength of this model relies on its ability to let inputs and outputs be different sizes. Nonetheless, these kinds of models, although effective, have big issues with long sequences of text. The problem lies in the fixed length vector representation that must be used to decode the sequence. As you can imagine, in the case of a long sequence, as individual inputs begin stacking up inside the encoder final hidden states an information bottleneck occurs. Another issue surfaces as the later input steps in the sequence are given more importance.

As a result, these models perform really well for shorter sequences and not so well for longer and more complex ones.

## Encoder-Decoder architecture with attention
The idea behind this kind of models relies on providing the model with an attention mechanism that allows the model to learn where to focus its attention on the input sequence, as each word of the output sequence is decoded. This architecture is currently the state-of-the-art on machine translation and is used for example in Google Neural Machine Translation system, the system behind Google Translate service.

On the Jupyter Notebook we went deeper into the Encoder-Decoder with attention architecture. We implemented an NMT model that translates from English to German using the Trax framework, an end-to-end library for deep learning that focuses on clear code and speed, actively used and maintained by the Google Brain team, as I believe in the near future it will become the meta library for deep learning. However, you can use pyTorch or TensorFlow framework if you wish, as both support most of the functions we will use in this project.
