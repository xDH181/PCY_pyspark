# 🛒 Frequent Itemset Mining with PCY Algorithm (PySpark)

## 📌 Objective

This project implements the **PCY (Park-Chen-Yu)** algorithm to efficiently find **frequent itemsets** from transaction data using **Apache Spark** and **PySpark**. The goal is to identify commonly purchased item combinations (e.g., in a market basket analysis) while optimizing memory use with hashing techniques.

---

## ⚙️ Technologies & Tools

- **PySpark** (Apache Spark with Python)
- **Google Colab** (Notebook execution)
- **RDDs & DataFrames** for scalable distributed processing
- Custom classes for:
  - `HashBucket`: Hash-based frequency counting
  - `PCY`: Main algorithm for frequent itemset mining

---

## 🗂️ Dataset

- Input file: `baskets.csv`
- Fields include: `Member_number`, `Date`, `itemDescription`
- Preprocessing includes:
  - Grouping by `Member_number` and `Date` to form baskets
  - Converting grouped items into list-based transaction format

---

## 🚀 Algorithm Overview

### Step 1: First Pass
- Count the frequency of individual items
- Hash item pairs into buckets using a custom hash function

### Step 2: Candidate Filtering
- Use bucket counts to create a bitmap for frequent pairs
- Generate candidate pairs that meet the support threshold and have valid hashed buckets

### Step 3: Association Rules (Optional)
- Generate strong association rules based on **minimum confidence threshold**

---

## 🧠 Key Classes

### `HashBucket`
- Stores hashed pair frequencies in buckets
- Optimizes memory by avoiding pairwise storage

### `PCY`
- Main class to run the PCY algorithm with:
  - `first_pass()`
  - `generate_candidates()`
  - `run()` for full pipeline

---

## 🧪 Parameters

- `min_support`: Minimum count for an item or pair to be considered frequent
- `num_buckets`: Number of hash buckets for pair hashing
- `min_confidence`: Minimum confidence for generating association rules (if applied)

---

## 💻 How to Run

1. Upload the notebook to **Google Colab**
2. Mount Google Drive and load `baskets.csv`
3. Adjust `min_support`, `num_buckets`, and `min_confidence` as needed
4. Run all cells to perform frequent itemset mining

---

## 📎 Project Structure

```
📦 Frequent Itemset Mining
├── Frequent_item_PCY.ipynb     # Main notebook implementing PCY algorithm
├── baskets.csv                 # Input dataset (assumed to be in Google Drive)
├── README.md                   # Project overview
```

---

## 📬 Contact

For questions or suggestions, feel free to open an issue or contact the project maintainer.

Email : haidangforworks@gmail.com