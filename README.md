#ChemBridge: 

"Chem" → Chemistry, Compounds, Molecules
"Bridge" → Connecting and integrating information

This project acts like a bridge between:

    PubChem’s raw data

    and the user’s need for structured, clean, usable information

We’re bridging the gap between messy, scattered chemical data and a usable, automated pipeline.


# 🔬 Drug Target Identification

## 🎯 Project Goal

This project aims to identify the **targets** of small drug molecules using a list of **PubChem IDs**. To achieve this, we extract relevant biological test data from PubChem CSV files, specifically focusing on the **"target names"** column.

## 🛠️ Overall Pipeline

1. **📌 Generate Initial Data**
   - Create a list of **PubChem IDs** and their corresponding **targets** from the initial dataset.
   - Construct a dictionary mapping each **PubChem ID** to its associated targets.

2. **📥 Download Biological Test Results**
   - Use the **`pubchempy`** library to fetch biological test results as **CSV files**.
   - Rename each file to match its corresponding **PubChem ID**.

3. **🔍 Extract Target Information**
   - Parse the downloaded files to generate a structured dictionary.
   - Each **PubChem ID** (file name) maps to a list of extracted **target names** from the **"target names"** column.

## 🚀 Next Phase

Once the targets (proteins interacting with the molecules) are identified, the next step is retrieving their **amino acid sequences** from **UniProt** (preferred) or **RCSB PDB** (alternative, though more complex).

## 🔬 Follow-Up Step

Using these sequences, we will perform a **BLAST search** 🔎 against **malaria orthologs** to identify potential matches.
