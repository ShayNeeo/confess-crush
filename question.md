# DAZONE 2025 Round 2.2: Customer Retention Prediction for E-commerce Platform

## Project Overview

This project addresses a critical business challenge in e-commerce: predicting customer retention and return behavior on merchant platforms. The objective is to develop a comprehensive data science solution that can identify which customers are likely to return to specific merchants within the next 6 months, enabling targeted retention strategies and optimized resource allocation.

## Table of Contents

1. [Business Problem Statement](#business-problem-statement)
2. [Technical Architecture](#technical-architecture)
3. [Data Processing Pipeline](#data-processing-pipeline)
4. [Machine Learning Pipeline](#machine-learning-pipeline)
5. [Advanced Analytics Components](#advanced-analytics-components)
6. [Evaluation Framework](#evaluation-framework)
7. [Implementation Status](#implementation-status)
8. [Technical Questions for Review](#technical-questions-for-review)

## Business Problem Statement

**Primary Objective:** Predict customer return behavior to specific merchants within a 6-month timeframe.

**Key Business Value:**
- Enable targeted customer retention campaigns
- Optimize marketing budget allocation
- Improve customer lifetime value prediction
- Identify high-risk customer segments for proactive intervention

**Success Metrics:**
- Model prediction accuracy (AUC-ROC, Precision, Recall)
- Customer segmentation quality (Silhouette Score)
- Business actionability of insights
- Interpretability of model decisions

## Technical Architecture

### System Requirements
- **Environment:** Python 3.8+ with scientific computing stack
- **Core Libraries:** pandas, numpy, scikit-learn, xgboost, lightgbm, imblearn, shap
- **Visualization:** matplotlib, seaborn
- **Data Processing:** Optimized for large datasets (5M+ records)

### Data Sources
- `train.csv`: Historical customer-merchant interaction data with labels
- `test.csv`: Unlabeled data for final predictions
- `user_info.csv`: Customer demographic and profile information
- `user_log.csv`: Detailed customer behavior logs and transaction history

### Output Structure
```
round_2.2/
├── model_outputs/          # Trained models and performance metrics
├── segmentation_outputs/   # Customer clustering results and profiles
├── shap_outputs/          # Model interpretability analysis
├── visualizations/        # Charts and analytical visualizations
└── logs/                  # Processing logs and performance tracking
```

## Data Processing Pipeline

### Phase 1: Data Quality Assessment and Cleaning

This phase implements a systematic approach to data quality assessment and preprocessing, ensuring data integrity and reliability for downstream analysis.

```mermaid
graph TD
    A[Raw Data Ingestion] --> B[Data Quality Assessment]
    B --> C[Missing Value Analysis]
    C --> D[Outlier Detection and Treatment]
    D --> E[Data Type Optimization]
    E --> F[Categorical Encoding]
    F --> G[Feature Engineering]
    G --> H[Data Validation]
    H --> I[Clean Dataset Output]
```

**Key Processing Steps:**
1. **Comprehensive Data Profiling:** Automated assessment of completeness, consistency, and quality
2. **Outlier Detection:** IQR-based detection with domain-specific validation rules
3. **Missing Value Handling:** Strategy justified by data patterns and business logic
4. **Memory Optimization:** Efficient data types and categorical encoding for large datasets
5. **Feature Engineering:** Time-based features, behavioral aggregations, interaction metrics

### Phase 2: Feature Engineering Pipeline

The feature engineering process transforms raw customer interaction data into meaningful predictive features through advanced behavioral analytics and demographic integration.

```mermaid
graph TD
    subgraph Data Preprocessing Pipeline
        A[Load Train and Test Features] --> B(Remove Raw Date Columns);
        B --> C[Handle Missing Values];
        C -- Numeric: median/0, Categorical: Unknown --> D[Label Encoding for Categorical Variables];
        D -- Store Label Encoders --> E[Handle Infinite Values];
        E --> F[Clean Data Ready];
        F --> G[Train-Validation Split];
        G --> H[StandardScaler Normalization];
        H --> I[SMOTE Balancing on X_train_scaled and y_train];
        I --> J[Data Ready for Model Training];
        H --> K[Store Original X_train_scaled for Tuning];
    end
```

**User Behavioral Features:**
- Total interactions, unique items/categories/brands explored
- Purchase conversion rates and frequencies
- Session patterns and engagement metrics
- Temporal behavior analysis (weekend/evening patterns)

**User-Merchant Relationship Features:**
- Interaction span and frequency
- Purchase history and loyalty indicators
- Category diversity and exploration patterns
- Recency, frequency, monetary (RFM) analysis

**Demographic Integration:**
- Age group segmentation
- Gender-based behavior patterns
- Geographic and carrier information

## Machine Learning Pipeline

### Model Development Strategy

The machine learning pipeline implements a dual-track approach to model development, balancing rapid deployment needs with comprehensive performance optimization.

#### Option 1: Focused Model Optimization
- **Target Models:** LightGBM_Opt1, RandomForest_Opt1, XGBoost_Opt1, LogisticRegression_Opt1
- **Approach:** Deep optimization of proven algorithms with standard configurations
- **Use Case:** Quick deployment and reliable performance assessment

#### Option 2: Comprehensive Model Comparison
- **Models:** LR_Comp, RF_Comp, XGBoost_Comp, LightGBM_Comp, SVC_Comp, MLP_Comp
- **Approach:** Extensive algorithm evaluation and competitive analysis
- **Use Case:** Maximum performance optimization through algorithm diversity

### Training Pipeline

```mermaid
graph TD
    A[Preprocessed Features] --> B[Train-Validation Split]
    B --> C[Feature Scaling - StandardScaler]
    C --> D[Class Balancing - SMOTE]
    D --> E[Model Training]
    E --> F[Performance Evaluation]
    F --> G{Best Model Selection}
    G --> H[Hyperparameter Tuning]
    H --> I[Final Model Validation]
    I --> J[Model Persistence]
```

**Standard Evaluation Process for Each Model:**
```mermaid
graph LR
    A[Prepared Training Data] --> B(SMOTE Class Balancing);
    B --> C[Train Model on X_train_smote];
    C --> D[Evaluate on X_val_scaled];
    D --> E[Performance Metrics and Visualization];
```

**Hyperparameter Optimization Process:**
```mermaid
graph TD
    subgraph Hyperparameter Tuning Pipeline
        A[Select Best Initial Model] --> B{Parameter Grid Available};
        B -- Yes --> C[Define Model Instance and Parameter Range];
        C --> D[Use Original X_train_scaled and y_train];
        D -- Apply Class Weight or Scale Pos Weight --> E(RandomizedSearchCV for Optimal Configuration);
        E --> F[Evaluate Tuned Model on X_val_scaled];
        F --> G{Performance Improved};
        G -- Yes --> H[Update as Current Best Model];
        G -- No --> I[Keep Original Model];
    end
```

**Key Technical Decisions:**
1. **Data Balancing:** SMOTE for addressing class imbalance
2. **Feature Scaling:** StandardScaler for numerical stability
3. **Validation Strategy:** Hold-out validation with temporal considerations
4. **Hyperparameter Optimization:** RandomizedSearchCV with cross-validation
5. **Model Selection:** Multi-metric evaluation (AUC, Precision, Recall, F1)

### Model Training Workflows

#### Workflow 1: Focused Algorithm Optimization
```mermaid
graph TD
    A[Preprocessed and SMOTE-balanced Data] --> B1[Train and Evaluate LightGBM_Opt1];
    A --> B2[Train and Evaluate RandomForest_Opt1];
    A --> B3[Train and Evaluate XGBoost_Opt1];
    A --> B4[Train and Evaluate LogisticRegression_Opt1];
    B1 & B2 & B3 & B4 --> C[Consolidate Option 1 Results];
```

#### Workflow 2: Comprehensive Algorithm Comparison
```mermaid
graph TD
    A[Preprocessed and SMOTE-balanced Data] --> B[Simultaneous Multi-Model Comparison];
    B --> LR[Train and Evaluate LR_Comp];
    B --> RF[Train and Evaluate RF_Comp];
    B --> XGB[Train and Evaluate XGB_Comp];
    B --> LGBM[Train and Evaluate LGBM_Comp];
    B --> SVC[Train and Evaluate SVC_Comp];
    B --> MLP[Train and Evaluate MLP_Comp];
    LR & RF & XGB & LGBM & SVC & MLP --> C[Consolidate Option 2 Results];
    C --> D[Compare and Select Outstanding Model from Option 2];
```

## Advanced Analytics Components

### SHAP Analysis for Model Interpretability

The interpretability analysis employs SHAP (SHapley Additive exPlanations) to provide comprehensive model explanation and feature importance analysis.

```mermaid
graph TD
    A[Final Best Model] --> B[Sample Validation Data X_val_scaled];
    A --> C{Model Type Classification};
    C -- Tree-based --> D[SHAP TreeExplainer];
    C -- Non-tree with predict_proba --> E[SHAP KernelExplainer];
    E -- Requires Background Data --> D;
    D --> F[Calculate SHAP Values];
    F --> G[Generate SHAP Summary Visualizations];
    G --> H[Save SHAP Importance Results];
```

**Interpretability Outputs:**
- Global feature importance rankings
- Local prediction explanations
- Feature interaction analysis
- Model decision boundary visualization

### Customer Segmentation Analysis

**Methodology:** K-Means Clustering with optimal k selection using multiple validation methods.

```mermaid
graph TD
    A[Comprehensive Customer Data] --> B[Integrate Demographic Information];
    B --> C[Preprocessing for Clustering];
    C -- Scaled Data --> D{Calculate Inertia and Silhouette Scores};
    D -- For Various k Values --> E[Generate Elbow and Silhouette Plots];
    E --> F{Select optimal_k by K_SELECTION_METHOD};
    F -- optimal_k --> G[Execute K-Means with optimal_k];
    G --> H[Assign Cluster Labels to Customers];
    H --> I[Cluster Profiling and Characteristic Analysis];
    I --> J[Save Segmentation Results];
```

**Segmentation Outputs:**
- Customer personas with behavioral characteristics
- Segment-specific retention strategies
- Profiling based on demographics and behavior
- Actionable business recommendations per segment

## Evaluation Framework

### Model Performance Metrics
- **AUC-ROC:** Overall discriminative ability
- **Precision/Recall:** Class-specific performance
- **F1-Score:** Balanced performance measure
- **Confusion Matrix:** Detailed classification analysis

### Business Impact Assessment
- **Segmentation Quality:** Silhouette score and interpretability
- **Feature Importance:** Business relevance and actionability
- **Scalability:** Performance on large datasets
- **Interpretability:** SHAP analysis clarity and business alignment


## Implementation Status

### Completed Components
- ✅ Comprehensive data cleaning and quality assessment pipeline
- ✅ Advanced feature engineering for user behavior and demographics
- ✅ Multi-model training and evaluation framework
- ✅ Hyperparameter optimization with proper validation
- ✅ SHAP-based model interpretability analysis
- ✅ K-means customer segmentation with optimal k selection
- ✅ Automated reporting and documentation system

### Current Performance Highlights
- **Best Model:** RandomForest_Comp_Tuned (AUC: 0.6279)
- **Segmentation:** 4 distinct customer personas identified
- **Data Quality:** Comprehensive cleaning with documented justifications
- **Scalability:** Optimized for 5M+ record datasets

## Technical Questions for Review

### 1. Data Processing and Feature Engineering
- **Question:** Is the current approach to outlier detection (IQR + domain rules) sufficient, or should we implement more sophisticated methods like Isolation Forest or Local Outlier Factor?
- **Context:** Currently using IQR with business logic validation. Wondering about trade-offs between simplicity and detection accuracy.

### 2. Model Selection and Validation
- **Question:** Given the temporal nature of customer behavior, should we implement time-series cross-validation instead of random train-test splits?
- **Context:** Current validation uses random splits. Customer behavior may have temporal dependencies that standard CV doesn't capture.

### 3. Class Imbalance Handling
- **Question:** Is SMOTE the optimal choice for this use case, or should we explore other techniques like ADASYN, BorderlineSMOTE, or cost-sensitive learning?
- **Context:** Using SMOTE for class balancing. Unsure if synthetic samples adequately represent real customer behavior patterns.

### 4. Feature Selection Strategy
- **Question:** Should we implement automated feature selection (RFE, SelectKBest) before model training, or is the current domain-driven approach sufficient?
- **Context:** Currently using all engineered features. Concerned about potential overfitting and computational efficiency.

### 5. Customer Segmentation Optimization
- **Question:** Would hierarchical clustering or DBSCAN provide better customer segments than K-means, especially for identifying outlier customer behaviors?
- **Context:** Using K-means with optimal k selection. Wondering if other clustering methods might reveal more actionable customer segments.

### 6. Model Interpretability vs Performance Trade-off
- **Question:** How should we balance model interpretability (favoring simpler models) against predictive performance (favoring ensemble methods)?
- **Context:** Current best model is RandomForest (interpretable) vs potentially better performing but less interpretable neural networks.

### 7. Evaluation Metrics Selection
- **Question:** Given the business context, should we prioritize Precision (minimize false positives) or Recall (minimize false negatives) in model optimization?
- **Context:** Currently optimizing for AUC. Business cost of false positives vs false negatives is unclear.

### 8. Scalability and Production Considerations
- **Question:** What additional considerations should be implemented for production deployment (real-time scoring, model drift detection, automated retraining)?
- **Context:** Current solution is batch-oriented. Considering production requirements for real-time customer scoring.

---

**Project Status:** Ready for mentor review and guidance on optimization strategies.

**Last Updated:** [Current Date]

**Author:** [Student Name]

**Repository:** DAZONE 2025 Round 2.2 Submission 
