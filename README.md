# Chest X-Ray Classification with Deep Learning

This project provides an end-to-end deep learning pipeline for automated classification of chest X-ray images, distinguishing between "NORMAL" and "PNEUMONIA" cases. It covers data ingestion, preprocessing, model training, evaluation, and deployment as a scalable inference service.

---

## 📂 Dataset

- **Source:** [Chest X-Ray Images (Pneumonia)](https://drive.google.com/file/d/1pfIAlurfeqFTbirUZ5v_vapIoGPgRiXY/view?usp=sharing)
- The dataset contains labeled chest X-ray images for both normal and pneumonia cases.

---

## 🚀 Features

- **Data Ingestion:** Automated download and organization from cloud storage (AWS S3 supported).
- **Preprocessing & Augmentation:** Robust image transformations for improved generalization.
- **Custom CNN Model:** Tailored convolutional neural network for binary image classification.
- **Training & Evaluation:** Modular pipeline with logging and metrics tracking.
- **Deployment:** Model packaging and deployment using BentoML, Docker, and AWS ECR.
- **Reproducibility:** Configuration-driven workflow for easy reruns and adaptation.

---

## 🛠️ Tech Stack

- Python 3.8+
- PyTorch & Torchvision
- AWS S3 & AWS CLI
- BentoML
- Docker
- Jupyter Notebook (for experimentation)
- tqdm, matplotlib, numpy, opencv

---

## 🏗️ Project Structure

```
deeplearningproject
├── artifacts
│   ├── model
│   └── processed
├── bentofile.yaml
├── README.md
├── requirements.txt
├── src
│   ├── __init__.py
│   ├── config
│   │   ├── __init__.py
│   │   └── config.py
│   ├── constants.py
│   ├── data
│   │   ├── __init__.py
│   │   ├── download.py
│   │   └── preprocess.py
│   ├── logs
│   │   └── training.log
│   ├── model
│   │   ├── __init__.py
│   │   ├── cnn.py
│   │   └── train.py
│   ├── output
│   │   ├── predictions.csv
│   │   └── metrics
│   └── utils
│       ├── __init__.py
│       └── helpers.py
└── train.py
```

---

## 📖 Usage

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/chest-xray-classification.git
   cd chest-xray-classification
   ```

2. **Set up the environment**

   ```bash
   conda create -n lungs python=3.8 -y
   conda activate lungs
   pip install -r requirements.txt
   ```

3. **Configure AWS CLI**

   Follow the [AWS CLI installation guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) to install and configure the AWS CLI with your credentials.

4. **Run the pipeline**

   ```bash
   python src/train.py
   ```

---

## 📦 BentoML Integration

This project is integrated with BentoML for model serving. To build and run the BentoML service, execute the following commands:

```bash
# Build the BentoML model server
bentoml build

# Run the BentoML model server locally
bentoml serve <ModelName>:latest
```

For more details on using BentoML, refer to the [BentoML documentation](https://docs.bentoml.org/en/latest/).

---

## 📝 Notes

- Ensure that you have the necessary permissions and configurations set up in your AWS account for S3 access.
- Monitor the `logs/training.log` file for training progress and metrics.
- The trained model and processed artifacts will be saved in the `artifacts` directory.

---

## 📞 Contact

For any inquiries or issues, please open an issue on the GitHub repository or contact the project maintainer.

---

## 🔄 Acknowledgements

- [PyTorch](https://pytorch.org/) - The deep learning framework used.
- [BentoML](https://docs.bentoml.org/en/latest/) - For model serving and deployment.
- [AWS](https://aws.amazon.com/) - For cloud storage and computing resources.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---