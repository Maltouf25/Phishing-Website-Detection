# 🛡️ Phishing Website Detection using Machine Learning

## Objective
Phishing websites are a common social engineering threat that mimic trusted URLs and webpages.  
The goal of this project is to **train machine learning models** on phishing and legitimate website data in order to detect phishing attempts automatically.  

A dataset of URLs was collected, features were extracted from both address bar and webpage content, and multiple machine learning models were trained and compared.

---

## Data Collection
- **Phishing URLs**: Collected from [PhishTank](https://www.phishtank.com/developer_info.php).  
  → 5000 random phishing URLs were selected.  
- **Legitimate URLs**: Collected from the [University of New Brunswick dataset](https://www.unb.ca/cic/datasets/url-2016.html).  
  → 5000 random benign URLs were selected.  

Total dataset size: **10,000 URLs** (balanced between phishing and legitimate).  
The datasets are stored in the `DataFiles/` folder of this repository.  

---

## Feature Extraction
From each URL, **17 features** were extracted in three categories:  
1. **Address Bar based features** (9 features)  
2. **Domain based features** (4 features)  
3. **HTML & JavaScript based features** (4 features)  

The extraction process is detailed in the notebook `URL Feature Extraction.ipynb`.  
The processed dataset is stored in `5.urldata.csv`.  

---

## Models and Training
- The dataset was split **80/20** → 8000 training samples, 2000 test samples.  
- Task type: **Supervised Classification** (Phishing = 1, Legitimate = 0).  

Models evaluated:  
- Decision Tree  
- Random Forest  
- Multilayer Perceptron (MLP)  
- XGBoost  
- Autoencoder Neural Network  
- Support Vector Machine (SVM)  

Implementation details are provided in `Phishing Website Detection_Models & Training.ipynb`.  

---

## Results
- The models were compared based on accuracy and test performance.  
- **XGBoost Classifier** achieved the highest performance with an accuracy of **86.4%**.  
- The trained model was saved as: `XGBoostClassifier.pickle.dat`.  