# DAZONE 2025 Vòng 2.2: Dự đoán Khả năng Quay lại của Người dùng & Phân khúc Người dùng

**Mục tiêu:** Dự đoán xác suất người dùng quay lại một cửa hàng và phát triển các chiến lược phân khúc người dùng để cá nhân hóa tương tác. Dự án này bao gồm làm sạch dữ liệu, xây dựng đặc trưng (feature engineering), mô hình hóa dự đoán, diễn giải mô hình bằng SHAP, và phân khúc khách hàng bằng thuật toán gom cụm.

**Tác giả:** AI Assistant
**Ngày:** 2025-06-01

## Các Tính năng Chính của Script:

* **Mô hình hóa Dự đoán:** Huấn luyện và đánh giá nhiều mô hình phân loại để dự đoán khả năng người dùng quay lại.
* **Phân khúc Người dùng:** Sử dụng thuật toán gom cụm K-Means để xác định các phân khúc người dùng riêng biệt.
* **Gán Chân dung Thông minh:** Tự động gán các chân dung (personas) có ý nghĩa cho từng phân khúc người dùng dựa trên đặc điểm của họ.
* **Xây dựng Đặc trưng Nâng cao:** Tạo ra các đặc trưng mới từ dữ liệu hiện có, bao gồm:
    * Phân tích nâng cao thông tin `điện thoại` và `nhà mạng` (tính hợp lệ, loại, thị phần).
    * Các đặc trưng tương tác (ví dụ: `tuổi_x_tỷ_lệ_mua_hàng`, `nghề_nghiệp_x_mức_độ_hoạt_động`).
    * Các tỷ lệ hành vi và điểm số tổng hợp.
* **Diễn giải Mô hình:** Sử dụng phân tích SHAP (SHapley Additive exPlanations) để hiểu sự đóng góp của các đặc trưng vào dự đoán của mô hình.
* **Chế độ Thực thi Có thể Cấu hình:**
    * `DEVELOPMENT_MODE`: Dành cho việc lặp lại nhanh với lấy mẫu dữ liệu và giảm độ phức tạp của mô hình.
    * `PRODUCTION_MODE` (Tier 1 & 2): Dành cho phân tích toàn bộ dữ liệu với các mức tối ưu hóa khác nhau cho thời gian chạy và tính toàn diện.
* **Ghi log Chi tiết:** Xuất tiến trình và kết quả ra cả console và tệp log.
* **Đầu ra Toàn diện:** Tạo biểu đồ trực quan, tệp CSV cho việc so sánh mô hình, độ quan trọng của đặc trưng, hồ sơ cụm, và phân tích chân dung.

## Các Bản sửa lỗi Gần đây được Triển khai:

* **Giải quyết Lỗi SHAP:** Cải thiện việc xác thực cấu trúc dữ liệu, làm sạch và xử lý lỗi cho phân tích SHAP, bao gồm xử lý mạnh mẽ các mảng giá trị SHAP 3D.
* **Ngưỡng NaN cho Gán Chân dung:** Triển khai xử lý NaN mạnh mẽ cho việc tính toán ngưỡng phần trăm trong gán chân dung, đảm bảo định nghĩa chân dung ổn định và đáng tin cậy hơn.

## Cấu trúc Thư mục:

Giả định script được chạy từ một thư mục gốc của dự án với cấu trúc tương tự như sau:

.
├── your_script_name.py                 # Script này
├── cleaning_results/
│   └── cleaned_data/                   # ĐẦU VÀO: Thư mục chứa các tệp dữ liệu CSV đã làm sạch
│       ├── competition_train_features.csv
│       ├── ... (các tệp CSV đầu vào khác)
└── round_2.2/                          # ĐẦU RA: Thư mục chứa tất cả các kết quả được tạo ra
├── round_2.2.txt
├── round_2_2_analysis_results.png
└── ... (các tệp CSV và text khác)


## Điều kiện Tiên quyết & Thư viện Phụ thuộc:

Đảm bảo các thư viện Python sau đã được cài đặt:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* imbalanced-learn (cho SMOTE)
* xgboost
* lightgbm
* shap (tùy chọn, nhưng được khuyến nghị để phân tích đầy đủ độ quan trọng của đặc trưng)

Bạn thường có thể cài đặt chúng bằng pip:
`pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost lightgbm shap`

## Cấu hình:

Hành vi của script có thể được cấu hình bằng hai biến toàn cục ở đầu tệp:

1.  **`DEVELOPMENT_MODE`** (Boolean):
    * Đặt thành `True` để kiểm thử và phát triển nhanh. Chế độ này cho phép lấy mẫu dữ liệu, sử dụng các tham số mô hình đơn giản hơn và giảm số lần lặp để thực thi nhanh hơn (dự kiến 15-30 phút).
    * Đặt thành `False` để phân tích đầy đủ trên toàn bộ tập dữ liệu.

2.  **`PRODUCTION_TIER`** (Số nguyên: 1 hoặc 2; áp dụng nếu `DEVELOPMENT_MODE = False`):
    * **Tier 1**: Tối ưu hóa cho thời gian chạy mục tiêu <1 giờ. Sử dụng toàn bộ dữ liệu với các tham số được tối ưu hóa và quy trình huấn luyện được tinh gọn.
    * **Tier 2**: Hướng đến sự cân bằng giữa độ chính xác và tốc độ, với thời gian chạy dự kiến ~2 giờ (tuy nhiên, thời gian chạy thực tế có thể thay đổi tùy thuộc vào phần cứng). Sử dụng toàn bộ dữ liệu với quá trình huấn luyện mô hình và tinh chỉnh siêu tham số toàn diện hơn.

## Chạy Script:

1.  Đặt các tệp CSV đầu vào đã làm sạch của bạn vào thư mục `cleaning_results/cleaned_data/` (hoặc cập nhật biến `data_path` trong script nếu dữ liệu của bạn được đặt ở nơi khác).
2.  Cấu hình `DEVELOPMENT_MODE` và `PRODUCTION_TIER` ở đầu script nếu cần.
3.  Thực thi script từ terminal của bạn:
    ```bash
    python your_script_name.py
    ```
    (Thay thế `your_script_name.py` bằng tên thực tế của tệp Python).

## Tệp Dữ liệu Đầu vào:

Script mong đợi các tệp CSV đã làm sạch sau (như được định nghĩa trong từ điển `files`):

* `competition_train_features.csv`
* `competition_test_features.csv`
* `user_log_user_behavior_summary.csv`
* `cleaned_user_info.csv`
* Và các tệp khác được chỉ định trong script.

## Quy trình Làm việc của Script (Cấp cao):

1.  **Cấu hình & Thiết lập:** Đặt chế độ, đường dẫn, và logging.
2.  **Tải Dữ liệu & Khám phá Ban đầu:** Tải các tập dữ liệu và cung cấp cái nhìn tổng quan.
3.  **Làm sạch & Tiền xử lý Dữ liệu:** Xử lý các giá trị bị thiếu.
4.  **Kết hợp & Xây dựng Đặc trưng:** Kết hợp dữ liệu và tạo các đặc trưng mới.
5.  **Chia Tách Tập Huấn luyện-Kiểm định & Mã hóa:** Chia dữ liệu; mã hóa các đặc trưng hạng mục (chủ yếu là Label Encoding).
6.  **Lựa chọn Đặc trưng:** Sử dụng tổng hợp các phương pháp (tương quan, thông tin tương hỗ, độ quan trọng từ Random Forest).
7.  **Mô hình hóa Dự đoán:**
    * Xử lý mất cân bằng lớp (SMOTE).
    * Huấn luyện, đánh giá và so sánh nhiều mô hình.
    * Thực hiện tinh chỉnh siêu tham số (`RandomizedSearchCV`).
8.  **Phân tích SHAP:** Tính toán và phân tích giá trị SHAP để diễn giải mô hình.
9.  **Phân khúc Người dùng:**
    * Chuẩn bị đặc trưng cho việc gom cụm.
    * Áp dụng K-Means và xác định số cụm tối ưu.
    * Xây dựng hồ sơ cụm và gán chân dung dựa trên dữ liệu.
10. **Trực quan hóa & Kể chuyện:** Tạo biểu đồ tóm tắt các phát hiện chính.
11. **Lưu trữ Kết quả Đầu ra:** Lưu log, biểu đồ, và các bảng kết quả.
12. **Thông tin Chi tiết Kinh doanh & Đề xuất:** Rút ra thông tin chi tiết và đề xuất chiến lược.

## Phương pháp Mô hình hóa & Các Kỹ thuật Được Sử dụng:

### Cơ sở Lựa chọn Mô hình:

Script sử dụng một bộ các mô hình phân loại để đảm bảo một cách tiếp cận mạnh mẽ và toàn diện để dự đoán khả năng quay lại của người dùng. Các mô hình được chọn đại diện cho các họ thuật toán và độ phức tạp khác nhau:

* **Logistic Regression (Hồi quy Logistic):** Được chọn làm một mô hình tuyến tính đơn giản, dễ diễn giải. Nó đóng vai trò là một mô hình cơ sở tốt để so sánh với các mô hình phức tạp hơn và có thể hiệu quả một cách đáng ngạc nhiên.
* **Random Forest (Rừng Ngẫu nhiên):** Một phương pháp học máy ensemble xây dựng nhiều cây quyết định và kết hợp chúng. Nó mạnh mẽ đối với overfitting, xử lý tốt các mối quan hệ phi tuyến tính và cung cấp các thước đo độ quan trọng của đặc trưng một cách tự nhiên.
* **XGBoost (Extreme Gradient Boosting):** Một thuật toán gradient boosting được tối ưu hóa cao và mạnh mẽ, nổi tiếng về tốc độ và hiệu suất. Nó thường đạt được kết quả hàng đầu trên dữ liệu có cấu trúc/dạng bảng. Nó bao gồm kỹ thuật điều chuẩn (regularization) để ngăn chặn overfitting và có thể xử lý các giá trị bị thiếu bên trong.
* **LightGBM (Light Gradient Boosting Machine):** Một framework gradient boosting khác đặc biệt hiệu quả cho các tập dữ liệu lớn và cung cấp tốc độ huấn luyện nhanh mà không làm giảm độ chính xác. Nó sử dụng chiến lược phát triển cây theo từng lá (leaf-wise).
* **Extra Trees (Extremely Randomized Trees - Cây Cực kỳ Ngẫu nhiên):** Tương tự như Random Forest, nhưng nó đưa thêm tính ngẫu nhiên vào cách chọn điểm chia khi xây dựng cây. Điều này đôi khi có thể dẫn đến hiệu suất tốt hơn hoặc một góc nhìn khác về độ quan trọng của đặc trưng.

Sự lựa chọn này cho phép so sánh giữa các mô hình tuyến tính, các phương pháp ensemble truyền thống và các kỹ thuật boosting nâng cao, nhằm tìm ra hiệu suất dự đoán tốt nhất cho tập dữ liệu cụ thể.

### SHAP (SHapley Additive exPlanations)

* **SHAP là gì?** SHAP là một cách tiếp cận dựa trên lý thuyết trò chơi được sử dụng để giải thích đầu ra của bất kỳ mô hình học máy nào. Nó tính toán sự đóng góp của mỗi đặc trưng vào một dự đoán cụ thể bằng cách xem xét tất cả các kết hợp đặc trưng có thể. Giá trị SHAP cho một đặc trưng đại diện cho mức độ mà đặc trưng đó đã thay đổi dự đoán của mô hình so với dự đoán cơ sở.
* **Mục đích trong script này:**
    * **Độ quan trọng của Đặc trưng:** Cung cấp một thước đo đáng tin cậy và chi tiết hơn về độ quan trọng toàn cục của đặc trưng bằng cách lấy trung bình các giá trị SHAP tuyệt đối trên tất cả các mẫu. Điều này giúp xác định những đặc trưng nào có ảnh hưởng lớn nhất đến mô hình tổng thể.
    * **Khả năng Diễn giải Mô hình:** Giúp hiểu *tại sao* mô hình đưa ra các dự đoán nhất định cho từng người dùng cụ thể (khả năng diễn giải cục bộ, mặc dù script này tập trung vào độ quan trọng toàn cục).
    * **Gỡ lỗi & Tin cậy:** Tăng cường sự hiểu biết và tin cậy vào các quyết định của mô hình bằng cách làm cho hoạt động bên trong của nó trở nên minh bạch hơn.
    * Script sử dụng `TreeExplainer` cho các mô hình dựa trên cây (Random Forest, XGBoost, LightGBM, Extra Trees) vì nó hiệu quả hơn, và `KernelExplainer` làm phương án dự phòng cho các mô hình khác như Logistic Regression.

## Bảng thuật ngữ Kỹ thuật:

* **AUC-ROC (Area Under the Receiver Operating Characteristic Curve - Diện tích dưới đường cong ROC):** Một thước đo hiệu suất cho các mô hình phân loại nhị phân. Nó thể hiện khả năng của mô hình trong việc phân biệt giữa các lớp dương và âm ở tất cả các ngưỡng phân loại. Giá trị 1.0 là hoàn hảo, trong khi 0.5 là ngẫu nhiên.
* **F1-Score:** Trung bình điều hòa của Precision (Độ chính xác) và Recall (Độ nhạy). Đây là một thước đo hữu ích khi xử lý các lớp không cân bằng.
* **Log Loss (Logistic Loss hoặc Cross-Entropy Loss - Mất mát Log):** Thước đo hiệu suất cho phân loại; phạt các dự đoán tự tin nhưng không chính xác. Giá trị càng thấp càng tốt.
* **Brier Score (Điểm Brier):** Đo lường sai số bình phương trung bình giữa xác suất dự đoán và kết quả thực tế. Giá trị càng thấp càng tốt.
* **SMOTE (Synthetic Minority Over-sampling Technique):** Một kỹ thuật để giải quyết vấn đề mất cân bằng lớp bằng cách tạo ra các mẫu tổng hợp cho lớp thiểu số.
* **K-Means Clustering (Gom cụm K-Means):** Một thuật toán học không giám sát nhằm mục đích phân chia n quan sát thành k cụm, trong đó mỗi quan sát thuộc về cụm có giá trị trung bình (tâm cụm) gần nhất.
* **Silhouette Score (Điểm Silhouette):** Một thước đo được sử dụng để tính toán chất lượng của kỹ thuật gom cụm. Giá trị của nó dao động từ -1 đến 1. Giá trị càng cao càng tốt.
* **Inertia (Quán tính - cho K-Means):** Tổng bình phương khoảng cách của các mẫu đến tâm cụm gần nhất của chúng. Được sử dụng trong Phương pháp Elbow để giúp tìm ra số k tối ưu. Giá trị càng thấp càng tốt.
* **Hyperparameter Tuning (Tinh chỉnh Siêu tham số):** Quá trình tìm kiếm bộ siêu tham số tối ưu cho một thuật toán học máy.
* **RandomizedSearchCV:** Một phương pháp để tinh chỉnh siêu tham số, thử nghiệm một số lượng cố định các cài đặt tham số được lấy mẫu ngẫu nhiên từ các phân phối được chỉ định.
* **Label Encoding (Mã hóa Nhãn):** Chuyển đổi dữ liệu văn bản hạng mục thành dữ liệu số (0, 1, 2...).
* **Feature Engineering (Xây dựng Đặc trưng):** Quá trình sử dụng kiến thức chuyên môn để tạo ra các đặc trưng đầu vào mới từ dữ liệu hiện có nhằm cải thiện hiệu suất mô hình.
* **Class Imbalance (Mất cân bằng Lớp):** Tình huống mà các lớp trong một bài toán phân loại không được biểu diễn đồng đều.
* **Ensemble Methods (Phương pháp Ensemble/Tổ hợp):** Các kỹ thuật học máy kết hợp nhiều mô hình cơ sở để tạo ra một mô hình dự đoán tối ưu (ví dụ: Random Forest, XGBoost).

## Kết quả Đầu ra:

Tất cả các kết quả đầu ra được lưu trong thư mục `round_2.2`:

* **`round_2.2.txt`**: Log thực thi hoàn chỉnh.
* **`round_2_2_analysis_results.png`**: Biểu đồ đa khung hình trực quan hóa các kết quả chính.
* **`model_comparison.csv`**: Các thước đo hiệu suất cho tất cả các mô hình đã huấn luyện.
* **`feature_importance_rf_initial.csv`**: Điểm độ quan trọng của đặc trưng từ Random Forest ban đầu.
* **`combined_feature_importance.csv`**: (Nếu SHAP chạy) Điểm độ quan trọng kết hợp từ RF + SHAP.
* **`shap_feature_importance.csv`**: (Nếu SHAP chạy) Điểm độ quan trọng của đặc trưng từ giá trị SHAP.
* **`cluster_profiles.txt`**: Hồ sơ chi tiết của các phân khúc người dùng được xác định.
* **`enhanced_persona_analysis.txt`**: Phân tích sâu về các chân dung được gán.
* **`selected_features.txt`**: Danh sách các đặc trưng được chọn để huấn luyện mô hình.
* **`phone_carrier_analysis.csv`**: (Nếu có) Phân tích dữ liệu điện thoại & nhà mạng liên quan đến biến mục tiêu.

## Các Bước Phân tích Chính & Phát hiện (Ví dụ từ một lần chạy Production Tier 2):

* Giải quyết vấn đề mất cân bằng biến mục tiêu đáng kể (ví dụ: ~6.9% lớp thiểu số) bằng SMOTE.
* So sánh nhiều mô hình phân loại; Random Forest thường hoạt động tốt (ví dụ: AUC-ROC ~0.6392 trong một lần chạy).
* Thực hiện phân tích SHAP để xác định các yếu tố chính thúc đẩy sự quay lại của người dùng, chẳng hạn như thông tin nhà mạng và các điểm tin cậy người dùng được xây dựng.
* Xác định các phân khúc người dùng riêng biệt (ví dụ: "Người trung thành ổn định," "Nhóm nhỏ có rủi ro rời bỏ cao") bằng cách sử dụng gom cụm K-Means.
* Gán các chân dung dựa trên dữ liệu và đề xuất các chiến lược phù hợp cho từng phân khúc.

## Gỡ lỗi & Lưu ý:

* Đảm bảo tất cả các thư viện Python phụ thuộc được liệt kê trong **Điều kiện Tiên quyết** đã được cài đặt trong môi trường của bạn.
* Nếu việc tải dữ liệu không thành công, hãy xác minh rằng các tệp CSV đầu vào có mặt trong thư mục `data_path` chính xác (`cleaning_results/cleaned_data/`) hoặc cập nhật biến `data_path` trong script.
* Thư viện `shap` là tùy chọn để script chạy nhưng rất được khuyến khích để có khả năng diễn giải mô hình và phân tích độ quan trọng của đặc trưng đầy đủ. Nếu không được cài đặt, phần SHAP sẽ được bỏ qua.
* Thời gian thực thi thay đổi đáng kể dựa trên `DEVELOPMENT_MODE` và `PRODUCTION_TIER` được chọn.
