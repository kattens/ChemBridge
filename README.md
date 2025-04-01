### **ChemBridge: Structure-Guided Drug Repurposing Pipeline for Malaria**

#### **Project Overview**

The goal of this project is to explore drug repurposing opportunities against **malaria (taxonomy ID 5833)** by leveraging existing drug-target interaction data and protein structural information. While previous research has focused heavily on **deep learning-based screening of millions of compounds to predict which ones might be active against malaria**, our approach aims to move beyond prediction and towards **understanding the mechanism of action** of these compounds.

In other words, prior studies answered the question:
> *Which molecules are active?*  
We are focused on answering:
> *How do these molecules work, and can they also work against malaria targets?*

This transition from **AI-based compound screening** to **mechanism-based target identification and structural analysis** is a critical next step in narrowing down potential candidates and reducing experimental search space.

---

### 🔬 **Project Strategy**

We start with a dataset of known drugs, including their **PubChem IDs** and other related information. The pipeline proceeds in a structured, step-by-step manner:

#### **1. Drug Target Information Extraction**
The first step is to identify the **protein targets** that these drugs are known to interact with. For this, we:
- Query **PubChem** for each drug to extract:
  - Biological test results
  - Interaction and pathway data
- Parse the results to build a clean and structured mapping between **PubChem IDs** and their associated **protein targets**.

This step is crucial to transform scattered chemical and biological data into usable, organized information — effectively forming the "bridge" in **ChemBridge**.

---

#### **2. Structural Data Retrieval for Targets**
Next, we check whether structural information is available for these identified targets:
- Search the **RCSB PDB** database for experimentally determined **PDB structures** corresponding to each target protein.
- Filter and retain only the targets with reliable structural data.

Having structural information allows us to go beyond statistical predictions and focus on concrete molecular interactions.

---

#### **3. Homology Search Against Malaria Proteins**
Once we have the PDB structures of the known targets:
- Perform a **BLASTp search** of these target sequences against proteins in malaria organisms (**taxonomy 5833**).
- Limit the search to malaria proteins with available **experimental PDB structures** to maintain structural reliability.
  
The objective here is to identify **structurally similar malaria proteins** that may share conserved binding sites with the known drug targets.

---

#### **4. Target-Malaria Protein Mapping**
For every successful match, we will establish a mapping between:
- The **drug**
- Its **known target protein** (with known interaction site)
- A **similar malaria protein** (with structural data)

This mapping provides a strong basis to hypothesize that the drug may also bind to the malaria protein at a structurally conserved site.

---

#### **5. Binding Interaction Modeling**
With the drug-target-malaria mapping in place:
- Conduct structural analysis and **binding prediction studies** to evaluate potential interactions between the drug and the malaria protein.
- This may include:
  - Docking simulations
  - Binding affinity scoring
  - Further computational validation

---

### 🚀 **Beyond the Core Pipeline**
There are additional steps and challenges we plan to address:
- **Filling Missing Structural Data:**  
  For targets or malaria proteins without available experimental structures, we will utilize **AlphaFold models** as an alternative.
  
- **Advanced Binding Site Analysis:**  
  Using interaction site data from known targets to guide and refine binding predictions for malaria proteins.

---

### 📌 **Summary & Significance**
In summary, this project complements and extends prior deep learning-based molecule screening efforts by focusing on the **mechanistic, structure-guided discovery process**. Instead of only predicting compound activity, we aim to understand and validate the **binding mechanism** of known drugs against potential malaria targets. This will ultimately help reduce the search space for experimental studies and accelerate the identification of viable drug candidates against malaria.
