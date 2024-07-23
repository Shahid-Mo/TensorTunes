+++
title = "Decoding from Language Models"
date = 2024-07-23T13:24:37-04:00
draft = false
math = true
+++

## Generating from Large Language Models (LLMs)

### A quick refresher on Autoregressive text generation

{{< centered-image src="/images/decoding_1.png" alt="Alt text" width="300" height="100" >}}


In an autoregressive language model, the probability of each token in the sequence is calculated based on the preceding tokens. For instance, the model first calculates the probability of the first token given the context (this might be the input prompt given by the user or can be unconditional text generation as well). Then, it calculates the probability of the second token given the first generated token and the context, the probability of the third token given the first two generated tokens and the context, and so on.

### Decoding what is it about?

What does calculating the probability of the first token mean?
At each time step $t$, the model takes in the preceding context  $y_{<t}$  and computes a vector of scores $\mathbf{S} \in \mathbb{R}^v$, where $v$ is the vocabulary size. For GPT-2, the vocabulary size is 50,257 tokens.

### Greedy Decoding

The idea here is straightforward. Like in any other classification task such as image classification, we just get the argmax as the answer. This is exactly what greedy decoding is.

##### Issues?

The issue with greedy decoding is that once a decision is made, you can't go back and change the decision. For example, there might have been a word like "a" or "the" which, if taken differently, could have led to a higher probability statement overall. There is a simple way to get around this limitation of only considering one possible hypothesis.

## Beam Search

The fundamental idea of beam search is to explore several different hypotheses instead of just a single one. We keep track of the k most probable partial translations at each decoder step instead of just one! 

The dotted red line represents the output of greedy decoding, whereas the red line shows the output after Beam Search.

## The issue with these approaches

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 24
- Color: Truecolor
- Dimensions: 752 x 261
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 714 x 343
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 1030 x 332
- Interlaced: Yes
- XResolution: 120
- YResolution: 120

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 264 x 41
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 579 x 132
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 549 x 109
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 625 x 392
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 782 x 423
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 787 x 393
- Interlaced: Yes
- XResolution: 96
- YResolution: 96

*Image Format: Portable Network Graphic (PNG)*
- Bits Per Pixel: 32
- Color: Truecolour with alpha
- Dimensions: 810 x 486
- Interlaced: Yes
- XResolution: 96
- YResolution: 96



# My Document with LaTeX

Inline math: $E = mc^2$, after this i can type anything



Block math example:
$$
\int_0^\infty e^{-x} \, dx = 1
$$


```python
def hello_world():
    print("Hello, world!")
```
```
echo "Hello, world!"
```