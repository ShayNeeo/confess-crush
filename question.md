# README: Hành Trình Khai Phá Dữ Liệu Khách Hàng Sàn TMĐT - Sứ Mệnh DAZONE 2025 Vòng 2.2


## Mục Lục

1. [Nhiệm Vụ Bí Mật: Hiểu Lòng Khách Hàng, Giữ Chân Doanh Thu](#nhiệm-vụ-bí-mật-hiểu-lòng-khách-hàng-giữ-chân-doanh-thu)
2. [Kích Hoạt "Cỗ Máy Thời Gian": Hướng Dẫn Vận Hành Script](#kích-hoạt-cỗ-máy-thời-gian-hướng-dẫn-vận-hành-script)
3. [Bản Thiết Kế "Cỗ Máy": Cấu Trúc Script và Câu Chuyện Đằng Sau](#bản-thiết-kế-cỗ-máy-cấu-trúc-script-và-câu-chuyện-đằng-sau)
   * [Tổng Quan Lộ Trình Khám Phá](#tổng-quan-lộ-trình-khám-phá)
   * [Chương 1: Thu Thập Thông Tin Tình Báo - Chuẩn Bị Dữ Liệu](#chương-1-thu-thập-thông-tin-tình-báo---chuẩn-bị-dữ-liệu)
   * [Chương 2: Chế Tạo Quả Cầu Tiên Tri - Xây Dựng và Đánh Giá Model](#chương-2-chế-tạo-quả-cầu-tiên-tri---xây-dựng-và-đánh-giá-model)
   * [Chương 3: Đọc Vị Quả Cầu & Phân Loại "Chiến Binh" - Phân Tích Sâu và Tạo Chân Dung Khách Hàng](#chương-3-đọc-vị-quả-cầu--phân-loại-chiến-binh---phân-tích-sâu-và-tạo-chân-dung-khách-hàng)
4. [Đáp Án Cho "Sếp Tổng": Đối Chiếu Với Barem Chấm Điểm DAZONE 2025](#đáp-án-cho-sếp-tổng-đối-chiếu-với-barem-chấm-điểm-dazone-2025)
5. [Báo Cáo Chiến Công Lên "Bộ Chỉ Huy": Gợi Ý Trực Quan Hóa Cho Bài Thuyết Trình](#báo-cáo-chiến-công-lên-bộ-chỉ-huy-gợi-ý-trực-quan-hóa-cho-bài-thuyết-trình)
6. [Thông Điệp Từ "Chỉ Huy Trưởng" Đội Đặc Nhiệm](#thông-điệp-từ-chỉ-huy-trưởng-đội-đặc-nhiệm)

## Nhiệm Vụ Bí Mật: Hiểu Lòng Khách Hàng, Giữ Chân Doanh Thu

Sàn thương mại điện tử của chúng ta có hàng triệu khách hàng. Nhưng, ai trong số họ sẽ thực sự gắn bó và quay lại mua hàng tại một gian hàng cụ thể trong 6 tháng tới? Đây không chỉ là một câu hỏi, mà là một "nhiệm vụ tối mật" ảnh hưởng trực tiếp đến doanh thu và sự phát triển bền vững. Nếu chúng ta biết được điều này, chúng ta có thể:

* Chăm sóc đúng người, đúng lúc.
* Tung ra các chương trình khuyến mãi hiệu quả hơn.
* Biến khách hàng mới thành khách hàng trung thành.

"Cỗ máy thời gian" (script Python này) sẽ giúp chúng ta giải quyết nhiệm vụ này bằng cách:

1. **"Thu thập và làm sạch các mảnh ghép quá khứ"**: Chuẩn bị dữ liệu giao dịch và thông tin khách hàng.
2. **"Chế tạo các phiên bản quả cầu tiên tri"**: Xây dựng các mô hình dự đoán.
3. **"Kiểm tra độ chính xác của từng quả cầu"**: Đánh giá model nào "phán" chuẩn nhất.
4. **"Nhận diện các nhóm chiến binh mua sắm"**: Phân loại khách hàng dựa trên hành vi và đặc điểm.
5. **"Vạch ra kế hoạch tác chiến"**: Đề xuất các chiến lược kinh doanh thông minh.

## Kích Hoạt "Cỗ Máy Thời Gian": Hướng Dẫn Vận Hành Script

Để "cỗ máy" của chúng ta bắt đầu hành trình xuyên không về quá khứ và dự đoán tương lai, cả đội cần chuẩn bị:

1. **"Trang bị cá nhân" (Môi trường):** Máy tính được cài Python và các "vũ khí" cần thiết (thư viện) như `pandas`, `numpy` (để xử lý số liệu), `matplotlib`, `seaborn` (để vẽ biểu đồ), `scikit-learn` (bộ công cụ xây model), `imblearn` (để cân bằng lực lượng các nhóm khách hàng), `xgboost`, `lightgbm` (2 "chiến mã" mạnh mẽ), và `shap` (kính lúp soi thấu model).

2. **"Bản đồ kho báu cổ" (Dữ liệu đầu vào):** Các file CSV đã được "lau chùi" từ vòng trước hoặc từ script `data_cleaning.py`, cất giữ trong `cleaning_results/cleaned_data/`:
   * `competition_train_features.csv`: Thông tin huấn luyện các "nhà tiên tri".
   * `competition_test_features.csv`: Thông tin để "thử tài" các "nhà tiên tri".
   * `cleaned_user_info.csv`: Hồ sơ chi tiết của từng khách hàng.

3. **"Niệm thần chú" (Chạy script):** Thực thi file `DAZONE2025_R2.2_Main_Analysis.py`.

4. **"Chiến lợi phẩm" (Kết quả):** Mọi "bí mật" và "kho báu" sẽ được tập hợp tại thư mục `round_2.2`:
   * `model_outputs`: Nơi cất giữ các "quả cầu tiên tri" mạnh nhất.
   * `segmentation_outputs`: "Hồ sơ mật" của từng nhóm khách hàng.
   * `shap_outputs`: "Bản giải mã" cách "quả cầu" đưa ra dự đoán.
   * `visualizations_from_main_analysis`: "Album ảnh" ghi lại những khám phá quan trọng.
   * `logs`: "Biên niên sử" của cuộc hành trình.

## Bản Thiết Kế "Cỗ Máy": Cấu Trúc Script và Câu Chuyện Đằng Sau

Hành trình của chúng ta được chia thành 3 chương lớn, mỗi chương hé lộ một phần của bức tranh toàn cảnh về khách hàng của sàn thương mại điện tử.

### Tổng Quan Lộ Trình Khám Phá

Đây là bức tranh toàn cảnh về hành trình của chúng ta, từ lúc bắt đầu với dữ liệu thô cho đến khi tìm ra những "viên ngọc" insight:

```mermaid
graph TD
    A[Initial Data - CSV Features] --> PREPROC[Preprocessing - Scale, Encode, SMOTE for Initial Train];
    PREPROC --> OPT1_EVAL[Option 1: Train & Evaluate 4 Models on SMOTE Data];
    PREPROC --> OPT2_EVAL[Option 2: Train & Evaluate 6 Models on SMOTE Data];

    OPT1_EVAL --> SELECT_BEST_BASE[Select Best Base Model];
    OPT2_EVAL --> SELECT_BEST_BASE;

    SELECT_BEST_BASE -- Original Scaled Train Data --> RFECV_STEP[RFECV: Feature Selection for Best Base Model];
    RFECV_STEP --> SELECTED_FEATURES[Selected Feature Set];

    SELECTED_FEATURES -- Create X_train_smote_rfe, X_val_rfe --> TUNE_MODEL[Hyperparameter Tuning - RandomizedSearchCV for Best Base Model on X_train_rfe original];
    
    TUNE_MODEL --> FINAL_MODEL((Final Best Tuned Model));
    FINAL_MODEL -- Validation Data X_val_rfe --> EVAL_FINAL[Evaluate Final Tuned Model];

    FINAL_MODEL --> DEPLOY[Goal: Predict Next 6 Months];
    FINAL_MODEL -- Sample Data X_val_rfe or X_train_rfe --> SHAP_ANALYSIS{SHAP Analysis};
    SHAP_ANALYSIS --> IMPORTANT_FEATURES[Important Features via SHAP];

    %% Customer Segmentation Flow (Parallel or Post-Feature Engineering)
    DATA_FOR_SEG[Aggregated Customer Data + Demographics] --> PREPROC_SEG[Preprocessing for Segmentation];
    PREPROC_SEG --> OPTIMAL_K[Determine Optimal K - Elbow/Silhouette];
    OPTIMAL_K --> CLUSTERING[K-Means Clustering];
    CLUSTERING --> SEGMENTS[Customer Segments];
    SEGMENTS -- Combine with 'label' --> PROFILE_SEGMENTS[Evaluate & Profile Segments by Label];

    %% Styling (Optional)
    classDef data fill:#f9f,stroke:#333,stroke-width:2px;
    classDef process fill:#ccf,stroke:#333,stroke-width:2px;
    classDef model fill:#cfc,stroke:#333,stroke-width:2px,color:#000;
    classDef decision fill:#f80,stroke:#333,stroke-width:2px;
    classDef deployment fill:#e7d38f,stroke:#333,stroke-width:2px;
    classDef analysis fill:#d2b4de,stroke:#333,stroke-width:2px;

    class A,SELECTED_FEATURES,DATA_FOR_SEG,IMPORTANT_FEATURES,SEGMENTS,PROFILE_SEGMENTS data;
    class PREPROC,PREPROC_SEG,RFECV_STEP,OPTIMAL_K,CLUSTERING process;
    class OPT1_EVAL,OPT2_EVAL,SELECT_BEST_BASE,TUNE_MODEL,FINAL_MODEL,EVAL_FINAL model;
    class SHAP_ANALYSIS analysis;
    class DEPLOY deployment;
```
```mermaid
graph TD
    %% Data Ingestion
    A1[CSV: competition_train_features.csv] --> PROC_TRAIN_FEAT;
    A2[CSV: competition_test_features.csv] --> PROC_TEST_FEAT;
    A3[CSV: cleaned_user_info.csv] --> MERGE_USER_INFO_SEG;

    subgraph "Part 1: Data Preparation"
        direction LR
        PROC_TRAIN_FEAT["Preprocess Train Features: Drop Dates, Encode Cats"] --> DF_TRAIN_ALIGNED["df_train_aligned (Features + Label)"];
        PROC_TEST_FEAT["Preprocess Test Features"] --> DF_TEST_ALIGNED["df_test_aligned"];

        DF_TRAIN_ALIGNED -- Split --> X_TRAIN_RAW["X_train_raw"];
        DF_TRAIN_ALIGNED -- Split --> Y_TRAIN["y_train (labels)"];
        DF_TRAIN_ALIGNED -- Split --> X_VAL_RAW["X_val_raw"];
        DF_TRAIN_ALIGNED -- Split --> Y_VAL["y_val (labels)"];

        X_TRAIN_RAW --> SCALE_TRAIN["Scale Features"];
        X_VAL_RAW --> SCALE_VAL["Scale Features"];
        
        SCALE_TRAIN --> X_TRAIN_SCALED["X_train_scaled (e.g. 20 features)"];
        SCALE_VAL --> X_VAL_SCALED["X_val_scaled (e.g. 20 features)"];

        X_TRAIN_SCALED -- "SMOTE with y_train" --> X_TRAIN_SMOTE["X_train_smote (for initial model eval)"];
    end

    subgraph "Part 2: Model Training, Evaluation & Tuning"
        direction TB
        subgraph "Initial Model Evaluation"
            direction LR
            X_TRAIN_SMOTE --> OPT1_EVAL["Opt 1: Train 4 Models"];
            X_TRAIN_SMOTE --> OPT2_EVAL["Opt 2: Train 6 Models (MLP, SVC etc.)"];
            OPT1_EVAL -- "Evaluate on X_val_scaled, y_val" --> METRICS_OPT1["Metrics Opt1"];
            OPT2_EVAL -- "Evaluate on X_val_scaled, y_val" --> METRICS_OPT2["Metrics Opt2"];
            METRICS_OPT1 --> SELECT_BEST_BASE["Select Best Base Model Pre-Tuning"];
            METRICS_OPT2 --> SELECT_BEST_BASE;
        end

        subgraph "Feature Selection (RFECV)"
            direction LR
            SELECT_BEST_BASE -- "Uses X_train_scaled, y_train" --> RFECV_STEP["RFECV on Best Base Model (Surrogate if needed)"];
            RFECV_STEP --> SELECTED_FEATURES["Selected Feature Set (e.g., 19 features)"];
            X_TRAIN_SCALED -- "Filter by Selected" --> X_TRAIN_RFE["X_train_rfe (scaled, RFE features)"];
            X_VAL_SCALED -- "Filter by Selected" --> X_VAL_RFE["X_val_rfe (scaled, RFE features)"];
        end

        X_TRAIN_RFE -- "SMOTE with y_train" --> X_TRAIN_SMOTE_RFE["X_train_smote_rfe (for tuned model eval training)"];
        
        subgraph "Hyperparameter Tuning (Production: Top 2 Models)"
            direction TB
            SELECTED_FEATURES ----> TUNE_MODELS_SETUP["Setup Tuning for Top Models"];
            TUNE_MODELS_SETUP -- "Model 1 + (X_train_rfe, y_train - NO SMOTE)" --> TUNE_MODEL_1["Tune Model 1 (e.g., MLP)"];
            TUNE_MODELS_SETUP -- "Model 2 + (X_train_rfe, y_train - NO SMOTE)" --> TUNE_MODEL_2["Tune Model 2 (e.g., RF)"];
            
            TUNE_MODEL_1 --> TUNED_MODEL_1_INSTANCE["Tuned Model 1 Instance"];
            TUNE_MODEL_2 --> TUNED_MODEL_2_INSTANCE["Tuned Model 2 Instance"];

            TUNED_MODEL_1_INSTANCE -- "Train on X_train_smote_rfe, Eval on X_val_rfe" --> EVAL_TUNED_1["Evaluate Tuned Model 1"];
            TUNED_MODEL_2_INSTANCE -- "Train on X_train_smote_rfe, Eval on X_val_rfe" --> EVAL_TUNED_2["Evaluate Tuned Model 2"];
            
            EVAL_TUNED_1 --> COMPARE_FINAL["Compare & Select Final Best Model"];
            EVAL_TUNED_2 --> COMPARE_FINAL;
            SELECT_BEST_BASE -- "Original Best Model" --> COMPARE_FINAL;
            COMPARE_FINAL --> FINAL_MODEL(("_Final Best Model (e.g., RF_Comp_Tuned)_"));
        end
    end
    
    subgraph "Part 3 & 4: Post-Modeling Analysis & Reporting"
        direction TB
        subgraph "SHAP Analysis"
            FINAL_MODEL --> SHAP_ANALYSIS["SHAP Analysis on Final Model"];
            X_VAL_RFE --> SHAP_ANALYSIS;
            %% Data for SHAP (consistent with model training if RFE used)
            SHAP_ANALYSIS --> SHAP_OUTPUT["SHAP Plots & Importance Values"];
        end

        subgraph "User Segmentation, Profiling & Persona Assignment"
            direction TB
            DF_TRAIN_ALIGNED --> AGG_BEHAVIOR["Aggregate User Behavior from df_train_aligned"];
            AGG_BEHAVIOR & MERGE_USER_INFO_SEG["Merge with UserInfo (A3)"] --> DATA_FOR_SEG["User Data for Segmentation"];
            MERGE_USER_INFO_SEG -.-> DATA_FOR_SEG; 
            
            DATA_FOR_SEG --> PREPROC_SEG["Preprocess & Scale for Segmentation to X_cluster_scaled"];
            PREPROC_SEG --> OPTIMAL_K["Determine Optimal K (e.g., K=4 from log)"];
            OPTIMAL_K --> KMEANS_CLUSTER["K-Means Clustering"];
            KMEANS_CLUSTER -- "Assigns Cluster Labels" --> DF_SEG_WITH_CLUSTERS["df_segmentation_data_with_clusters"];
            
            DF_SEG_WITH_CLUSTERS --> INITIAL_CLUSTER_PROFILES["Initial Cluster Profiles (Numeric Means, Demo Modes)"];

            DF_TRAIN_ALIGNED --> USER_LEVEL_LABELS_CALC["Calculate User-Level Repurchase Labels (user_level_labels)"];
            DF_SEG_WITH_CLUSTERS & USER_LEVEL_LABELS_CALC --> MERGED_FOR_EARLY_PROFILE["Merge Segments with User Repurchase Labels"];
            MERGED_FOR_EARLY_PROFILE --> CLUSTER_LABEL_PROFILE["Calculate cluster_label_profile (Repurchase Rate & Size per Cluster)"];
            
            INITIAL_CLUSTER_PROFILES & CLUSTER_LABEL_PROFILE --> ENHANCED_CLUSTER_PROFILES["Enhanced cluster_profiles_mean (with Repurchase Rate & Size)"];
            
            ENHANCED_CLUSTER_PROFILES --> PERSONA_THRESHOLDS["Define Persona Thresholds"];
            PERSONA_THRESHOLDS & ENHANCED_CLUSTER_PROFILES --> ASSIGN_PERSONAS["Assign Personas to Clusters (persona_map)"];
            ASSIGN_PERSONAS --> DF_SEG_WITH_PERSONAS["Update df_segmentation_data_with_clusters with 'persona' col"];
            
            DF_SEG_WITH_PERSONAS & CLUSTER_LABEL_PROFILE & PERSONA_THRESHOLDS --> VALIDATE_PERSONAS["Persona Performance Validation"];
       
            DF_SEG_WITH_PERSONAS & USER_LEVEL_LABELS_CALC --> MERGED_FOR_FINAL_PROFILING["df_merged_for_profiling (for Part IV reporting)"];
            MERGED_FOR_FINAL_PROFILING --> ANALYZE_PERSONA_REPURCHASE["Analyze/Report Repurchase by Persona"];
            CLUSTER_LABEL_PROFILE --> VISUALIZE_CLUSTER_REPURCHASE["Visualize Repurchase by Cluster"];
            ANALYZE_PERSONA_REPURCHASE --> VISUALIZE_PERSONA_REPURCHASE["Visualize Repurchase by Persona"];
        end
        
        subgraph "Part V: Insights & Deployment Planning"
            direction TB
            FINAL_MODEL & SHAP_OUTPUT & DF_SEG_WITH_PERSONAS & ANALYZE_PERSONA_REPURCHASE & CLUSTER_LABEL_PROFILE --> BUSINESS_INSIGHTS["Generate Business Insights & Recommendations"];
            FINAL_MODEL --> DEPLOY_MODEL["Plan: Deploy Model for Future Predictions"];
        end
    end

    %% Styling
    classDef data fill:#583269,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef process fill:#204051,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef model fill:#3B685C,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef decision fill:#7D5A38,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef deployment fill:#A36B38,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef analysis fill:#6A4C93,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef io fill:#8A7A5F,stroke:#ccc,stroke-width:2px,color:#fff;
    classDef styleForMetrics fill:#4E6A58,stroke:#ccc,stroke-width:1px,color:#fff; %% Renamed class
    
    %% Ensure a blank line above this line separates classDefs from class assignments
    class A1,A2,A3,X_TRAIN_RAW,Y_TRAIN,X_VAL_RAW,Y_VAL,X_TRAIN_SCALED,X_VAL_SCALED,X_TRAIN_SMOTE,SELECTED_FEATURES,X_TRAIN_RFE,X_VAL_RFE,X_TRAIN_SMOTE_RFE,SHAP_OUTPUT,DATA_FOR_SEG,CLUSTER_LABELS,DF_SEG_WITH_CLUSTERS,INITIAL_CLUSTER_PROFILES,USER_LEVEL_LABELS_CALC,MERGED_FOR_EARLY_PROFILE,CLUSTER_LABEL_PROFILE,ENHANCED_CLUSTER_PROFILES,PERSONA_THRESHOLDS,DF_SEG_WITH_PERSONAS,MERGED_FOR_FINAL_PROFILING io;
    class PROC_TRAIN_FEAT,PROC_TEST_FEAT,DF_TRAIN_ALIGNED,DF_TEST_ALIGNED,SCALE_TRAIN,SCALE_VAL,PREPROC_SEG,OPTIMAL_K,KMEANS_CLUSTER,AGG_BEHAVIOR,MERGE_USER_INFO_SEG process;
    class OPT1_EVAL,OPT2_EVAL,RFECV_STEP,TUNE_MODELS_SETUP,TUNE_MODEL_1,TUNE_MODEL_2,TUNED_MODEL_1_INSTANCE,TUNED_MODEL_2_INSTANCE,EVAL_TUNED_1,EVAL_TUNED_2,FINAL_MODEL,ANALYZE_PERSONA_REPURCHASE,VISUALIZE_CLUSTER_REPURCHASE,VISUALIZE_PERSONA_REPURCHASE model;
    class SELECT_BEST_BASE,COMPARE_FINAL decision;
    class SHAP_ANALYSIS,VALIDATE_PERSONAS,BUSINESS_INSIGHTS analysis;
    class DEPLOY_MODEL deployment;
    class METRICS_OPT1,METRICS_OPT2 styleForMetrics;
```
