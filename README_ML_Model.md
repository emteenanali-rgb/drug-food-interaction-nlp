# 💊 Drug-Food Interaction ML Model

Built on **DrugBank 6.0** data. Predicts drug-food interactions using TF-IDF + Logistic Regression with direct database lookup.

## 🚀 How to Run

1. Open `drug_nlp_clean.ipynb` in Google Colab  
2. Upload `drug_food_data.csv` when Cell 2 prompts you  
3. Run all cells (Runtime → Run all)

## 📊 Model Details

- **Algorithm:** TF-IDF (1-2 ngrams) + Logistic Regression (class_weight=balanced)
- **Data:** 2,500+ drug-food interaction records from DrugBank 6.0 + 60 verified no-interaction examples
- **Task:** Binary classification — YES/NO interaction

## 🔍 Prediction Logic

```
1. Look up drug in database
   ├── Has interactions → check if food word is mentioned → YES or NO
   └── Not in DB → use ML model

2. Generic words filtered out (food, any, meal, diet...)
   to prevent false positives
```

## ✅ Test Results

| Drug | Food Query | Result |
|------|-----------|--------|
| Warfarin | spinach, kale, vitamin K | YES ⚠️ |
| Metformin | alcohol | YES ⚠️ |
| Simvastatin | grapefruit | YES ⚠️ |
| Atorvastatin | orange | NO ✅ |
| Cetirizine | any food | NO ✅ |
| Cetirizine | alcohol | YES ⚠️ |

## 📁 Repository Files

| File | Description |
|------|-------------|
| `drug_nlp_clean.ipynb` | Main Colab notebook with all steps |
| `drug_food_data.csv` | Processed DrugBank 6.0 dataset |

## 📦 Requirements

```
scikit-learn pandas numpy matplotlib seaborn
```

---
*Data: DrugBank 6.0 — Knox C, et al. Nucleic Acids Res. 2024*
