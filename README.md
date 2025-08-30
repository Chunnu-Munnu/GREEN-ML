Green ML Compression Suite 🌱
An open-source toolkit to make AI models lighter, faster, and more sustainable. Our mission is to democratize AI by making it efficient enough to run anywhere, for everyone.

The Problem: AI's Growing Carbon Footprint
Artificial Intelligence is a revolutionary technology, but it has a hidden cost. The current trend of building ever-larger models has led to an unsustainable demand for computational resources.

Massive Energy Consumption: Training a single large model can emit over 550 tons of CO₂.

High Operational Costs: Inference (daily usage) accounts for up to 90% of an AI model's lifetime energy costs, requiring vast, 24/7 data centers.

A Barrier to Innovation: The need for expensive hardware (often ₹25,00,000+ for a single high-end GPU) locks out innovators in startups, academia, and emerging markets like India.

Our Solution: A Toolkit for Sustainable AI
The Green ML Compression Suite is a practical, powerful, and easy-to-use Python library that directly tackles this problem. It provides an integrated pipeline to transform bloated, inefficient models into lean, green, and deployable assets.

Core Features
✅ Intelligent Pruning: Systematically removes redundant model components to reduce size and computation.

✅ Advanced Quantization: Converts models to efficient 8-bit integer formats with minimal accuracy loss using Quantization-Aware Training (QAT).

✅ The "Green Report Card": A unique feature that generates a clear report quantifying the improvements in model size, prediction speed, and estimated energy savings.

🚀 Getting Started
Installation
To get started, clone the repository and install the required dependencies.

# Clone the repository
git clone [https://github.com/GreenML-Suite/Core-Optimizer.git](https://github.com/GreenML-Suite/Core-Optimizer.git)
cd Core-Optimizer

# Install dependencies
pip install -r requirements.txt

Quickstart: Optimize Your First Model
Optimizing a model is designed to be simple. Here’s a quick example of how to take a standard PyTorch CNN model and make it "Green."

import torch
from torchvision.models import resnet18
from greenml.suite import GreenMLSuite
from greenml.reporter import report_model

# 1. Load your pre-trained model
model = resnet18(pretrained=True)
model.eval()

# 2. Profile the baseline model
print("--- Baseline Model ---")
report_model(model, input_shape=(1, 3, 224, 224))

# 3. Initialize the Green ML Suite with an optimization strategy
suite = GreenMLSuite(strategy=['prune', 'quantize'])

# 4. Run the optimization pipeline
# (Note: This would require a dataloader for retraining steps)
# green_model = suite.optimize(model, train_dataloader) 
# For this example, we'll use a placeholder for the optimized model
green_model = suite.quantize(suite.prune(model, amount=0.5)) # Simplified example

# 5. Report on the final, optimized model
print("\n--- Green Model ---")
report_model(green_model, input_shape=(1, 3, 224, 224))

🗺️ Project Roadmap
This project is actively developed. Our goal is to build the most comprehensive and user-friendly toolkit for sustainable AI.

[x] Core Pipeline: Pruning and Post-Training Quantization.

[ ] Advanced QAT: Implement full Quantization-Aware Training.

[ ] Knowledge Distillation: Add support for training smaller "student" models.

[ ] NLP Model Support: Create specialized pipelines for Transformers (e.g., BERT, T5).

[ ] Expanded "Green Report Card": Include estimated CO₂ and cloud cost savings.

🤝 How to Contribute
We believe in the power of open collaboration. This mission is bigger than one team, and we welcome contributions from the community.

Fork the repository and create your branch (git checkout -b feature/YourFeature).

Make your changes. Please adhere to the coding standards.

Submit a Pull Request with a clear description of your changes.

You can also contribute by:

Reporting bugs or suggesting new features in the Issues section.

Helping us improve the documentation.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.
