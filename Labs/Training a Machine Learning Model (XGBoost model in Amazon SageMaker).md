# Training a Machine Learning Model (XGBoost model in Amazon SageMaker)

**Primary Domain:** Data Science & Machine Learning


**Key Concepts:** Data Partitioning, XGBoost Algorithm, Amazon SageMaker AI

---

### OVERVIEW
In this lab, I continued exploring the biomechanical vertebral column dataset to build a predictive model. I implemented a standard machine learning workflow by splitting data into training, validation, and testing subsets, followed by training an XGBoost model using Amazon SageMaker.

### CORE MILESTONES

#### 1. Dataset Preparation & Partitioning
* **Data Splitting:** Divided the biomechanical dataset into three distinct sets: Training (to teach the model), Validation (to tune hyperparameters), and Testing (for final unbiased evaluation).
* **Objective:** Ensured model generalizability and prevented overfitting by isolating the test data from the training process.

#### 2. Environment Configuration
* **Resource Assessment:** Accessed the Amazon SageMaker AI dashboard and deployed a pre-provisioned notebook instance named `MyNotebook`.
* **IDE Setup:** Launched JupyterLab and initialized the development environment using the `conda_python3` kernel for optimal compatibility.

#### 3. Model Training with XGBoost
* **Algorithm Implementation:** Utilized the XGBoost algorithm, a high-performance gradient-boosted decision tree method, to process the vertebral column data.
* **SageMaker Integration:** Executed the training job directly within the SageMaker platform, leveraging cloud-native machine learning tools.

### CONCLUSION
I successfully validated the machine learning pipeline by confirming the model's ability to classify biomechanical data. This lab demonstrated proficiency in managing the full ML lifecycle on AWS, from data engineering to model training.
