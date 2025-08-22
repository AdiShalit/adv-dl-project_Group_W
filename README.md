# DL_2_Project – Group W

This repository contains our work for the Advanced Deep Learning project.  
The project is organized into **9 Jupyter notebooks**, each representing a step in our workflow.  
Below is the explanation of the process and how to use the notebooks.

---

## 📂 Project Structure

### 1. **Group_W_EDA_Data_Processing.ipynb**
- Purpose: Exploratory Data Analysis (EDA) and data preprocessing.  
- Output: A `cleaned_csv` file used for all training stages.  
⚠️ **Important:** Since translation to English is model-based, re-running this notebook may produce a different CSV.  
👉 Please use the **existing CSV in the repository** for consistency in the training phase.
['Corona_NLP_train_cleaned_translated.csv','Corona_NLP_test_cleaned_translated.csv']

---

### 2. **Group_W_Model_1_EX4_Roberta_Base.ipynb**
- First training notebook (RoBERTa, Exercise 4).  
- Outputs:
  - Best model → saved in `adv_dl_models_final/`  
  - Quantization & pruning results → saved in compression notebooks  
  - Trial checkpoints during HP tuning → saved in `adv_dl_models/`  
- Usage: You can use the **Table of Contents** → “Load Best Model & Test” to directly evaluate the final model.

---

### 3. **Group_W_Model_1_EX5_Roberta_Base.ipynb**
- Second training notebook (RoBERTa, Exercise 5).  
- Outputs:
  - Best models saved in `adv_dl_models_final2_best/`.  
- Usage: As with EX4, you can use the **ToC** to quickly load the trained model and run evaluation.
  (******)Important note- This model was trained with label mapping of ["Neutral", "Positive", "Extremely Negative", "Negative", "Extremely Positive"] as [0,1,2,3,4]- This is implemted in code.(******)

---

### 4. **Group_W_Model_2_Training_mdeberta_v3_Base.ipynb**
- Training notebook for **mDeBERTa-v3-base**, includes both **EX4** and **EX5** methods.  
- Outputs:
  - EX4 → best model in `ex_4_model/` + checkpoints.  
  - EX5 → models saved in `hf_ckpts/`.  
- Usage: Table of Contents allows direct navigation to training, loading best model, or evaluation.

---

### 5. **Group_W_Models_Ensembling.ipynb**
- This notebook combines predictions from multiple trained models to improve performance.  
- Required model files (must be downloaded from Drive):
  - `adv_dl_models_final/roberta_base_best_manual.pt`  
  - `adv_dl_models_final2_best/roberta_base_best_set2.pt`  
  - `microsoft__mdeberta-v3-base_ex5_trainer-try__final_20250817_104013/best_model`  
  - `microsoft__mdeberta-v3-base_full_ex_4_20250817_133620/`  

👉 Place these files in the same directory structure as expected by the notebook before running.

---

### 6–9. **Compression Notebooks**
- **Group_W_Compression_ex4_roberta_base.ipynb**  
- **Group_W_Compression_ex5_roberta_base.ipynb**  
- **Group_W_Compression_ex4_mDberta_v3_base.ipynb**  
- **Group_W_Compression_ex5_mDberta_v3_base.ipynb**

Each notebook corresponds to a **different model and training method** (RoBERTa vs. mDeBERTa, EX4 vs. EX5).  

- These notebooks implement **compression (quantization & pruning)** and **Knowledge Distillation (KD)**.  
- Best models are loaded automatically at the start.  
- For KD with hyperparameter tuning:  
  - Use the **ToC** to quickly jump to “Load Best Student HP & Test”.

---

## ⚠️ Checkpoints & Weights

Due to Git size limitations, **we could not push checkpoints to GitHub**.  
All checkpoints and weights are stored in Google Drive.  
You must download them locally and place them alongside the notebooks to run training/evaluation properly.  

🔗 **Drive Link (TAU account required):**  
[Project Models & Checkpoints](https://drive.google.com/drive/folders/1cPD83Tt7OirelryPsy51WytqkCrPuX24?usp=sharing)

---

## 🔑 Usage Notes
- Always **load the dataframe (`df`) first** in training notebooks.  
- Use the **cleaned CSV provided** rather than re-running preprocessing.  
- Use **Table of Contents** shortcuts for faster navigation (loading best models, testing, skipping training).  
