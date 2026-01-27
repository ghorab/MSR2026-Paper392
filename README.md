# Replication Package
## Towards Secure and Reliable Kubernetes Configurations

This replication package accompanies the paper:

> **Towards Secure and Reliable Kubernetes Configurations: A Taxonomy of Misconfigurations and Automated Correction with Large Language Models**

submitted to **The ACM Joint European Software Engineering Conference and Symposium on the Foundations of Software Engineering (FSE 2026)**.

This replication package is distributed as a **fully self-contained virtual machine image**.  
**All datasets, source code, executable artifacts, tools, and dependencies are already included inside the image.**  
No external installation or environment configuration is required.

---

## 🎥 Video Demonstration

A video demonstrating the tool, execution environment, and replication workflow is available at:

* https://youtu.be/PzxQsXRym3Y

---

## 📦 Contents (Inside the VM Image)

The virtual machine image contains all components required to reproduce the experiments presented in the paper.

### 📊 Taxonomy
* Complete taxonomy of Kubernetes misconfigurations  
* Five main categories and twenty-one subcategories  
* Severity levels normalized into **Low / Medium / High**

### 💻 Source Code & Executable
* Full source code of the detection and correction system  
* Ready-to-run executable **JAR**  
* Configuration files and scripts used in the experiments

### 🔍 Misconfiguration Detection Tools
The following tools are pre-installed and pre-configured inside the VM:
* **Datree**
* **Kube-Score**
* **Snyk**

Detection results are aggregated, normalized, and deduplicated automatically.

### 🤖 LLM-Based Correction
* Prompt templates corresponding to multiple correction settings:
  * Configuration only  
  * Configuration + misconfiguration type  
  * Configuration + type + short description  
* Support for multiple Large Language Models

---

## 🛡️ Kubecurity: Schema-Guided Kubernetes Configuration Correction

Kubecurity is a schema-guided, rule-based correction framework integrated into the replication package.

While Large Language Models are effective at reasoning about Kubernetes misconfigurations, their outputs may violate structural constraints, such as missing required fields, incorrect nesting, or invalid data types. Kubecurity enforces **deterministic compliance with official Kubernetes JSON schemas**, ensuring that corrected configurations are syntactically valid and parsable.

### Design Principles
* **Schema Awareness** – validation against official Kubernetes JSON schemas  
* **Deterministic Correction** – reproducible, rule-based fixes  
* **LLM Complementarity** – reinforces LLM reasoning without replacing it  
* **Minimal Intervention** – only schema-violating elements are modified  

### Correction Workflow
* **Pre-LLM Validation**
  * Repairs deterministic structural issues  
  * Normalizes object hierarchy and indentation  
* **Post-LLM Validation**
  * Re-validates LLM-generated configurations  
  * Corrects residual schema violations  

### Correction Capabilities
* Insert missing mandatory fields  
* Resolve type mismatches (e.g., string vs integer)  
* Reconstruct invalid configuration trees  
* Remove obsolete or invalid sections  
* Enforce canonical Kubernetes object structure  

A configuration is considered **successfully corrected** only if:
* It passes Kubernetes JSON schema validation, and  
* It is no longer flagged by Datree, Kube-Score, or Snyk  

---

## 🔁 Replication Workflow

* Load Kubernetes configuration files  
* Detect misconfigurations using Datree, Kube-Score, and Snyk  
* Map detections to taxonomy categories and severity levels  
* Apply LLM-based correction  
* Enforce deterministic schema compliance using Kubecurity  

---

## ▶️ How to Run

* Launch the provided OVH virtual machine image  
* Open a terminal inside the VM  
* Run the tool:
  ```bash
  java -jar KubeCurty.jar


## ⚠️ Notes

Some functionalities may require user-provided credentials (e.g., API keys).

---

## 📄 Citation

If you use this replication package, please cite the corresponding **FSE 2026** paper.  
(Citation details will be added upon acceptance.)

---

## 📜 License

MIT License

---

## ⚠️ Work in Progress

This replication package will be extended with:
* Additional datasets
* New Kubecurity versions
* Fully automated experiment pipelines
