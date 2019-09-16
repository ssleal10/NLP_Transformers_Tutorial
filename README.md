# NLP_Homework
**Homework:**

1. Using `Simple_Transformer_AttnIsAllUNeed/simple_transformer.py`, write a detailed pseudocode of what is done in "Attention is all you need" and how the transformer works. At the same time, try training with different words (not just: "i want a beer") and analyze what the attention plot suggests about the training.

2. Using `Transformer_AttnIsAllUNeed/train.py`, implement the METEOR metric and vary the parameters of d_model, dff, h, dk and dv. Then, discuss about the metric (METEOR compared to BLEU, is it really better? ) and whether the behavior you obtain is similar to the presented in the paper (for example: increasing the d_model and dff parameters seems to improve the BLEU obtained, why does it happen? did it happen to you?). Have in mind that this code is using a different dataset from the one used in "Attention is all you need", so keep the distances.

3. BERT Fine-Tuning for Sentence Classification in Jupyter Notebook: report the Matthews correlation coefficient. Briefly discuss the algorithm. `https://colab.research.google.com/drive/1xj364W2xuP6eSLVTTrwSw856KwhTJ3HB`.


**Please be sure to use PyTorch v1.2.0. Further instructions can be found inside the folders.**
