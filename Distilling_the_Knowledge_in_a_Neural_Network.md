# Distilling the Knowledge in a Neural Network [https://arxiv.org/abs/1503.02531](url)

The author describes a different kind of training - "Distillation" to transfer the knowledge from
a complex ensemble of models to a small model which is more suitable for deployment. The core idea is that the relative probabilities of incorrect answers assigned by the complex model carries a lot of information about how the model is trying to generalize. Using Distillation, the small model tries to learn this generalization information instead of learning to generalize on the data. 

Important Points:

-  Less amount of Data is required to transfer knowledge.
-  The learning rate for distillation is much higher than the rate at which the training happens.
-  Learning directly from logits (not normalized scores) as done in a previous paper, is a special case of the presented distillation approach.
- Unlabeled data can also be used to transfer knowledge but the same training data works well in practice.
-  The temperature used in the softmax layer is generally between 1 to 10 and it depends on the problem being tackled.
-  The small model is also able to generalize well on new type of data. For example, the MNIST networks learn to recognize digits without ever having seen base, solely based on the "errors" that the teacher network makes. (Bias needs to be adjusted)
-  The idea of distillation does not fit in the idea of using large number of specialist net instead of single large net.

Questions:
- Would like to see how the distillation method would perform if each specialist net were distilled ?
