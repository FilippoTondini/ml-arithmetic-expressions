# Neural Calculator: Generalization on Arithmetic Expressions

## Abstract
This project investigates the generalization capabilities of neural networks on a simple mathematical task: the neural calculator. The primary objective is to train a machine learning model that receives an arithmetic expression as a string and accurately predicts its integer output value. 

Our main goal is to evaluate generalization beyond the training distribution. Specifically, we focus on the extrapolation behavior of three substantially different architectures: FCNN, CNN, and LSTM. We aim to assess their robustness not only to the sequences observed during training but also to out-of-distribution (OOD) and long-sequences tests.

## Data Augmentation
To improve coverage, we applied custom data augmentation specifically built to improve the models' accuracy on OOD and longer sequences. We generated 36,000 synthetic expressions specifically targeted to fill the 15-21 character length region. The expressions are built step-by-step starting from a base element, ensuring perfectly accurate mathematical labels automatically, eliminating the need for any external parsing tools or post-processing.

## Models Evaluated
*   **Fully Connected Network (FCNN/MLP):** Designed to map character sequences to continuous numerical values. 
*   **Convolutional Neural Network (CNN):** Focuses on local pattern recognition. We evaluated various pooling strategies and network depths to optimize performance.
*   **Long Short-Term Memory (LSTM):** Both UniLSTM and BiLSTM were evaluated. BiLSTM reads tokens one at a time and preserves the full ordered sequence with an unbounded receptive field.

## Results
The best model, a bidirectional LSTM, reaches **98.7% (test_id)**, **96.0% (OOD)** and **86.7% (long-sequences)** exact accuracy. 

BiLSTM remains the most stable across all splits, overcoming the degradation caused by increasing structural complexity, length, and parenthesis depth.
