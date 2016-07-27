# Distilling the Knowledge in a Neural Network [https://arxiv.org/abs/1503.02531](url)

The author describes a different kind of training - "Distillation" to transfer the knowledge from
a complex ensemble of models to a small model which is more suitable for deployment. The core idea is that the relative probabilities of incorrect answers assigned by the complex model carries a lot of information about how the model is trying to generalize. Using Distillation, the small model tries to learn this generalization information. Later, he also discuss the specialist framework in the case of very large dataset like the JFT (google).

Important Points:

-  Less amount of Data is required to transfer knowledge.
-  The learning rate for distillation is much higher than the rate at which the training happens.
-  Learning directly from logits (not normalized scores) as done in a previous paper, is a special case of the presented distillation approach.
- Unlabeled data can also be used to transfer knowledge but the same training data works well in practice.
-  The temperature used in the softmax layer is generally between 1 to 10 and it depends on the problem being tackled.
-  The small model is able to generalize well. For example, the MNIST network learns the the knowledge about how to generalize that is learned from translated training data even though the transfer set does not contain any translations.
-  The small model is also able to generalize well on new type of data. For example, the MNIST networks learn to recognize digits without ever having seen them, solely based on the "errors" that the teacher network makes. (Bias needs to be adjusted)
-  It shows that distillation works well for transferring knowledge from an ensemble or highly regularised model into a smaller model

Questions:
- It did not discuss about distilling the knowledge from specialist into one single net ?
- I would like to know how the specialist would distill knowledge without the help of generalized net, like coufusing classes combined into one specialist which decides the fate of prediction?
