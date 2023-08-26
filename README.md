# Cynthia Machine Learning

## Introduction
Welcome to the Cynthia Machine Learning repository, a core resource for advanced research and development in the field of Machine Learning and Natural Language Processing. This repository encompasses meticulously designed algorithms and models, with a particular emphasis on our Cynthia Transformer.

## Cynthia Transformer
Our Transformer model exemplifies Cynthia's commitment to rigorous scientific research and technological advancement. Utilizing the state-of-the-art attention mechanisms, this model pushes boundaries in the NLP domain, facilitating intricate tasks and overcoming longstanding challenges.

Getting Started with the Cynthia Transformer
Setting Up
To utilize the Cynthia Transformer, start by defining your input data structures.

```python
encoder_input = tf.placeholder(np.int32, shape=[None, 5], name="encoder_input")
decoder_labels = tf.placeholder(np.int32, shape=[None, 6], name="decoder_labels")
```

### Model Integration
Integrate the Cynthia Transformer into your workflow with the following:

```python
softmax, loss, accuracy = transformer(encoder_input,
                                      decoder_labels,
                                      encoder_vocab_size=6,
                                      decoder_vocab_size=10)
```
### Example Data
For testing and experimentation purposes, manually coded example data is provided to evaluate the functionality and performance of the Cynthia Transformer.

```python
# encoder
# ------------------------
# 0: padding
# 1: unknown
encoder_input_data = [[2, 3, 4, 0, 0],
                      [5, 4, 3, 2, 0],
                      [2, 3, 4, 3, 2]]

# decoder
# -------------------------
# 0: padding
# 1: unknown
# 2: start of sequence
# 3: end of sequence
decoder_input_data = [[9, 8, 7, 3, 0, 0],
                      [4, 5, 6, 7, 8, 3],
                      [9, 8, 3, 0, 0, 0]]
```
### Execution
Execute the training loop as follows:

```python
optimizer = tf.train.AdamOptimizer().minimize(loss)

sess = tf.Session()
sess.run(tf.global_variables_initializer())

for i in range(200):
    result = sess.run(
        feed_dict={
            encoder_input: encoder_input_data,
            decoder_labels: decoder_input_data
        }, fetches=[optimizer, softmax, loss, accuracy])
    print(f"{i:<5} {result[2]} {result[3]}")
```
## Quick Links

### Code of Conduct
We value a respectful and inclusive environment. Please review our Code of Conduct for best collaborative practices.

### Contribution Guide
We welcome contributions from the research community. Refer to our Contributor Guidelines for details on how to contribute.

### License
This repository operates under the Apache 2.0 License, granting rights to use, modify, and distribute the codebase. It's imperative to provide appropriate credit, declare modifications, and retain the original license notice. Thorough details can be found in the Apache License 2.0.

## About Cynthia.io Inc.
This repository is the result of dedicated efforts by the team at Cynthia.io Inc. We pride ourselves on rigorous research and development, driven by passion and scientific integrity.

For inquiries, please contact: cynthia@cynthia.io

For additional details on our research and developments, visit: https://cynthia.io

## Conclusion
We invite collaborations, contributions, and feedback from the broader Machine Learning and NLP community. Through joint efforts, we aim to elevate the field's state-of-the-art and drive forward innovative solutions.

