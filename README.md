 ##FGSM Attack from Scratch — Fooling Image & Text Classifiers with PyTorch
A hands-on implementation of Fast Gradient Sign Method (FGSM) adversarial attacks on both image and text classifiers — including a working defense using adversarial training.

📌 What is FGSM?
Fast Gradient Sign Method (FGSM) is one of the most well-known adversarial attack techniques in AI Security, introduced by Goodfellow et al. (2014).
It works by adding a small, carefully crafted perturbation to the input, causing a neural network to misclassify — while the input looks almost identical to the human eye.
x_adv = x + ε × sign(∇_x J(θ, x, y))
SymbolMeaningxOriginal inputεPerturbation strength (epsilon)∇_x JGradient of loss w.r.t. inputx_advAdversarial example

🗂️ Project Structure
FGSM-Attack-PyTorch/
│
├── FGSM_Attack_Project.ipynb   # Main notebook (run on Google Colab)
├── README.md                   # This file
├── LICENSE                     # MIT License
└── .gitignore                  # Python gitignore

✨ Features
🖼️ Part 1 — Image Classification Attack

Custom ResNet-style CNN trained on CIFAR-10
FGSM attack across multiple epsilon values [0.0, 0.01, 0.02, 0.05, 0.1, 0.2, 0.3]
Visual comparison of clean vs adversarial images
Accuracy vs epsilon plot

📝 Part 2 — NLP Text Classification Attack

Bidirectional LSTM sentiment classifier
FGSM attack in the embedding space (standard approach for discrete text)
Per-sample attack result visualization

🛡️ Part 3 — Defense: Adversarial Training

Train model on mix of clean + adversarial examples
Side-by-side comparison: Standard model vs Robust model
Robustness gap visualization


🚀 Quick Start
Option 1 — Run on Google Colab (Recommended)
Click the badge below — no setup needed:
Tampilkan Gambar

Click Runtime → Run all
Wait for training to complete (~10-15 min with GPU)
View results and visualizations inline


💡 Tip: Enable GPU for faster training — Runtime → Change runtime type → T4 GPU

Option 2 — Run Locally
bash# Clone the repo
git clone https://github.com/Jung1eBear/FGSM-Attack-PyTorch.git
cd FGSM-Attack-PyTorch

# Install dependencies
pip install torch torchvision matplotlib numpy tqdm

# Open notebook
jupyter notebook FGSM_Attack_Project.ipynb

📊 Results
Image Attack — Accuracy Drop Under FGSM
Epsilon (ε)Model Accuracy0.000 (clean)~85%0.010~75%0.050~50%0.100~30%0.200~15%0.300~10%

As epsilon increases, the model becomes increasingly fooled — even though the images look nearly identical to humans.

Defense Results
ModelClean AccUnder Attack (ε=0.1)Standard CNN~85%~30%Adversarially Trained CNN~80%~55%

🛠️ Tech Stack
LibraryVersionPurposePyTorch2.0+Deep learning frameworkTorchvision0.15+CIFAR-10 dataset & transformsMatplotlib3.7+VisualizationNumPy1.24+Numerical computationtqdm4.65+Progress bars

📚 References

Goodfellow, I. et al. (2014). Explaining and Harnessing Adversarial Examples. arXiv:1412.6572
Madry, A. et al. (2017). Towards Deep Learning Models Resistant to Adversarial Attacks. arXiv:1706.06083


👤 Author
YounJungie

GitHub: @Jung1eBear


📄 License
This project is licensed under the MIT License — see the LICENSE file for details.
