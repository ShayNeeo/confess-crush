# README: Hành Trình Khai Phá Dữ Liệu Khách Hàng Sàn TMĐT - Sứ Mệnh DAZONE 2025 Vòng 2.2

Chào các chiến binh dữ liệu của đội! Chúng ta đang đứng trước một thử thách lớn từ "Sếp Tổng" tại cuộc thi DAZONE 2025: làm sao để sàn thương mại điện tử của chúng ta giữ chân được khách hàng, khiến họ quay lại mua sắm? File Python này chính là "bảo bối" và "kim chỉ nam" của đội trong hành trình khám phá những bí mật ẩn sâu trong dữ liệu khách hàng. Hãy cùng nhau giải mã nó và mang về chiến thắng nhé! 🚀

## Mục Lục

1.  [Nhiệm Vụ Bí Mật: Hiểu Lòng Khách Hàng, Giữ Chân Doanh Thu](#nhiệm-vụ-bí-mật-hiểu-lòng-khách-hàng-giữ-chân-doanh-thu)
2.  [Kích Hoạt "Cỗ Máy Thời Gian": Hướng Dẫn Vận Hành Script](#kích-hoạt-cỗ-máy-thời-gian-hướng-dẫn-vận-hành-script)
3.  [Giải Mã "Cỗ Máy Thời Gian": Cấu Trúc Script và Câu Chuyện Đằng Sau](#giải-mã-cỗ-máy-thời-gian-cấu-trúc-script-và-câu-chuyện-đằng-sau)
    * [Chương 1: Thu Thập Thông Tin Tình Báo - Chuẩn Bị Dữ Liệu](#chương-1-thu-thập-thông-tin-tình-báo---chuẩn-bị-dữ-liệu)
    * [Chương 2: Chế Tạo Quả Cầu Tiên Tri - Xây Dựng và Đánh Giá Model](#chương-2-chế-tạo-quả-cầu-tiên-tri---xây-dựng-và-đánh-giá-model)
    * [Chương 3: Đọc Vị Quả Cầu & Phân Loại "Chiến Binh" - Phân Tích Sâu và Tạo Chân Dung Khách Hàng](#chương-3-đọc-vị-quả-cầu--phân-loại-chiến-binh---phân-tích-sâu-và-tạo-chân-dung-khách-hàng)
4.  [Đáp Án Cho "Sếp Tổng": Đối Chiếu Với Barem Chấm Điểm DAZONE 2025](#đáp-án-cho-sếp-tổng-đối-chiếu-với-barem-chấm-điểm-dazone-2025)
5.  [Báo Cáo Chiến Công Lên "Bộ Chỉ Huy": Gợi Ý Trực Quan Hóa Cho Bài Thuyết Trình](#báo-cáo-chiến-công-lên-bộ-chỉ-huy-gợi-ý-trực-quan-hóa-cho-bài-thuyết-trình)
6.  [Thông Điệp Từ "Chỉ Huy Trưởng" Đội Đặc Nhiệm](#thông-điệp-từ-chỉ-huy-trưởng-đội-đặc-nhiệm)

## Nhiệm Vụ Bí Mật: Hiểu Lòng Khách Hàng, Giữ Chân Doanh Thu

Sàn thương mại điện tử của chúng ta có hàng triệu khách hàng. Nhưng, ai trong số họ sẽ thực sự gắn bó và quay lại mua hàng tại một gian hàng cụ thể trong 6 tháng tới? Đây không chỉ là một câu hỏi, mà là một "nhiệm vụ tối mật" ảnh hưởng trực tiếp đến doanh thu và sự phát triển bền vững. Nếu chúng ta biết được điều này, chúng ta có thể:
* Chăm sóc đúng người, đúng lúc.
* Tung ra các chương trình khuyến mãi hiệu quả hơn.
* Biến khách hàng mới thành khách hàng trung thành.

"Cỗ máy thời gian" (script Python này) sẽ giúp chúng ta giải quyết nhiệm vụ này bằng cách:
1.  **"Thu thập và làm sạch các mảnh ghép quá khứ"**: Chuẩn bị dữ liệu giao dịch và thông tin khách hàng.
2.  **"Chế tạo các phiên bản quả cầu tiên tri"**: Xây dựng các mô hình dự đoán.
3.  **"Kiểm tra độ chính xác của từng quả cầu"**: Đánh giá model nào "phán" chuẩn nhất.
4.  **"Nhận diện các nhóm chiến binh mua sắm"**: Phân loại khách hàng dựa trên hành vi và đặc điểm.
5.  **"Vạch ra kế hoạch tác chiến"**: Đề xuất các chiến lược kinh doanh thông minh.

## Kích Hoạt "Cỗ Máy Thời Gian": Hướng Dẫn Vận Hành Script

Để "cỗ máy" của chúng ta bắt đầu hành trình xuyên không về quá khứ và dự đoán tương lai, cả đội cần chuẩn bị:
1.  **"Trang bị cá nhân" (Môi trường):** Máy tính được cài Python và các "vũ khí" cần thiết (thư viện) như `pandas`, `numpy` (để xử lý số liệu), `matplotlib`, `seaborn` (để vẽ biểu đồ), `scikit-learn` (bộ công cụ xây model), `imblearn` (để cân bằng lực lượng các nhóm khách hàng), `xgboost`, `lightgbm` (2 "chiến mã" mạnh mẽ), và `shap` (kính lúp soi thấu model).
2.  **"Bản đồ kho báu cổ" (Dữ liệu đầu vào):** Các file CSV đã được "lau chùi" từ vòng trước hoặc từ script `data_cleaning.py`, cất giữ trong `cleaning_results/cleaned_data/`:
    * `competition_train_features.csv`: Thông tin huấn luyện các "nhà tiên tri".
    * `competition_test_features.csv`: Thông tin để "thử tài" các "nhà tiên tri".
    * `cleaned_user_info.csv`: Hồ sơ chi tiết của từng khách hàng.
3.  **"Niệm thần chú" (Chạy script):** Thực thi file `DAZONE2025_R2.2_Main_Analysis.py`.
4.  **"Chiến lợi phẩm" (Kết quả):** Mọi "bí mật" và "kho báu" sẽ được tập hợp tại thư mục `round_2.2`:
    * `model_outputs`: Nơi cất giữ các "quả cầu tiên tri" mạnh nhất.
    * `segmentation_outputs`: "Hồ sơ mật" của từng nhóm khách hàng.
    * `shap_outputs`: "Bản giải mã" cách "quả cầu" đưa ra dự đoán.
    * `visualizations_from_main_analysis`: "Album ảnh" ghi lại những khám phá quan trọng.
    * `logs`: "Biên niên sử" của cuộc hành trình.

## Giải Mã "Cỗ Máy Thời Gian": Cấu Trúc Script và Câu Chuyện Đằng Sau

Hành trình của chúng ta được chia thành 3 chương lớn, mỗi chương hé lộ một phần của bức tranh toàn cảnh.

### Chương 1: Thu Thập Thông Tin Tình Báo - Chuẩn Bị Dữ Liệu

Trước mọi trận đánh lớn, khâu tình báo và chuẩn bị luôn là quan trọng nhất. Ở đây, "tình báo" chính là dữ liệu khách hàng của sàn thương mại điện tử.

* **Triệu Tập "Đội Quân" Thư Viện:** Gọi các thư viện cần thiết.
* **Thiết Lập "Chiến Trường" (Cấu hình):**
    * `DEVELOPMENT_MODE`: Chế độ "diễn tập" (`True`) với ít quân hơn (dữ liệu mẫu) để nhanh chóng kiểm tra chiến thuật, hoặc "ra trận thật" (`False`) với toàn bộ lực lượng. *Log gần nhất của đội ta (18:04:02) đang ở chế độ "ra trận thật".*
    * `PRODUCTION_TIER`: Khi "ra trận thật", chọn cấp độ "dốc toàn lực" (Tier 2 - kỹ lưỡng) hay "đánh nhanh thắng nhanh" (Tier 1). *Log gần nhất đang ở Tier 2.*
    * `RANDOM_STATE`: "Con số định mệnh" (ví dụ `9` như trong log) để mọi quyết định ngẫu nhiên (chia quân, chọn mẫu) đều theo một kịch bản, giúp chúng ta dễ dàng xem lại và so sánh các "trận đánh".
    * `K_SELECTION_METHOD`: "Chiến thuật chọn tướng" cho việc chia nhóm khách hàng ("silhouette" hoặc "elbow"). *Log gần nhất đang dùng "silhouette".*
    * Màu sắc: Chọn "màu cờ sắc áo" (màu đỏ) cho các biểu đồ báo cáo.
* **Xây Dựng "Hậu Cần" (Tạo thư mục output, Logging):** Chuẩn bị nơi lưu trữ "chiến lợi phẩm" và ghi chép lại toàn bộ diễn biến.
* **Tiếp Nhận "Thông Điệp Mật Mã" (Tải dữ liệu):** Đọc dữ liệu từ các file CSV.
* **Đọc Lướt "Thông Điệp" (EDA ban đầu):** Vẽ biểu đồ tròn xem tỷ lệ khách hàng có khả năng quay lại (`label = 1`) và không (`label = 0`). Bước này cho ta biết "kẻ địch" chính của chúng ta (khách hàng không quay lại) có đông không.
* **"Giải Mã" và "Sắp Xếp" Thông Tin (Tiền xử lý dữ liệu cho model):**
    * Hàm `preprocess_for_modeling`: "Phiên dịch viên" và "sắp xếp viên" của đội.
        * Xử lý các thông tin còn thiếu (NaN), mã hóa thông tin dạng chữ thành dạng số, xử lý các con số "kỳ lạ" (vô cực).
    * **Chia "Bản Đồ Chiến Lược" (Train/Validation Split):** Chia dữ liệu huấn luyện thành khu vực "huấn luyện binh sĩ" (`X_train`, `y_train`) và khu vực "thử nghiệm vũ khí" (`X_val`, `y_val`).
    * **"Trang Bị Đồng Phục" Cho "Binh Sĩ" (StandardScaler):** Đưa các đặc điểm số về cùng một "chuẩn", tránh việc "binh sĩ" này quá to con so với "binh sĩ" khác.
    * **"Tuyển Thêm Quân" Cho Phe Yếu (SMOTE):** Nếu nhóm khách hàng quay lại quá ít, SMOTE sẽ "chiêu mộ" thêm các "tân binh" ảo có đặc điểm tương tự để lực lượng hai bên cân bằng hơn, giúp "quả cầu tiên tri" học được nhiều hơn về nhóm ít ỏi này. *Log cho thấy SMOTE đã tạo ra tập `X_train_smote` đông đảo hơn.*
* **Chuẩn Bị Sẵn Các "Mẫu Quả Cầu" (Model Options Storage):**
    * Trong "Chiến Thuật 1", chúng ta đã chuẩn bị sẵn các "mẫu quả cầu" `LightGBM_Opt1`, `RandomForest_Opt1`, và theo cập nhật mới nhất là `XGBoost_Opt1`, `LogisticRegression_Opt1`. Mỗi loại có "công thức chế tạo" (tham số) riêng, phù hợp với từng cấp độ "tác chiến".
* **Dọn Dẹp "Chiến Trường" (Memory Management):**
    * Lưu lại `X_train_scaled` (dữ liệu huấn luyện gốc, chưa SMOTE) để dùng cho việc "mài giũa quả cầu" (Hyperparameter Tuning), giúp "quả cầu" không bị "ảo tưởng sức mạnh".

### Chương 2: "Chế Tạo Quả Cầu Tiên Tri" - Xây Dựng và Đánh Giá Model

Đây là chương hấp dẫn nhất! Chúng ta sẽ tạo ra những "quả cầu" có khả năng nhìn thấu tương lai và xem "quả cầu" nào "phán" chuẩn nhất.

* **Hàm "Thẩm Định Quả Cầu" (`evaluate_model_performance`):**
    * Dùng để "thôi miên" (huấn luyện) "quả cầu" (model) bằng dữ liệu `X_train_smote`.
    * Yêu cầu "quả cầu" dự đoán kết quả trên `X_val_scaled`.
    * Chấm điểm "quả cầu" bằng các thước đo: AUC-ROC (khả năng phân biệt tổng thể), F1-Score (cân bằng giữa tìm đúng và không sót khách hàng mục tiêu), Log Loss, Brier Score (các hình thức "phạt" nếu đoán sai và quá tự tin), Precision, Recall (cho nhóm khách hàng quay lại).
    * Vẽ "Ma trận Lỗi Lầm": Xem "quả cầu" hay nhầm lẫn ở đâu.

* **Luồng Chế Tạo và Thử Nghiệm "Quả Cầu":**
    * **Quy Trình Chuẩn cho mỗi "Quả Cầu" được đánh giá ban đầu:**
        ```mermaid
        graph LR
            A[Dữ liệu huấn luyện đã chuẩn bị] --> B(SMOTE Cân bằng lực lượng);
            B --> C[Thôi miên Quả Cầu trên X_train_smote];
            C --> D[Thử tài Quả Cầu trên X_val_scaled];
            D --> E[Kết quả: Điểm số và Biểu đồ];
        ```
    * **Quy Trình "Mài Giũa Quả Cầu" (Hyperparameter Tuning):**
        ```mermaid
        graph LR
            A[Dữ liệu huấn luyện X_train_scaled và y_train gốc] --> B(RandomizedSearchCV tìm công thức mài giũa tốt nhất);
            B -- Áp dụng Class Weight hoặc Scale Pos Weight để Quả Cầu tự cân bằng --> C[Thôi miên Quả Cầu đã mài giũa trên X_train_smote];
            C --> D[Thử tài Quả Cầu đã mài giũa trên X_val_scaled];
            D --> E[Kết quả: Quả Cầu có tinh xảo hơn không?];
        ```

* **Hai "Xưởng Rèn Quả Cầu" Chính:**

    * **Xưởng 1: Tập Trung Vào Các "Pháp Sư" Danh Tiếng (Opt1 Models)**
        * *Chiến thuật:* "Mời" các "pháp sư" nổi tiếng (`LightGBM_Opt1`, `RandomForest_Opt1`, `XGBoost_Opt1`, `LogisticRegression_Opt1`) đến "thử sức" với những "bộ phép" (tham số) cơ bản đã chuẩn bị cho từng cấp độ "khẩn cấp" (`DEVELOPMENT_MODE` / `PRODUCTION_TIER`).
        * *Kết quả trong log (Tier 2):* `MLPClassifier_Comp` (AUC 0.6084) là "pháp sư" ấn tượng nhất ở vòng sơ loại, nhưng trong Option 1, `LogisticRegression_Opt1` (AUC 0.5985) và `RandomForest_Opt1` (AUC 0.5827) cũng cho thấy tiềm năng nhất định (lưu ý là log cho `PRODUCTION_TIER = 2` mới nhất của bạn, các model Opt1 có AUC hơi thấp hơn so với Opt2).

    * **Xưởng 2: "Đại Hội Võ Lâm" của các "Pháp Sư" (Comp Models - Comparative Analysis)**
        * *Chiến thuật:* Tổ chức một "đại hội" quy tụ nhiều "pháp sư" từ các "môn phái" khác nhau (`LogisticRegression_Comp`, `RandomForest_Comp`, `XGBoost_Comp`, `LightGBM_Comp`, `LinearSVC_Comp`, `MLPClassifier_Comp`) để xem ai "cao tay" nhất khi cùng giải một bài toán trên dữ liệu `X_train_smote`.
        * *Kết quả trong log (Tier 2):* `MLPClassifier_Comp` (AUC 0.6084) tạm thời dẫn đầu "đại hội".

* **"Bảng Vàng Vinh Danh" (Model Comparison Summary):**
    * Tổng hợp điểm số của tất cả các "pháp sư".
    * Log của bạn cho thấy `MLPClassifier_Comp` (AUC 0.6084) là "Trạng Nguyên" trước khi "mài giũa".

* **Chọn "Pháp Sư Đại Diện" (Best Model Before Tuning):** `MLPClassifier_Comp` được chọn.

* **"Truyền Thụ Bí Kíp" Cho Các "Pháp Sư" (Hyperparameter Tuning):**
    * *Mục tiêu:* Giúp các "pháp sư" hàng đầu (`MLPClassifier_Comp` và `RandomForest_Comp` trong log Tier 2) hoàn thiện "phép thuật" của mình bằng cách thử các "biến thể thần chú" (siêu tham số) khác nhau.
    * **Cải tiến quan trọng:** "Buổi luyện tập" này diễn ra trên dữ liệu gốc `X_train_scaled` và `y_train`, các "pháp sư" được dạy cách tự cân bằng sức mạnh (qua `class_weight` hoặc `scale_pos_weight`) để tránh "tẩu hỏa nhập ma" (overfitting).
    * `RandomizedSearchCV` là "sư phụ" hướng dẫn tìm "biến thể thần chú" tốt nhất.
    * **Kết quả "luyện công" trong log (Tier 2):**
        * `RandomForest_Comp_Tuned`: CV AUC 0.6463 (khá hứa hẹn trên tập luyện), Validation AUC **0.6279**. (Cải thiện so với bản gốc 0.6071!)
        * `MLPClassifier_Comp_Tuned`: CV AUC 0.6362, Validation AUC **0.6097**. (Cải thiện nhẹ so với bản gốc 0.6084).
    * CV ROC-AUC của cả hai model đã "mài giũa" đều hợp lý và gần với validation AUC, cho thấy **không bị "ảo tưởng sức mạnh" nghiêm trọng.**

* **"Quả Cầu Tiên Tri Hoàn Hảo Nhất" (Final Best Model):**
    * `RandomForest_Comp_Tuned` (AUC 0.6279) được chọn làm "Bảo vật trấn phái".
    * "Bảo vật" này được cất giữ cẩn thận.
* **"Thần Chú Quyền Năng Nhất" (Feature Importance):**
    * Biểu đồ cho thấy những "yếu tố" (đặc trưng) nào có sức mạnh lớn nhất trong "quả cầu" này.

### Chương 3: "Đọc Vị Quả Cầu" & Phân Loại "Chiến Binh" - Phân Tích Sâu và Tạo Chân Dung Khách Hàng

Khi đã có "Bảo vật trấn phái", chúng ta sẽ tìm hiểu cách nó hoạt động và dùng nó để "nhìn thấu" các nhóm khách hàng.

* **I. "Soi Gương Ma Thuật" - Hiểu Cách "Quả Cầu" Suy Nghĩ (SHAP Analysis):**
    * Dùng `shap` để "đọc vị" `RandomForest_Comp_Tuned`.
    * SHAP giải thích tại sao "quả cầu" lại dự đoán một khách hàng sẽ quay lại hoặc không, dựa trên từng đặc điểm của họ.
    * Log cho thấy các "manh mối" quan trọng nhất là: `days_since_last_interaction`, `sex`, `unique_categories`, `purchase_rate`, `age`.
* **II. "Phân Loại Chiến Binh" Theo Đặc Tính (User Segmentation - K-Means Clustering):**
    * *Mục tiêu:* Tập hợp những khách hàng ("chiến binh") có "phong cách chiến đấu" (hành vi) và "lý lịch" (đặc điểm) giống nhau vào cùng một "biệt đội".
    * **Chuẩn bị "hồ sơ chiến binh":** Sử dụng các đặc trưng hành vi và nhân khẩu học tổng hợp ở cấp độ người dùng.
    * **Chọn Số "Biệt Đội" Tối Ưu (`optimal_k`):**
        * Script được cấu hình dùng `K_SELECTION_METHOD = "silhouette"`.
        * Tính Silhouette score cho `k` từ 2 đến 7. Log cho thấy:
            * k=2 (0.156), k=3 (0.185), k=4 (**0.190** - cao nhất), k=5 (0.131), k=6 (0.125), k=7 (0.111).
        * Script đã **chọn chính xác `optimal_k=4`** theo Silhouette score.
    * **Biên Chế "Biệt Đội" (Chạy K-Means):** Dùng `k=4` để phân chia.
    * **Báo Cáo Đặc Điểm Từng "Biệt Đội" (Cluster Profiling):** Xem xét đặc điểm trung bình của các "chiến binh" trong mỗi "biệt đội".
* **III. "Đặt Biệt Danh" Cho Các "Biệt Đội" (Persona Assignment):**
    * Dựa trên đặc điểm của mỗi "biệt đội", đặt cho họ những "biệt danh" dễ nhớ (ví dụ: "🌟👑 VIP Champions", "💔 Dormant & High Churn Risk", v.v.).
    * Log cho thấy 4 "biệt danh" đã được gán cho 4 "biệt đội".
* **IV. "Kế Sách Tác Chiến" Cho Từng "Biệt Đội" (Business Insights & Recommendations):**
    * Tổng hợp những "tin tình báo" quan trọng từ "quả cầu tiên tri", SHAP, và các "biệt đội".
    * Đề xuất "kế sách" kinh doanh cụ thể cho từng "biệt đội" trên sàn thương mại điện tử.
    * Phác họa "Chân Dung Chiến Binh Vàng" (Ideal Customer Profile - ICP).
* **V. Tổng Kết "Chiến Dịch" và "Kế Hoạch Tương Lai" (Final Summary & Next Steps).**

## Đối Chiếu Với "Bảng Vàng" Ban Giám Khảo (Barem Chấm Điểm DAZONE 2025)

Phiên bản script này, khi chạy ở PRODUCTION TIER 2, đã thể hiện nhiều điểm mạnh:

1.  **Forecasting & Model Evaluation (30%):**
    * **Script làm được:** Rất nhiều model được thử nghiệm. So sánh rõ ràng. Metrics đầy đủ. Hyperparameter tuning đã thực sự chạy và có cải thiện model (RF_Comp_Tuned tốt hơn RF_Comp). Vấn đề overfitting trong CV đã được kiểm soát tốt.
    * **Chấm điểm (ước lượng):** 75-90%. Để tối đa, cần phân tích sâu hơn nữa về lý do chọn từng model để thử nghiệm, và có thể là các kỹ thuật kết hợp model tiên tiến.

2.  **User Segmentation & Personalization Strategy (25%):**
    * **Script làm được:** K-Means với `optimal_k` được chọn linh hoạt bằng Silhouette. Có profiling và gán Persona. Các đề xuất chiến lược có cơ sở.
    * **Chấm điểm (ước lượng):** 70-85%. Để tối đa, cần làm chiến lược cá nhân hóa cực kỳ chi tiết cho từng persona (kênh, nội dung, thời điểm, KPI đo lường, cân nhắc ROI).

3.  **Visualization & Storytelling (20%):**
    * **Script làm được:** Tạo ra bộ sưu tập biểu đồ tĩnh phong phú, làm nền tảng tốt cho việc kể chuyện.
    * **Chấm điểm (ước lượng):** 50-70%. Điểm cộng cho sự đa dạng. Để cao hơn, bài thuyết trình cần sâu chuỗi chúng thành một câu chuyện kinh doanh hấp dẫn. "Dashboard prescriptive" và "scenario analysis" vẫn là những mục nâng cao cần ý tưởng trình bày riêng.

4.  **Business Insights (25%):**
    * **Script làm được:** Insight từ SHAP (ví dụ: `days_since_last_interaction`, `sex` quan trọng) và 4 persona rõ ràng cung cấp nhiều hiểu biết giá trị. Các đề xuất có tính ứng dụng.
    * **Chấm điểm (ước lượng):** 70-85%. Để xuất sắc, cần những insight mang tính đột phá, độc đáo cho ngành TMĐT và có kế hoạch kiểm định các insight đó.

**Tổng kết:** Script đã được cải tiến mạnh mẽ, giải quyết các vấn đề cốt lõi và cho ra kết quả phân tích đáng tin cậy hơn, phù hợp với yêu cầu của một cuộc thi lớn.

## Những "Viên Kim Cương" Nên "Đánh Bóng" Cho Buổi Trình Bày (Gợi Ý Trực Quan Hóa)

Dựa trên log chạy `PRODUCTION_TIER = 2` và `K_SELECTION_METHOD = "silhouette"` (kết quả `optimal_k=4`):

1.  **Câu Chuyện Mở Đầu - "Thử Thách Của Sàn TMĐT":**
    * `target_variable_distribution.png`: Đặt vấn đề về tỷ lệ khách hàng không quay lại.
2.  **Hành Trình "Rèn Giũa Quả Cầu Tiên Tri":**
    * **Bảng So Sánh Model Ban Đầu:** Nêu bật `MLPClassifier_Comp` là ứng viên sáng giá ban đầu.
    * **Tóm Tắt Kết Quả Tuning:**
        * Cho thấy `RandomForest_Comp_Tuned` đã cải thiện như thế nào so với bản gốc (AUC từ 0.6071 lên 0.6279).
        * Cho thấy `MLPClassifier_Comp_Tuned` (AUC 0.6097) dù được tune nhưng không vượt qua được RF đã tune.
    * **"Bằng Chứng Sức Mạnh" của `RandomForest_Comp_Tuned`:**
        * `confusion_matrix_RandomForest_Comp_Tuned.png`
        * ROC Curve và Precision-Recall Curve (có thể vẽ riêng cho model này, hoặc trích từ `roc_curves_comparative_models.png` và `pr_curves_comparative_models.png` nhưng chỉ làm nổi bật đường của model tốt nhất).
    * `feature_importances_RandomForest_Comp_Tuned.png`: Những "thần chú" model này dựa vào.
3.  **"Bên Trong Quả Cầu" - Giải Mã Với SHAP:**
    * `shap_summary_plot_RandomForest_Comp_Tuned.png` (dot plot).
    * `shap_bar_plot_RandomForest_Comp_Tuned.png`.
4.  **"Bản Đồ Các Nhóm Khách Hàng Chiến Lược":**
    * `kmeans_silhouette_scores.png` (và có thể cả `kmeans_elbow_method.png`): Giải thích tại sao chọn `k=4`.
    * `user_segment_distribution.png` (cho `k=4`): Quy mô của 4 "biệt đội".
    * `cluster_profiles_boxplots.png` (cho `k=4`): So sánh trực quan các đặc điểm cốt lõi của 4 "biệt đội".
    * **Slide Chân Dung Persona (4 personas):** Mỗi persona một slide (hoặc 2 persona/slide) với tên, đặc điểm nổi bật (trích từ `cluster_profiles_combined.csv`), và gợi ý chiến lược chính.
5.  **"Chân Dung Vàng" - Khách Hàng Lý Tưởng:**
    * `ideal_customer_profile_age_dist.png`
    * `ideal_customer_profile_sex_dist.png`.
6.  **Slide "Kế Sách Vàng":** Tổng hợp các đề xuất chiến lược quan trọng nhất, liên kết với model insights và personas.

**Lời khuyên vàng ngọc cho đội:**
* **Storytelling is Key:** Hãy dệt nên một câu chuyện hấp dẫn xoay quanh việc sàn TMĐT làm thế nào để thấu hiểu và giữ chân khách hàng, với đội của bạn là những người giải mã.
* **Focus on "So What?":** Với mỗi biểu đồ, mỗi kết quả, luôn trả lời câu hỏi: "Điều này có ý nghĩa gì với việc kinh doanh của sàn TMĐT? Chúng ta nên làm gì tiếp theo?"
* **Đơn Giản Hóa:** Ngay cả những phân tích phức tạp cũng cần được trình bày một cách dễ hiểu. Các bạn trong đội hãy đảm bảo tất cả cùng hiểu để có thể trình bày trôi chảy.

## Lời Dặn Dò Từ "Chỉ Huy Trưởng" Đội Đặc Nhiệm

Các chiến binh, chúng ta đã có một "bộ chỉ huy tác chiến" (script) rất chi tiết và hiệu quả. Log chạy PRODUCTION TIER 2 mới nhất cho thấy những cải tiến quan trọng đã được áp dụng thành công. "Quả cầu tiên tri" của chúng ta đã được "mài giũa" cẩn thận, và các "biệt đội khách hàng" đã được "điểm danh".

Phần còn lại là ở tài "ngoại giao" và "thuyết trình" của cả đội để báo cáo những "chiến công" này lên "Bộ Chỉ Huy Tối Cao" DAZONE. Hãy nhớ, dữ liệu chỉ thực sự có giá trị khi nó dẫn đến hành động và tạo ra kết quả.

Chúc đội chúng ta tự tin, tỏa sáng và giành chiến thắng! 💪🎉
