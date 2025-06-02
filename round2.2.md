# README: Giải Mã Kho Báu Dữ Liệu Sàn Thương Mại Điện Tử - DAZONE 2025 Vòng 2.2

Chào mừng các nhà thám hiểm dữ liệu của đội chúng ta đến với hành trình chinh phục DAZONE 2025! File Python này chính là la bàn và cuốc xẻng để chúng ta khai phá những "mỏ vàng" thông tin từ dữ liệu của một sàn thương mại điện tử. Mục tiêu cuối cùng? Tìm ra bí mật giữ chân khách hàng và chiến thắng cuộc thi! 🚀

## Mục Lục

1.  [Bối Cảnh Cuộc Thám Hiểm: Sàn Thương Mại Điện Tử và Thử Thách DAZONE](#bối-cảnh-cuộc-thám-hiểm-sàn-thương-mại-điện-tử-và-thử-thách-dazone)
2.  [Cách Vận Hành "Cỗ Máy Khai Khoáng" (Cách Chạy Script)](#cách-vận-hành-cỗ-máy-khai-khoáng-cách-chạy-script)
3.  [Bản Thiết Kế "Cỗ Máy" (Cấu Trúc Script Chi Tiết)](#bản-thiết-kế-cỗ-máy-cấu-trúc-script-chi-tiết)
    * [Giai Đoạn 1: Gom Góp "Đất Đá" và Chuẩn Bị "Dụng Cụ"](#giai-đoạn-1-gom-góp-đất-đá-và-chuẩn-bị-dụng-cụ)
    * [Giai Đoạn 2: "Luyện Kim" và "Thử Vàng" (Huấn Luyện & Đánh Giá Model)](#giai-đoạn-2-luyện-kim-và-thử-vàng-huấn-luyện--đánh-giá-model)
    * [Giai Đoạn 3: "Chế Tác Trang Sức" và "Trưng Bày" (Phân Tích Sâu & Kể Chuyện)](#giai-đoạn-3-chế-tác-trang-sức-và-trưng-bày-phân-tích-sâu--kể-chuyện)
4.  [Đối Chiếu Với "Bảng Vàng" Ban Giám Khảo (Barem Chấm Điểm DAZONE 2025)](#đối-chiếu-với-bảng-vàng-ban-giám-khảo-barem-chấm-điểm-dazone-2025)
5.  [Những "Viên Kim Cương" Nên "Đánh Bóng" Cho Buổi Trình Bày (Gợi Ý Trực Quan Hóa)](#những-viên-kim-cương-nên-đánh-bóng-cho-buổi-trình-bày-gợi-ý-trực-quan-hóa)
6.  [Lời Dặn Dò Từ "Trưởng Đoàn Thám Hiểm"](#lời-dặn-dò-từ-trưởng-đoàn-thám-hiểm)

## Bối Cảnh Cuộc Thám Hiểm: Sàn Thương Mại Điện Tử và Thử Thách DAZONE

Tưởng tượng chúng ta đang làm việc cho một sàn thương mại điện tử lớn. Sàn có rất nhiều khách hàng và vô vàn sản phẩm. Một câu hỏi lớn mà sếp đặt ra là: "Làm sao để biết khách hàng nào sẽ tiếp tục mua sắm với chúng ta, cụ thể là với một gian hàng họ từng mua, trong 6 tháng tới?" [cite: 909, 911] Đây chính là "kho báu" mà cuộc thi DAZONE 2025 Vòng 2.2 yêu cầu chúng ta tìm kiếm. [cite: 895]

"Cỗ máy khai khoáng" (script Python) này sẽ giúp chúng ta:
1.  **Sàng lọc "đất đá"**: Làm sạch và chuẩn bị dữ liệu giao dịch, thông tin người dùng. [cite: 946]
2.  **Chế tạo "máy dò vàng"**: Xây dựng các mô hình (model) dự đoán khả năng khách hàng quay lại. [cite: 925, 949]
3.  **Thử nghiệm "máy dò"**: Đánh giá xem "máy dò" nào hoạt động tốt nhất. [cite: 926]
4.  **Phân loại "vàng"**: Chia khách hàng thành từng nhóm (phân khúc) để hiểu rõ hơn về họ. [cite: 951]
5.  **Đề xuất "chiến lược khai thác"**: Đưa ra những gợi ý kinh doanh thông minh dựa trên những gì tìm được. [cite: 953, 981]

## Cách Vận Hành "Cỗ Máy Khai Khoáng" (Cách Chạy Script)

Để "cỗ máy" này hoạt động, đội của chúng ta cần:
1.  **"Xưởng chế tạo" (Môi trường):** Máy tính có cài Python và các "phụ tùng" (thư viện) như `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` (cho các model, scaler), `imblearn` (cho SMOTE), `xgboost`, `lightgbm` (cho các model mạnh), và `shap` (để hiểu model).
2.  **"Nguồn quặng" (Dữ liệu đầu vào):** Các file CSV đã được xử lý ở vòng trước hoặc từ script `data_cleaning.py`, nằm trong thư mục `cleaning_results/cleaned_data/`:
    * `competition_train_features.csv`: Dữ liệu huấn luyện chính, đã có sẵn nhiều "đặc điểm" (features) của khách hàng.
    * `competition_test_features.csv`: Dữ liệu để "thử thách" model, cấu trúc tương tự file train.
    * `cleaned_user_info.csv`: Thông tin chi tiết về người dùng (tuổi, giới tính, nghề nghiệp,...).
3.  **Khởi động "cỗ máy"**: Chạy file Python `DAZONE2025_R2.2_Main_Analysis.py`.
4.  **"Thành phẩm" (Kết quả):** Mọi thứ "khai thác" được sẽ nằm trong thư mục `round_2.2`:
    * `model_outputs`: Các "máy dò vàng" (model) tốt nhất đã được lưu lại.
    * `segmentation_outputs`: Thông tin chi tiết về các nhóm khách hàng và "chân dung" (persona) của họ.
    * `shap_outputs`: Các file giải thích cách "máy dò" đưa ra quyết định.
    * `visualizations_from_main_analysis`: Rất nhiều biểu đồ, hình ảnh minh họa cho từng bước.
    * `logs`: "Sổ nhật ký" ghi lại toàn bộ quá trình "khai khoáng".

## Bản Thiết Kế "Cỗ Máy" (Cấu Trúc Script Chi Tiết)

"Cỗ máy" của chúng ta có 3 bộ phận chính, hoạt động tuần tự.

### Giai Đoạn 1: Gom Góp "Đất Đá" và Chuẩn Bị "Dụng Cụ"

Đây là bước chuẩn bị nền tảng, đảm bảo mọi thứ sẵn sàng.

* **Khai Báo "Dụng Cụ" (Import Libraries):** Gọi tên tất cả các thư viện cần thiết.
* **Thiết Lập "Công Trường" (Configuration):**
    * `DEVELOPMENT_MODE`: Chế độ "chạy thử" (`True`) để nhanh có kết quả với ít dữ liệu, hoặc "chạy thật" (`False`) với toàn bộ dữ liệu. Log gần nhất của chúng ta là `False`.
    * `PRODUCTION_TIER`: Khi "chạy thật", chọn mức độ "đào sâu" (1: nhanh hơn, 2: kỹ hơn, lâu hơn). Log gần nhất là `2`.
    * `RANDOM_STATE`: Một con số (ví dụ: `9` như trong log, hoặc `42` như trong script gốc) để đảm bảo các bước ngẫu nhiên (như chia dữ liệu, khởi tạo model) cho kết quả giống nhau mỗi lần chạy, giúp dễ dàng kiểm tra và so sánh.
    * `K_SELECTION_METHOD`: Cách chọn số cụm `k` cho K-Means ("silhouette" hoặc "elbow"). Log gần nhất là `silhouette`.
    * Màu sắc (`PRIMARY_RED_THEME`): Chọn màu đỏ làm chủ đạo cho các biểu đồ.
* **Tạo Các "Kho Chứa" (Output Directory Setup):** Tạo các thư mục để lưu kết quả.
* **Ghi "Sổ Tay Công Trường" (Logging Setup):** Thiết lập để ghi lại mọi hoạt động.
* **Thu Thập "Đất Đá Thô" (Load Data):**
    * Hàm `load_data` sẽ đọc dữ liệu từ các file CSV.
    * Dữ liệu được lấy mẫu nếu ở `DEVELOPMENT_MODE`.
* **"Sơ Khảo Địa Chất" (Initial Data Exploration):**
    * Vẽ biểu đồ tròn thể hiện tỷ lệ khách hàng quay lại và không quay lại (`label`) trong tập huấn luyện. Giúp hiểu sự mất cân bằng của dữ liệu.
* **"Tinh Chế Quặng" Sơ Bộ (Data Preparation for Modeling):**
    * Hàm `preprocess_for_modeling`: "Lọc rửa" dữ liệu lần cuối.
        * **Xử lý ngày tháng:** Bỏ các cột ngày tháng thô (vì đã có features được tạo từ ngày tháng như `interaction_span_days`).
        * **Điền giá trị rỗng (NaN):** Với cột số, điền 0 cho các cột đếm/cờ, điền trung vị (median) cho các cột khác. Cột chữ/category điền "Unknown".
        * **Mã hóa chữ thành số (Label Encoding):** Chuyển các cột dạng chữ (ví dụ `sex`, `age_group`) thành dạng số mà model hiểu được. Lưu lại "bảng mã" (`label_encoders`) để áp dụng nhất quán cho cả tập train và test.
        * **Xử lý vô cực (Inf):** Chuyển thành NaN rồi xử lý.
    * **Phân chia "Khu Vực Khai Thác" (Train/Validation Split):** Chia tập train thành 2 phần: `X_train` (để dạy model) và `X_val` (để kiểm tra model). `y_train` và `y_val` là "đáp án" tương ứng.
    * **"Đồng Bộ Hóa Kích Cỡ" (StandardScaler):** Đưa các features số về cùng một thang đo, tránh feature nào có giá trị lớn "át vía" feature khác.
    * **"Tăng Cường Lực Lượng" Cho Nhóm Yếu Thế (SMOTE):** Nếu nhóm khách hàng quay lại (`label=1`) quá ít, SMOTE sẽ tạo thêm các "bản sao thông minh" của họ trong tập `X_train_smote`, `y_train_smote` để model học tốt hơn về nhóm này. **Log của bạn cho thấy SMOTE đã được áp dụng.**
* **Chuẩn Bị "Máy Dò" Sẵn (Model Options Storage):**
    * Trong "Modeling Option 1", chúng ta đã chuẩn bị sẵn các "máy dò" (model) `LightGBM_Opt1`, `RandomForest_Opt1`, và theo yêu cầu mới nhất là cả `XGBoost_Opt1` và `LogisticRegression_Opt1`, mỗi loại với bộ "phụ tùng" (tham số) riêng tùy theo `DEVELOPMENT_MODE` hoặc `PRODUCTION_TIER`. Log cho thấy điều này đã được thực hiện.
* **Giữ Gọn "Công Trường" (Memory Management):**
    * Lưu `X_train_scaled` (dữ liệu gốc, chưa SMOTE) để dùng cho Hyperparameter Tuning, nhằm chống overfitting. Log xác nhận: `Preserving X_train_scaled ... for hyperparameter tuning`.

### Giai Đoạn 2: "Luyện Kim" và "Thử Vàng" (Huấn Luyện & Đánh Giá Model)

Đây là trái tim của "cỗ máy", nơi các "máy dò vàng" được chế tạo và kiểm tra.

* **Hàm "Giám Định Chất Lượng Vàng" (`evaluate_model_performance`):**
    * Dùng để huấn luyện một model trên dữ liệu được cung cấp (thường là `X_train_smote`, `y_train_smote` cho đánh giá ban đầu).
    * Dự đoán trên `X_val_scaled` (dữ liệu kiểm tra chưa từng thấy).
    * Tính các chỉ số "độ tinh khiết" của "vàng" (metrics): AUC-ROC, F1-Score, Log Loss, Brier Score, Precision, Recall cho lớp "quay lại".
    * Vẽ "Ma trận nhầm lẫn": Xem model nhầm ở đâu.

* **Luồng Chế Tạo và Thử Nghiệm "Máy Dò" (Model Pipeline):**
    * **Pipeline Tổng Quát cho mỗi lần đánh giá ban đầu:**
        ```mermaid
        graph LR
            A[Dữ liệu đã sơ chế từ GĐ1] --> B(SMOTE: Cân bằng dữ liệu huấn luyện);
            B --> C[Huấn luyện "Máy Dò" trên X_train_smote];
            C --> D[Đánh giá "Máy Dò" trên X_val_scaled];
            D --> E[Kết quả: Điểm số & Biểu đồ];
        ```
    * **Pipeline cho Hyperparameter Tuning (Tinh chỉnh "Máy Dò"):**
        ```mermaid
        graph LR
            A[Dữ liệu X_train_scaled, y_train gốc từ GĐ1] --> B(RandomizedSearchCV tìm cấu hình tốt nhất);
            B -- Sử dụng Class Weight hoặc Scale Pos Weight --> C[Huấn luyện "Máy Dò" đã tinh chỉnh trên X_train_smote];
            C --> D[Đánh giá "Máy Dò" đã tinh chỉnh trên X_val_scaled];
            D --> E[Kết quả: Model hiệu quả hơn?];
        ```

* **Hai Lựa Chọn "Khai Thác Vàng":**

    * **Lựa Chọn 1: Đào Sâu Ở Những "Mỏ Lớn" Đã Biết (Opt1 Models)**
        * *Mục tiêu:* Kiểm tra nhanh hiệu suất của một số "máy dò" mạnh mẽ (`LightGBM_Opt1`, `RandomForest_Opt1`, `XGBoost_Opt1`, `LogisticRegression_Opt1`) với các cấu hình ban đầu đã được thiết lập sẵn cho từng `DEVELOPMENT_MODE` / `PRODUCTION_TIER`.
        * *Log của bạn cho thấy cả 4 model này đều đã được huấn luyện và đánh giá trên `X_train_smote` và `X_val_scaled`.*

    * **Lựa Chọn 2: "Tuyển Chọn Thợ Mỏ" Giỏi Nhất (Comp Models - Comparative Analysis)**
        * *Mục tiêu:* Tổ chức một "cuộc thi" cho nhiều loại "máy dò" khác nhau (`LogisticRegression_Comp`, `RandomForest_Comp`, `XGBoost_Comp`, `LightGBM_Comp`, `LinearSVC_Comp`, `MLPClassifier_Comp`) để xem loại nào có tiềm năng nhất trên dữ liệu `X_train_smote`.
        * *Log của bạn cho thấy tất cả các model này cũng đã được huấn luyện và đánh giá.*

* **"Bảng Phong Thần" (Model Comparison Summary):**
    * Tổng hợp điểm số AUC-ROC, F1, Precision, Recall, LogLoss, Brier Score của tất cả các model đã thử nghiệm (cả Opt1 và Comp).
    * Log của bạn cho thấy `MLPClassifier_Comp` (AUC 0.6084) là model tốt nhất trước khi tuning trong lần chạy này.

* **Chọn "Thợ Mỏ Vô Địch" (Best Model Before Tuning):** Dựa vào AUC-ROC, `MLPClassifier_Comp` được chọn.

* **"Rèn Lại Công Cụ" Cho "Thợ Mỏ Vô Địch" (Hyperparameter Tuning):**
    * *Mục tiêu:* Tinh chỉnh các "ốc vít" (siêu tham số) của những "thợ mỏ" (model) tiềm năng nhất để họ làm việc hiệu quả hơn nữa.
    * Script của bạn đã chọn `MLPClassifier_Comp` và `RandomForest_Comp` (top 2 model có base name khác nhau trong `PRODUCTION_TIER = 2`) để tuning.
    * **Cải tiến quan trọng:** Tuning được thực hiện trên `X_train_scaled` và `y_train` gốc, đồng thời model được truyền tham số xử lý mất cân bằng (như `class_weight` cho RF hoặc `scale_pos_weight` được tính cho XGB/LGBM, MLP) để chống overfitting trong quá trình cross-validation.
    * `RandomizedSearchCV` được dùng để thử các bộ "ốc vít" khác nhau.
    * **Kết quả tuning trong log:**
        * `RandomForest_Comp_Tuned`: CV AUC 0.6463, Validation AUC **0.6279**. (Cải thiện so với RF_Comp gốc 0.6071)
        * `MLPClassifier_Comp_Tuned`: CV AUC 0.6362, Validation AUC **0.6097**. (Cải thiện nhẹ so với MLP_Comp gốc 0.6084)
    * CV ROC-AUC của cả hai model đã tuned (0.6463 và 0.6362) đều rất hợp lý và gần với validation AUC, cho thấy **vấn đề overfitting trong tuning đã được kiểm soát tốt.**

* **"Công Cụ Tối Thượng" (Final Best Model):**
    * `RandomForest_Comp_Tuned` (AUC 0.6279) được chọn làm model tốt nhất cuối cùng.
    * Model này được lưu lại.
* **"Những Mũi Khoan Quan Trọng Nhất" (Feature Importance):**
    * Biểu đồ độ quan trọng của các "mũi khoan" (đặc trưng) cho model tốt nhất được vẽ.

### Giai Đoạn 3: "Chế Tác Trang Sức" và "Trưng Bày" (Phân Tích Sâu & Kể Chuyện)

Sau khi có "máy dò vàng" tốt nhất, chúng ta sẽ tìm hiểu xem nó "nghĩ" gì và "vàng" của chúng ta có những loại nào.

* **I. "Đọc Vị Máy Dò" (SHAP Analysis):**
    * Sử dụng thư viện `shap` để "giải mã" model `RandomForest_Comp_Tuned`.
    * SHAP cho biết mỗi "đặc điểm" (feature) của khách hàng ảnh hưởng đến quyết định "quay lại" hay "không quay lại" của model như thế nào.
    * Log cho thấy các features quan trọng nhất theo SHAP là `days_since_last_interaction`, `sex`, `unique_categories`, `purchase_rate`, `age`.
* **II. "Phân Loại Vàng" (User Segmentation - K-Means Clustering):**
    * *Mục tiêu:* Gom những khách hàng có hành vi tương tự nhau thành từng "hũ vàng" (cụm) riêng.
    * **Chuẩn bị "vàng" để phân loại:** Lấy các đặc trưng hành vi và nhân khẩu học ở cấp độ người dùng.
    * **Chọn Số "Hũ Vàng" (`optimal_k`):**
        * Script được cấu hình dùng `K_SELECTION_METHOD = "silhouette"`.
        * Tính Silhouette score cho `k` từ 2 đến 7. Log cho thấy:
            * k=2: Sil = 0.156
            * k=3: Sil = 0.185
            * k=4: Sil = **0.190** (làm tròn từ 0.1897 - cao nhất)
            * k=5: Sil = 0.131
            * k=6: Sil = 0.125
            * k=7: Sil = 0.111
        * Script đã **chọn chính xác `optimal_k=4`** dựa trên Silhouette score cao nhất.
    * **Chia "vàng" vào "hũ" (Chạy K-Means):** Sử dụng `k=4` để phân cụm.
    * **Mô Tả "Vàng" Trong Từng "Hũ" (Cluster Profiling):** Xem xét đặc điểm trung bình của khách hàng trong mỗi cụm.
* **III. "Dán Nhãn Cho Từng Hũ Vàng" (Persona Assignment):**
    * Dựa trên đặc điểm của mỗi cụm, đặt cho chúng những cái tên "kêu kêu" (persona) như "🌟👑 VIP Champions", "💔 Dormant & High Churn Risk", v.v.
    * Log cho thấy 4 persona đã được gán cho 4 cụm.
* **IV. "Khai Thác Giá Trị Từ Mỏ Vàng" (Business Insights & Recommendations):**
    * Tổng hợp những phát hiện quan trọng từ model dự đoán, SHAP, và các persona.
    * Đề xuất các chiến lược kinh doanh cụ thể cho từng nhóm khách hàng.
    * Phác họa "Chân Dung Khách Hàng Vàng" (Ideal Customer Profile - ICP).
* **V. Tổng Kết và "Kế Hoạch Mở Rộng Mỏ" (Final Summary & Next Steps).**

## Đối Chiếu Với "Bảng Vàng" Ban Giám Khảo (Barem Chấm Điểm DAZONE 2025)

Phiên bản script này đã có những cải tiến đáng kể và đáp ứng tốt hơn các tiêu chí:

1.  **Forecasting & Model Evaluation (30%):**
    * **Script làm được:** Nhiều model được thử nghiệm (Opt1 và Opt2). Có so sánh, có metrics đầy đủ. Hyperparameter tuning được thực hiện và **vấn đề overfitting trong CV đã được kiểm soát tốt hơn nhiều**. Logic chọn model tốt nhất rõ ràng.
    * **Chấm điểm (ước lượng):** 70-85%. Để đạt điểm cao hơn, có thể thử nghiệm các kỹ thuật ensemble phức tạp hơn, hoặc phân tích sâu hơn về learning curve của model cuối cùng.

2.  **User Segmentation & Personalization Strategy (25%):**
    * **Script làm được:** K-Means được sử dụng. `optimal_k` được chọn một cách linh hoạt (lần này là Silhouette). Có profiling và gán persona. Các đề xuất chiến lược đã bắt đầu hình thành.
    * **Chấm điểm (ước lượng):** 65-80%. Để tối đa, cần làm sâu sắc hơn phân tích đặc điểm từng segment, liên kết chặt chẽ hơn giữa persona và chiến lược hành động (kênh, nội dung, thời điểm cụ thể), và bắt đầu đề cập đến việc đo lường ROI.

3.  **Visualization & Storytelling (20%):**
    * **Script làm được:** Tạo ra nhiều biểu đồ tĩnh quan trọng (target distribution, CM, ROC/PR, feature importance, SHAP, K-Means evaluation, cluster distribution, boxplots, ICP).
    * **Chấm điểm (ước lượng):** 50-65%. Điểm mạnh là có nhiều building blocks. Để cao hơn, cần kể một câu chuyện mạch lạc bằng các biểu đồ này trong bài thuyết trình. Phần "dashboard prescriptive" và "scenario analysis" vẫn là điểm cần phát triển ý tưởng bên ngoài script.

4.  **Business Insights (25%):**
    * **Script làm được:** Insight từ SHAP và các persona đã rõ ràng hơn. Các đề xuất chiến lược dựa trên kết quả phân tích.
    * **Chấm điểm (ước lượng):** 65-80%. Để xuất sắc, cần những insight thực sự "đắt giá", có tính ứng dụng cao và đề xuất cụ thể, có thể kiểm chứng được cho sàn thương mại điện tử.

**Tổng kết:** Script đã được cải thiện đáng kể, đặc biệt là phần tuning. Các phân tích đã đầy đủ hơn và logic hơn.

## Những "Viên Kim Cương" Nên "Đánh Bóng" Cho Buổi Trình Bày (Gợi Ý Trực Quan Hóa)

Dựa trên log chạy `PRODUCTION_TIER = 2` và `K_SELECTION_METHOD = "silhouette"`:

1.  **Tổng Quan Bài Toán:**
    * `target_variable_distribution.png`: Tỷ lệ khách hàng quay lại/không quay lại (nền tảng của bài toán).
2.  **Hành Trình Tìm Kiếm Model Tốt Nhất:**
    * **Bảng So Sánh Model Ban Đầu:** (Trích từ `model_comparison_summary.csv`) Cho thấy sự đa dạng model đã thử và làm nổi bật `MLPClassifier_Comp` là model tốt nhất trước tuning.
    * **Kết Quả Tuning:**
        * Trình bày ngắn gọn quá trình tuning của `RandomForest_Comp` và `MLPClassifier_Comp`, nêu bật CV AUC và Validation AUC để cho thấy sự cải thiện (hoặc không) và việc kiểm soát overfitting.
        * **Confusion Matrix, ROC Curve, Precision-Recall Curve của Model Tốt Nhất Cuối Cùng (`RandomForest_Comp_Tuned`):** Đây là bằng chứng về hiệu suất của model bạn chọn.
    * `feature_importances_RandomForest_Comp_Tuned.png`: Các yếu tố model này cho là quan trọng.
3.  **"Bóc Tách" Model Với SHAP:**
    * `shap_summary_plot_RandomForest_Comp_Tuned.png` (dot plot): Tác động của các feature lên dự đoán.
    * `shap_bar_plot_RandomForest_Comp_Tuned.png`: Feature nào ảnh hưởng mạnh nhất theo SHAP.
4.  **Khám Phá Các Nhóm Khách Hàng:**
    * `kmeans_silhouette_scores.png` (và có thể cả `kmeans_elbow_method.png` để so sánh): Giải thích tại sao chọn `k=4` (dựa trên Silhouette score cao nhất).
    * `user_segment_distribution.png` (cho `k=4`): Quy mô của từng phân khúc.
    * `cluster_profiles_boxplots.png` (cho `k=4`): So sánh trực quan các đặc điểm chính (loyalty, engagement, purchase_rate, total_interactions, churn_risk) giữa 4 phân khúc.
    * **Bảng Tổng Hợp Chân Dung Persona (4 personas):** Trình bày ngắn gọn đặc điểm nổi bật và tên persona của từng cụm.
5.  **Khách Hàng Lý Tưởng (ICP):**
    * `ideal_customer_profile_age_dist.png` và `ideal_customer_profile_sex_dist.png`. Có thể bổ sung thêm biểu đồ về ngành nghề/công việc nếu dữ liệu này chất lượng.
6.  **Slide Chiến Lược:** Dựa trên Persona và ICP, đề xuất các hành động cụ thể.

**Lưu ý quan trọng cho thuyết trình:**
* **Câu chuyện mạch lạc:** Sắp xếp các biểu đồ để dẫn dắt người nghe qua quá trình phân tích của bạn, từ hiểu bài toán, xây dựng model, đến khám phá insight và đề xuất giải pháp.
* **Tập trung vào ý nghĩa:** Đừng chỉ trình bày biểu đồ, hãy giải thích nó cho thấy điều gì và ý nghĩa của nó đối với bài toán của sàn thương mại điện tử.
* **Kết nối với barem:** Ngầm liên kết các phần trình bày với các tiêu chí của ban giám khảo.

## Lời Dặn Dò Từ "Trưởng Đoàn Thám Hiểm"

Đội của chúng ta đã có một "cỗ máy khai khoáng" rất mạnh mẽ và nhiều "báu vật" đã được tìm thấy! Lần chạy PRODUCTION này cho thấy script đã ổn định hơn, logic chặt chẽ hơn và các cải tiến đã phát huy tác dụng.

Hãy nhớ, mục tiêu của DAZONE không chỉ là những con số AUC cao ngất, mà còn là khả năng biến dữ liệu thành những câu chuyện có ý nghĩa, những quyết định kinh doanh thông minh cho sàn thương mại điện tử. Hãy tự tin trình bày những khám phá của đội! Chúc cả đội thành công rực rỡ! 🌟
