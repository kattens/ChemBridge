### **ChemBridge - A Drug Repurposing Pipeline for Malaria**

**Why "ChemBridge"?**  
The name reflects the purpose of the project:
- **"Chem"** → Chemistry, Compounds, Molecules
- **"Bridge"** → Connecting and integrating scattered chemical information

This project acts as a bridge between:
- **Raw, unstructured data from PubChem**
- And the user's need for **clean, structured, actionable information**

We aim to bridge the gap between messy chemical databases and a streamlined, automated pipeline to repurpose drugs against **malaria (taxonomy ID: 5833)**.

---

### 🎯 **Project Goal**

The main objective is to identify potential drug candidates for malaria by:
- Analyzing known drug-target interactions
- Finding structural homologs of these targets in malaria organisms
- Predicting possible binding sites based on these similarities
- Ultimately, reducing the search space for experimental validation

---

### 🚀 **Overall Workflow**

#### **1. Drug Dataset & Target Information Extraction**
We start with a dataset of **PubChem IDs** and associated metadata.
- We will use **PubChemPy** to retrieve:
  - Biological test results
  - Pathways and interaction data
- Specifically, we will parse **target names** from the **biological test CSV files**.
- A structured **dictionary** will be created, mapping each **PubChem ID** to its list of known targets.

This step converts scattered PubChem data into a structured and queryable format — the "bridge" of ChemBridge.

---

#### **2. Structural Data Retrieval**
For every identified target:
- Search **RCSB PDB** for available **experimental PDB structures**.
- Prioritize targets with high-quality structural data.
- Prepare a clean dataset of drug-target pairs with known 3D structures.

---

#### **3. Homology Search Against Malaria Proteins**
For each target PDB structure:
- Perform a **BLASTp search** against proteins from **Plasmodium species (taxonomy 5833)**.
- Focus first on matches with **experimental PDB structures**.
- Identify malaria proteins with significant sequence/structural similarity to known drug targets.

---

#### **4. Mapping & Binding Site Prediction**
For each valid match:
- Establish a triplet mapping:
  - **Drug name**
  - **Known target protein (with interaction site information)**
  - **Similar malaria protein (with structural data)**

This allows us to hypothesize that the drug may bind to the malaria protein at a similar site.

---

#### **5. Binding Modeling & Advanced Analysis**
With this mapping:
- Perform **docking simulations** and **binding affinity predictions**.
- Leverage known interaction sites to constrain the search space.
- Further analyze physicochemical and biological properties to evaluate efficacy.

---

### 🔄 **Future & Optional Steps**
- **Filling Structural Gaps:**  
  For proteins without experimental PDB data, we will use **AlphaFold models** to continue the analysis.
  
- **Advanced Binding Analysis:**  
  Incorporate more advanced binding site prediction techniques once preliminary results are established.

---

### ✅ **Summary**
The ChemBridge pipeline is an iterative, modular approach to drug repurposing:
1. **Data Collection & Cleaning** (PubChem, bioactivity parsing)
2. **Structural Mapping** (RCSB PDB)
3. **Homology Search** (BLAST against malaria proteins)
4. **Drug-Target-Pathogen Mapping**
5. **Binding Prediction & Further Analysis**
