# Technical Portfolio

This repository is the central portfolio map connecting my enterprise IT delivery experience with hands-on technical artifacts across machine learning, neural-network optimization, high-performance computing, Spark/Databricks lakehouse engineering, computer vision, and GIS analytics on Azure.

---

## Repository Map

| Repository | Status | Purpose | Primary Focus |
|---|---|---|---|
| [`ml-model-selection-and-error-analysis`](https://github.com/olzhas-tolegen/ml-model-selection-and-error-analysis) | **Completed** | Multiclass model selection and error-analysis benchmark on the Covertype dataset | Decision Trees, kNN, SVM, scikit-learn MLP, PyTorch MLP, learning curves, class-level metrics, runtime trade-offs |
| [`neural-training-optimization-stability`](https://github.com/olzhas-tolegen/neural-training-optimization-stability) | **Completed** | Controlled study of neural-network optimization, regularization, stability, and compute efficiency | SGD and Adam-family ablations, randomized optimization, regularization, multi-seed stability, per-class generalization |
| [`gis-data-analytics-azure-platform`](https://github.com/tolegen-ai/gis-data-analytics-azure-platform) | **Completed** | Azure-hosted GIS analytics platform | PostgreSQL/PostGIS, Azure, Docker, Kubernetes, Terraform, geospatial analytics |
| [`finance-sales-lakehouse-spark-databricks`](https://github.com/tolegen-ai/finance-sales-lakehouse-spark-databricks) | **Completed** | Enterprise finance and sales analytics platform | Databricks, Spark, lakehouse design, data quality, business analytics modernization |
| `high-performance-ml-systems` | In progress | HPC and ML systems portfolio | Parallel computing, distributed systems, GPU/HPC, performance engineering |
| `computer-vision-perception-systems` | Planned | Computer vision and perception systems | Image processing, object detection, tracking, motion analysis, classification |
| `ai-ml-tpm-portfolio` | Planned | AI/ML Technical Program Management portfolio | TPM narrative, architecture, program artifacts, roadmap ownership, AI platform execution |
| `ai-research-engineer-portfolio` | Planned | AI research and applied ML engineering portfolio | Reproducible experimentation, research summaries, model evaluation, applied AI depth |

---

## Featured Portfolio Systems

### ML Model Selection and Error Analysis

A reproducible multiclass classification benchmark comparing classical and neural models on the Forest Covertype dataset.

The project evaluates five algorithm families under a shared experimental framework:

- Decision Tree
- k-Nearest Neighbors
- Support Vector Machine
- scikit-learn MLPClassifier
- PyTorch multilayer perceptron

The evaluation combines:

- accuracy, Macro-F1, and balanced accuracy;
- learning curves and model-complexity curves;
- confusion matrices and per-class precision, recall, and F1;
- fit and prediction runtime;
- class-imbalance and minority-class error analysis;
- leakage-controlled model selection and external evaluation.

#### Key findings

| Finding | Evidence |
|---|---|
| Best external accuracy and Macro-F1 | Distance-weighted kNN with `k=1`: **0.808 accuracy**, **0.699 Macro-F1** |
| Best balanced accuracy | RBF SVM with `C=10`, `gamma=0.1`: **0.762 balanced accuracy** |
| Best practical interpretability/runtime compromise | Decision Tree: **0.767 accuracy**, **0.659 Macro-F1**, approximately **0.20 s fit** and **0.46 s prediction** |
| Highest inference cost | RBF SVM required approximately **754.20 s** to predict the external remainder |
| Core model-risk lesson | Accuracy alone concealed weak minority-class behavior; model choice changed materially by metric and operating constraint |

The resulting decision framework is objective-dependent: kNN for maximum accuracy and Macro-F1, RBF SVM for class-balanced recall, and Decision Tree when interpretability and runtime dominate.

[Open repository](https://github.com/olzhas-tolegen/ml-model-selection-and-error-analysis)

---

### Neural Training Optimization and Stability

A controlled neural-network training study that isolates how optimizer choice, randomized optimization, regularization, seed sensitivity, and compute budgets affect convergence and multiclass generalization.

The project holds the following elements constant:

- 54-feature Covertype representation;
- `54 → 64 → 64 → 7` ReLU MLP;
- 8,135 trainable parameters;
- class-weighted cross-entropy;
- batch size of 512;
- fixed train, validation, and locked test partitions;
- three repeated seeds;
- consistent CPU execution settings.

The experiment evaluates:

- plain SGD, momentum SGD, Nesterov, Adam, Adam without bias correction, Adam with `beta1=0`, and AdamW;
- randomized hill climbing, simulated annealing, and genetic algorithms on the 455-parameter output layer;
- L2 weight decay, dropout, early stopping, label smoothing, and input noise;
- validation loss, Macro-F1, balanced accuracy, per-class behavior, runtime, gradient evaluations, and function evaluations.

#### Key findings

| Finding | Evidence |
|---|---|
| Highest median test Macro-F1 | Adam without bias correction: **0.5824** |
| Fastest threshold crossing | Adam without bias correction reached the locked loss threshold in a median **320 updates** and **0.824 s** |
| Most stable optimizer | Standard Adam recorded approximately **0.0010 Macro-F1 standard deviation**, versus **0.0224** for the no-bias variant |
| Highest median accuracy and balanced accuracy | AdamW: **0.6827 accuracy**, **0.7533 balanced accuracy** |
| Best individual regularizer | L2 weight decay increased median test Macro-F1 from **0.5659** to **0.5697** |
| Randomized-search lesson | RHC reduced validation loss but lowered median test Macro-F1 from **0.5424** to **0.5219** after SGD pretraining |
| Deployment lesson | Lower validation loss and smaller train–validation gaps did not reliably indicate better multiclass generalization |

The resulting selection rule is multi-objective: use seed-aggregated Macro-F1, balanced accuracy, per-class precision/recall, convergence speed, stability, and compute cost together rather than selecting from validation loss or accuracy alone.

[Open repository](https://github.com/olzhas-tolegen/neural-training-optimization-stability)

---

### GIS Data Analytics Azure Platform — Completed

A cloud-native geospatial analytics platform for humanitarian and infrastructure project tracking.

Architecture and implementation:

- Node.js / Express public web application
- Django Admin and Django REST Framework backend
- Azure Database for PostgreSQL with PostGIS
- Leaflet.js interactive mapping
- Docker Compose local environment
- Kubernetes deployment model
- Terraform-based Azure infrastructure
- EN/KZ localization
- Project-level geospatial filtering and GeoJSON output

[Open repository](https://github.com/tolegen-ai/gis-data-analytics-azure-platform)

---

### Finance and Sales Lakehouse Platform — Completed

An enterprise data platform for finance, sales, shipment, pricing, customer, product, and retail analytics.

Architecture and implementation:

- Databricks
- Apache Spark / PySpark
- Azure Data Lake
- Delta-style lakehouse layers
- Direct and indirect shipment analytics
- Point-of-sales analytics
- Product and customer master data
- Pricing and currency data
- Reporting-ready gold datasets
- Data-quality controls
- Reproducible data pipelines

[Open repository](https://github.com/tolegen-ai/finance-sales-lakehouse-spark-databricks)

---

### High-Performance ML Systems — In Progress

A systems-focused repository aligned with high-performance computing and scalable ML infrastructure.

Representative topics:

- locality and memory hierarchy;
- I/O-efficient computing;
- OpenMP and shared-memory parallelism;
- MPI and distributed-memory systems;
- parallel sorting, scans, and list ranking;
- distributed matrix multiplication;
- distributed graph processing and partitioning;
- GPU scaling concepts;
- strong- and weak-scaling analysis.

---

### Computer Vision Perception Systems — Planned

A computer vision portfolio focused on applied perception pipelines and visual analytics.

Representative work:

- image processing and filtering;
- traffic-sign and traffic-signal perception;
- camera geometry and augmented reality;
- motion detection and video analysis;
- object tracking and pedestrian detection;
- visual classification;
- end-to-end perception-system evaluation.

---

## Technical Stack

| Area | Technologies and Methods |
|---|---|
| Programming | Python, JavaScript, SQL, Bash |
| ML / AI | scikit-learn, PyTorch, supervised model selection, error analysis, neural optimization, regularization, clustering |
| Experimentation | Learning curves, model-complexity curves, ablations, multi-seed analysis, runtime and compute accounting |
| Data Engineering | Spark, PySpark, Databricks, PostgreSQL, PostGIS |
| Cloud | Azure, Azure App Service, Azure Database for PostgreSQL, AKS, ACR |
| Infrastructure | Docker, Docker Compose, Kubernetes, Terraform |
| HPC / Systems | OpenMP, MPI, distributed algorithms, strong and weak scaling |
| GIS | Leaflet.js, GeoJSON, PostGIS, spatial indexing |
| Analytics | Pandas, notebooks, reporting pipelines, reproducibility documentation |
| Delivery | Roadmaps, program plans, operating models, risk management, execution metrics |

---

## Contact

For collaboration, technical review, or career opportunities, connect through GitHub or LinkedIn.
