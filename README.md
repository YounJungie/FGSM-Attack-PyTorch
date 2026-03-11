🔐 FGSM Adversarial Attack — Image & Text Classifier with PyTorch

Implementation of Fast Gradient Sign Method (FGSM) adversarial attacks on image and text classifiers, including a defense using adversarial training.
What is FGSM?
FGSM fools a neural network by adding small, invisible noise to the input — calculated from the model's own gradients.
**x_adv = x + ε × sign(∇_x J(θ, x, y))**
The result: a model that was 85% accurate drops to ~10% — just from noise humans can barely see.

**What's Inside**

Part 1 — Image Attack (CIFAR-10)
ResNet-style CNN attacked across epsilon values **[0.0 → 0.3]**.Accuracy collapses as epsilon increases.

Part 2 — Text Attack (NLP)
Bidirectional LSTM sentiment classifier attacked via embedding space perturbation — the standard approach for discrete text inputs.

Part 3 — Defense
Adversarial training: mixing clean + adversarial examples during training. Robust model holds ~55% accuracy under attack vs ~30% for standard model.


References

Goodfellow et al. (2014). Explaining and Harnessing Adversarial Examples
Madry et al. (2017). Towards Deep Learning Models Resistant to Adversarial Attacks

