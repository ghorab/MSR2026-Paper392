# Replication Package  
## Towards Secure and Reliable Kubernetes Configurations

This replication package accompanies the paper:

> **Towards Secure and Reliable Kubernetes Configurations: A Taxonomy of Misconfigurations and Automated Correction with Large Language Models**

submitted to **The 23rd International Conference on Mining Software Repositories (MSR 2026)**.

The package provides all datasets, tools, and scripts required to **replicate the empirical analyses, taxonomy construction, severity assessment, and LLM-based correction experiments** presented in the paper.

---

## 📦 Contents

This repository contains the following components:

### 📁 Datasets
- **Stack Overflow Dataset**  
  Curated Kubernetes-related posts (2015–2024) used to construct the misconfiguration taxonomy.
- **GitHub Kubernetes Manifests**  
  10,000 schema-validated Kubernetes YAML configuration files collected from public GitHub repositories.
- **Helm Charts Dataset**  
  Kubernetes configurations from incubator and stable Helm projects used to study misconfiguration evolution.

### 📊 Taxonomy & Mapping
- The complete **taxonomy of Kubernetes misconfigurations** (5 main categories, 21 subcategories).
- Mapping tables aligning Datree, Kube-Score, and Snyk rule identifiers with taxonomy categories.
- Severity normalization into **Low / Medium / High** levels.

### 🔍 Misconfiguration Detection
- Scripts to execute and aggregate results from:
  - **Datree**
  - **Kube-Score**
  - **Snyk**
- Deduplication and consolidation of overlapping detections across tools.

### 🤖 LLM-Based Correction
- Prompt templates corresponding to the three experimental settings:
  1. Configuration only  
  2. Configuration + misconfiguration type  
  3. Configuration + type + detailed description
- Evaluation scripts for:
  - GPT-3.5-Turbo  
  - Mistral-7B  
  - LLaMA-3.1-70B  
  - DeepSeek-R1  
  - Qwen-2.5-7B  

### 🛡️ Kubecurity
- **Kubecurity**, a schema-guided correction engine enforcing Kubernetes JSON schemas.
- Pre- and post-LLM validation to ensure syntactic correctness and structural compliance.

---

## 🔁 Replication Workflow

1. **Dataset Preparation**
   - Collect Kubernetes YAML files
   - Validate schemas using `kubeval`

2. **Misconfiguration Detection**
   - Run Datree, Kube-Score, and Snyk
   - Normalize severity and remove duplicate detections

3. **Taxonomy & Severity Analysis**
   - Map detections to taxonomy categories
   - Aggregate results by Kubernetes object type and category

4. **LLM-Based Correction**
   - Apply prompt configurations (Experiments 1–3)
   - Validate corrected outputs using schemas and detection tools

5. **Schema-Guided Correction**
   - Apply Kubecurity to enforce deterministic schema compliance
   - Re-evaluate corrected configurations

---

## 📄 Citation

If you use this replication package, please cite:



## 📜 License

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.

## 📌 Notes

To be added 


## ⚠️ Work in Progress
This replication package will be extended with:

Additional datasets

Full Kubecurity source code

Fully automated experiment pipelines

