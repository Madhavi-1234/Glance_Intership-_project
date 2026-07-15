# 👗 Fashion Style Classification using CLIP & User Profile Builder

An AI-powered fashion understanding system that classifies clothing images into different fashion styles using **OpenAI CLIP**, combining **zero-shot vision-language learning** with a supervised deep learning classifier.

The project includes a complete pipeline from dataset exploration, style label creation, CLIP-based prediction, model training, evaluation, and a user profile builder component for personalized fashion understanding.

---

## 🚀 Project Overview

Fashion recommendation systems require understanding more than just clothing categories. They need to identify the **overall style identity** of an outfit, such as casual, formal, sporty, or streetwear.

This project builds a fashion style classification pipeline that:

* Analyzes fashion product images
* Creates meaningful style labels using product metadata
* Uses CLIP for zero-shot style prediction
* Trains a hybrid CLIP-based classifier
* Generates structured user style profiles for personalization

---

# ✨ Key Features

✅ Fashion image style classification
✅ CLIP-based zero-shot prediction
✅ Multiple text prompts per style category
✅ Custom fashion style label mapping
✅ Exploratory Data Analysis (EDA)
✅ Dataset balancing for improved learning
✅ Transfer learning using CLIP Vision Encoder
✅ PyTorch training pipeline
✅ Model evaluation and testing
✅ User profile builder for future personalization

---

# 🧠 Fashion Style Categories

The model predicts the following fashion styles:

* Casual Everyday
* Formal Office
* Sporty Athleisure
* Streetwear
* Bohemian
* Elegant Party

---

# 🏗️ System Workflow

```
Fashion Dataset
        |
        ↓
Dataset Exploration & Cleaning
        |
        ↓
Style Label Mapping using Metadata
        |
        ↓
Class Balancing
        |
        ↓
CLIP Zero-Shot Prediction
        |
        ↓
Hybrid CLIP Classifier Training
        |
        ↓
Style Prediction
        |
        ↓
User Profile Builder
```

---

# 🛠️ Tech Stack

| Category                | Technology                      |
| ----------------------- | ------------------------------- |
| Programming Language    | Python                          |
| Deep Learning Framework | PyTorch                         |
| Vision Language Model   | OpenAI CLIP (ViT-Large-Patch14) |
| Dataset Platform        | Hugging Face Datasets           |
| Data Processing         | Pandas, NumPy                   |
| Visualization           | Matplotlib                      |
| Image Processing        | Pillow                          |
| Machine Learning        | Scikit-learn                    |

---

# 📂 Dataset

Dataset used:

**ashraq/fashion-product-images-small (Hugging Face)**

The dataset contains:

* Fashion product images
* Product names
* Article types
* Subcategories
* Usage information
* Other product metadata

Since the original dataset does not contain direct fashion style labels, a custom style mapping pipeline was created.

---

# 🏷️ Style Label Mapping

Fashion styles were generated using text-based keyword matching from product metadata.

The mapping uses:

* `productDisplayName`
* `articleType`
* `subCategory`
* `usage`

Example:

| Product Information       | Assigned Style    |
| ------------------------- | ----------------- |
| Blazer, suit, formal wear | Formal Office     |
| Hoodie, sneakers, cargo   | Streetwear        |
| Gym wear, activewear      | Sporty Athleisure |
| Party dress, gown         | Elegant Party     |
| Jeans, casual shirt       | Casual Everyday   |

This approach creates meaningful labels from an unlabeled fashion dataset.

---

# 📊 Exploratory Data Analysis

Before training, extensive EDA was performed:

* Dataset size analysis
* Metadata inspection
* Class distribution analysis
* Sample image visualization
* Image dimension analysis

The original dataset showed strong class imbalance, where some styles had significantly more samples than others.

---

# ⚖️ Data Balancing

To reduce bias toward majority classes, controlled undersampling was applied.

Process:

* Majority classes were limited to a fixed number of samples.
* Smaller classes were preserved.
* Balanced data was used for training.

This helped the model learn different fashion styles instead of over-predicting the dominant class.

---

# 🤖 Zero-Shot Prediction using CLIP

Before supervised training, CLIP was used for zero-shot classification.

CLIP understands images and text jointly because it was pretrained on large-scale image-text pairs.

The prediction process:

```
Input Image
     |
     ↓
CLIP Image Encoder
     |
     ↓
Image Embedding

Text Prompts
     |
     ↓
CLIP Text Encoder
     |
     ↓
Text Embeddings

     ↓

Cosine Similarity

     ↓

Fashion Style Prediction
```

Multiple prompts were created for each style category to improve recognition.

Example:

Instead of only:

```
"casual outfit"
```

multiple descriptions were used:

```
"casual everyday outfit with jeans and t-shirt"

"relaxed weekend outfit with denim jacket"
```

---

# 🧠 Hybrid CLIP Classifier

For improved performance, a supervised classifier was trained on top of CLIP visual features.

Architecture:

```
Image
 |
 ↓
CLIP Vision Encoder
 |
 ↓
Visual Embedding
 |
 ↓
Classification Head
 |
 ↓
Fashion Style Class
```

The CLIP backbone provides strong visual representations, while the classifier learns fashion-specific patterns from the dataset.

---

# 📈 Model Performance

Final evaluation was performed using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

Example evaluation:

```
Test Accuracy: ~78.5%

Backbone:
CLIP ViT-Large-Patch14

Classes:
6 Fashion Styles
```

---

# 👤 User Profile Builder

A user profile builder component was developed to represent user fashion preferences.

The goal is to create structured user style information that can support:

* Personalized recommendations
* User preference understanding
* Similar style discovery
* Future recommendation systems

The profile builder can use predicted fashion styles and extracted style representations to create user-level fashion profiles.

---

# 📁 Project Structure

```
Fashion-Style-Classifier/

│
├── notebooks/
│   └── fashion_style_classifier.ipynb
│
├── models/
│   └── trained_model_files
│
├── outputs/
│   ├── predictions
│   ├── evaluation_results
│   └── visualizations
│
├── README.md
│
└── requirements.txt
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone <repository-url>
```

Navigate to the project:

```bash
cd Fashion-Style-Classifier
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# ▶️ Running the Project

The complete pipeline includes:

### 1. Dataset Loading

Load fashion images and metadata.

### 2. Data Exploration

Analyze dataset quality and distribution.

### 3. Style Mapping

Generate fashion style labels.

### 4. CLIP Zero-Shot Prediction

Predict styles without training.

### 5. Model Training

Train the hybrid CLIP classifier.

### 6. Evaluation

Evaluate model performance on unseen images.

---
## Sample prediction outputs with the input image, predicted style, and generated description are included below for demonstration.( folder called Demo Outputs)

# 🔮 Future Improvements

Possible improvements:

* Collect more samples for minority styles
* Advanced data augmentation
* Multi-label fashion classification
* Outfit compatibility prediction
* Fashion recommendation engine
* Real-time API deployment
* Better user personalization using embeddings

---

# 📚 Learning Outcomes

This project provided practical experience with:

* Vision-Language Models
* CLIP architecture
* Zero-shot learning
* Transfer learning
* PyTorch training pipelines
* Dataset preprocessing
* Feature embeddings
* Image classification
* Fashion AI applications

---

# 🙌 Acknowledgements

* OpenAI CLIP
* Hugging Face
* PyTorch
* Scikit-learn
* Fashion Product Images Dataset

---

⭐ If you find this project useful, consider starring the repository.
