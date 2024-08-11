


# 🧠 LoRA Fine-tuning for ResNet and VGG on MNIST

![Python](https://img.shields.io/badge/Python-3.7%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-1.7%2B-orange)
![License](https://img.shields.io/badge/license-MIT-green)

This project demonstrates the implementation of Low-Rank Adaptation (LoRA) for fine-tuning ResNet and VGG models on the MNIST dataset. LoRA is a parameter-efficient fine-tuning technique that adds trainable rank decomposition matrices to existing weights, enabling adaptation with significantly fewer parameters.

## 🌟 Features

- Custom implementation of ResNet and VGG architectures
- LoRA parameterization for convolutional and linear layers
- Fine-tuning on specific MNIST digits
- Parameter counting before and after LoRA addition
- Comparison of model performance with and without LoRA

## 🛠️ Requirements

- Python 3.7+
- PyTorch 1.7+
- torchvision
- matplotlib
- tqdm

## 🚀 Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Sarim-MBZUAI/LoRA-implementation-from-scratch.git
   cd lora-mnist-finetuning
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## 📊 Usage

1. Train the base ResNet or VGG model on MNIST


2. Add LoRA and fine-tune on specific digits


3. Evaluate the model


## 📈 Results

We performed experiments to evaluate the effectiveness of LoRA fine-tuning on specific digits (6, 3, and 8) of the MNIST dataset. Here are the key findings:

### Base Model Performance (LoRA disabled)

| Metric | Value |
|--------|-------|
| Accuracy | 94.3% |

#### Error Distribution

| Digit | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|-------|---|---|---|---|---|---|---|---|---|---|
| Errors | 21 | 10 | 73 | 143 | 34 | 25 | 36 | 69 | 70 | 93 |

### LoRA Fine-tuned Model Performance (LoRA enabled)

| Metric | Value |
|--------|-------|
| Accuracy | 61.9% |

#### Error Distribution

| Digit | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|-------|---|---|---|---|---|---|---|---|---|---|
| Errors | 99 | 845 | 881 | 4 | 537 | 305 | 7 | 567 | 25 | 542 |

### Analysis

1. The base model achieved a high accuracy of 94.3% on the entire MNIST dataset.

2. After fine-tuning with LoRA on digits 6, 3, and 8:
   - The overall accuracy decreased to 61.9%.
   - However, the model significantly improved its performance on the targeted digits:
     - Errors for digit 3 reduced from 143 to 4
     - Errors for digit 6 reduced from 36 to 7
     - Errors for digit 8 reduced from 70 to 25

3. The trade-off is a decrease in performance on other digits, particularly 1, 2, 4, 7, and 9.

These results demonstrate that LoRA fine-tuning can effectively adapt the model to perform better on specific classes. However, this comes at the cost of reduced performance on non-targeted classes. This approach could be particularly useful in scenarios where improving performance on specific classes is more critical than maintaining overall accuracy.

## 🔮 Future Work

- Balance the fine-tuning process to maintain better overall performance
- Investigate the impact of different LoRA ranks and learning rates
- Apply this technique to more complex datasets and model architectures

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- [Umar Jamil Tutorial on Lora](https://www.youtube.com/watch?v=PXWYUTMt-AU)

- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685)
- [PyTorch](https://pytorch.org/)
- [MNIST Dataset](http://yann.lecun.com/exdb/mnist/)