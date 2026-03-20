# 🧪 Replication Package – AIWARE 2026

## 🔐 Kubernetes Misconfigurations in the Wild  
### Taxonomy, Evolution, and Automated Repair with Large Language Models

---

## 📖 Overview

This repository provides the **official replication package** for the AIWARE 2026 paper:

> *Kubernetes Misconfigurations in the Wild: Taxonomy, Evolution, and Automated Repair with Large Language Models*

The package is designed to ensure **transparency, reproducibility, and extensibility**. It includes all necessary artifacts to reproduce the results associated with the following research questions:

- **RQ1** — Taxonomy construction of Kubernetes misconfigurations  
- **RQ2** — Severity analysis across object types and categories  
- **RQ3** — Evolution of misconfigurations across project maturity  
- **RQ4** — LLM-based automated correction and schema-guided validation  

---

## 🗂️ Repository Structure
├── 📁 data/ # Datasets used across all research questions
├── 📁 taxonomy/ # Taxonomy definitions and mappings
├── 📁 scripts/ # Data collection and preprocessing pipelines
├── 📁 experiments/ # LLM prompts, configurations, and outputs
├── 📁 kubecurity/ # Schema-guided correction framework
├── 📁 results/ # Aggregated results and evaluation logs


---

## 🔁 Reproducing the Results

### ⚙️ 1. Data Preparation
- Use datasets available in `data/`  
- Or regenerate them using provided scripts:
  - Stack Overflow extraction (**RQ1**)  
  - GitHub Kubernetes configurations (**RQ2, RQ4**)  
  - Helm charts (**RQ3**)  

---

### 🧠 2. Taxonomy Construction (RQ1)
- Execute BERTopic pipeline from `scripts/`  
- Reproduce hierarchical clustering and taxonomy generation  

---

### 📊 3. Severity Analysis (RQ2)
- Run misconfiguration detection tools:
  - Datree  
  - Snyk  
  - KubeScore  
- Apply normalization and taxonomy mapping  

---

### 🔄 4. Evolution Analysis (RQ3)
- Compare incubator vs stable Helm charts  
- Compute:
  - Correction rates  
  - Emerged misconfigurations  

---

### 🤖 5. LLM-Based Correction (RQ4)
- Use prompt templates from `experiments/`  
- Run the four experimental configurations  
- Evaluate outputs using:
  - Kubernetes schema validation  
  - Detection tools  

#### 🛡️ Optional: Kubecurity Integration
Enable **Kubecurity** to enforce schema compliance and significantly improve correction accuracy (Experiment 4).

---

## ⚙️ Requirements

- 🐍 Python ≥ 3.10  
- 🔑 API access:
  - Stack Exchange API  
  - GitHub API  
- ☸️ Kubernetes validation tools  
- 🔍 Detection tools:
  - Datree  
  - Snyk  
  - KubeScore  

**Optional:**
- ⚡ GPU for large-scale experiments  
- 🤖 Access to LLM APIs or local models  

---

## 🔬 Reproducibility Statement

All results reported in the paper can be reproduced using this package.

We provide:
- ✅ Intermediate outputs  
- ✅ Evaluation logs  
- ✅ Full processing pipelines  

This ensures:
- **Traceability**  
- **Deterministic evaluation**  
- **Independent verification**  

---

## 🚀 Extensibility

This package is designed to support future research. It can be extended to:

- Integrate newer or alternative LLMs  
- Extend the taxonomy with additional categories  
- Incorporate new detection tools  
- Apply the methodology to other configuration systems  

---

## 📚 Citation

If you use this repository, please cite:

```bibtex
@inproceedings{ghorab2026aiware,
  title={Kubernetes Misconfigurations in the Wild: Taxonomy, Evolution, and Automated Repair with Large Language Models},
  author={Ghorab, Mostafa Anouar and Abdel Latif, Ahmad and Saied, Mohamed Aymen},
  booktitle={AIWARE 2026},
  year={2026}
}

## 📬 Contact

For questions, issues, or reproducibility concerns, please open an issue in this repository.

## 📝 License

This project is released for academic and research purposes.
