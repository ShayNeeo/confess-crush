# README: Hành Trình Khai Phá Dữ Liệu Khách Hàng Sàn TMĐT - Sứ Mệnh DAZONE 2025 Vòng 2.2

Chào các chiến binh dữ liệu của đội! Chúng ta đang đứng trước một thử thách lớn từ "Sếp Tổng" tại cuộc thi DAZONE 2025: làm sao để sàn thương mại điện tử của chúng ta giữ chân được khách hàng, khiến họ quay lại mua sắm? File Python này chính là "bảo bối" và "kim chỉ nam" của đội trong hành trình khám phá những bí mật ẩn sâu trong dữ liệu khách hàng. Hãy cùng nhau giải mã nó và mang về chiến thắng nhé! 🚀

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
    A[Bắt đầu Script với Cấu Hình] --> B(Chương 1: Chuẩn Bị Dữ Liệu);
    B -- Dữ liệu đã Tiền xử lý, Chia TrainVal, Scale, SMOTE --> C(Chương 2: Huấn Luyện & Đánh Giá Model);
    C -- Model Dự Đoán Tốt Nhất --> D(Chương 3: Phân Tích Sâu);
    B -- Thông tin Người dùng, Dữ liệu Train sạch --> D;
    D -- SHAP, Phân khúc, Personas --> E[Kết thúc: Insights, Đề Xuất Chiến Lược cho Sàn TMĐT];
```

### Chương 1: Thu Thập Thông Tin Tình Báo - Chuẩn Bị Dữ Liệu

Trong chương này, chúng ta như những nhà khảo cổ, cẩn thận thu thập từng mảnh vỡ thông tin, làm sạch và sắp xếp chúng để chuẩn bị cho việc tái tạo lại bức tranh quá khứ và dự đoán tương lai. Đây là nền móng của mọi phân tích!

* **Khai Báo "Dụng Cụ Khảo Cổ" (Import Libraries)**
* **Thiết Lập "Khu Vực Khai Quật" (Configuration)**
* **Tạo Các "Hầm Trưng Bày" (Output Directory Setup)**
* **Ghi "Nhật Ký Khảo Cổ" (Logging Setup)**
* **Thu Thập "Cổ Vật" (Load Data)**
* **"Giám Định Sơ Bộ Cổ Vật" (Initial Data Exploration):** Vẽ biểu đồ tròn xem tỷ lệ khách hàng quay lại/không quay lại.
* **"Làm Sạch và Phục Chế Cổ Vật" (Data Preparation for Modeling):** Đây là một quy trình tỉ mỉ:

```mermaid
graph TD
    subgraph Quy Trình Tiền Xử Lý Dữ Liệu
        A[Tải Dữ Liệu Features Train và Test] --> B(Loại bỏ cột ngày tháng thô);
        B --> C[Điền giá trị NaN];
        C -- Số điền median hoặc 0, Chữ điền Unknown --> D[Mã hóa Label Encoding cho cột chữ];
        D -- Lưu trữ Bảng mã Label Encoders --> E[Xử lý giá trị Vô cực];
        E --> F[Dữ liệu Sạch Sẵn Sàng];
        F --> G[Chia Tập Huấn Luyện và Kiểm Chứng];
        G --> H[StandardScaler Đồng bộ hóa thang đo];
        H --> I[SMOTE Cân bằng X_train_scaled và y_train];
        I --> J[Dữ liệu sẵn sàng cho Huấn luyện Model];
        H --> K[Lưu X_train_scaled gốc cho Tuning];
    end
```

* **Chuẩn Bị Sẵn Các "Bản Phác Thảo Quả Cầu" (Model Options Storage)**
* **Dọn Dẹp "Phòng Thí Nghiệm" (Memory Management)**

### Chương 2: "Chế Tạo Quả Cầu Tiên Tri" - Xây Dựng và Đánh Giá Model

Sau khi "nguyên liệu" đã sẵn sàng, các "pháp sư dữ liệu" của chúng ta bắt tay vào việc chế tạo và thử nghiệm những "quả cầu tiên tri" có khả năng nhìn thấu tương lai.

* **Hàm "Thẩm Định Quả Cầu" (`evaluate_model_performance`):** "Hội đồng giám khảo" nội bộ của chúng ta, chuyên chấm điểm các "quả cầu".

* **Luồng Chế Tạo và Thử Nghiệm "Quả Cầu":**
  * **Quy Trình Chuẩn cho mỗi "Quả Cầu" được đánh giá ban đầu:**
    ```mermaid
    graph LR
        A[Dữ liệu huấn luyện đã chuẩn bị] --> B(SMOTE Cân bằng lực lượng);
        B --> C[Thôi miên Quả Cầu trên X_train_smote];
        C --> D[Thử tài Quả Cầu trên X_val_scaled];
        D --> E[Kết quả Điểm số và Biểu đồ];
    ```
  * **Quy Trình "Mài Giũa Quả Cầu" (Hyperparameter Tuning):**
    ```mermaid
    graph TD
        subgraph Quy Trình Tinh Chỉnh Siêu Tham Số
            A[Chọn Model Tốt Nhất Ban Đầu] --> B{Có Grid Tham Số cho Model này};
            B -- Có --> C[Xác định Model Instance và Dải Tham Số];
            C --> D[Sử dụng X_train_scaled và y_train gốc];
            D -- Truyền Class Weight hoặc Scale Pos Weight --> E(RandomizedSearchCV Tìm Cấu Hình Tốt Nhất);
            E --> F[Đánh giá Model Đã Tinh Chỉnh trên X_val_scaled];
            F --> G{Hiệu suất có cải thiện};
            G -- Có --> H[Cập nhật là Model Tốt Nhất Hiện Tại];
            G -- Không --> I[Giữ Model Gốc Tốt Hơn];
        end
    ```

* **Hai "Lò Rèn Thần Khí" (Two Modeling Options):**

  * **Lò Rèn 1: Tập Trung Rèn Giũa Những "Thần Khí" Đã Có Tiếng Tăm (Opt1 Models)**
    * *Chiến thuật:* Mời các "thợ rèn bậc thầy" (`LightGBM_Opt1`, `RandomForest_Opt1`, `XGBoost_Opt1`, `LogisticRegression_Opt1`) đến để chế tạo "vũ khí" theo công thức cơ bản của họ.
    * *Mục tiêu:* Xem xét nhanh hiệu suất của các model mạnh với cấu hình tiêu chuẩn, phù hợp với từng cấp độ thử thách.
    * *Luồng công việc:*
      ```mermaid
      graph TD
          A[Dữ liệu đã sơ chế và SMOTE] --> B1[Huấn luyện và Đánh giá LightGBM_Opt1];
          A --> B2[Huấn luyện và Đánh giá RandomForest_Opt1];
          A --> B3[Huấn luyện và Đánh giá XGBoost_Opt1];
          A --> B4[Huấn luyện và Đánh giá LogisticRegression_Opt1];
          B1 & B2 & B3 & B4 --> C[Tổng hợp kết quả Option 1];
      ```

  * **Lò Rèn 2: Tổ Chức "Thiên Hạ Đệ Nhất Lò Rèn" (Comp Models - Comparative Analysis)**
    * *Chiến thuật:* Mở một "đại hội võ lâm" cho nhiều "thợ rèn" từ các "môn phái" khác nhau, xem ai rèn ra "thần khí" lợi hại nhất.
    * *Mục tiêu:* So sánh một loạt thuật toán đa dạng để tìm ra "chân mệnh thiên tử".
    * *Luồng công việc:*
      ```mermaid
      graph TD
          A[Dữ liệu đã sơ chế và SMOTE] --> B[So Sánh Đồng Loạt Nhiều Models];
          B --> LR[Huấn luyện và Đánh giá LR_Comp];
          B --> RF[Huấn luyện và Đánh giá RF_Comp];
          B --> XGB[Huấn luyện và Đánh giá XGB_Comp];
          B --> LGBM[Huấn luyện và Đánh giá LGBM_Comp];
          B --> SVC[Huấn luyện và Đánh giá SVC_Comp];
          B --> MLP[Huấn luyện và Đánh giá MLP_Comp];
          LR & RF & XGB & LGBM & SVC & MLP --> C[Tổng hợp kết quả Option 2];
          C --> D[So sánh và chọn Model nổi bật từ Option 2];
      ```

* **Công Bố "Bảng Vàng" và Chọn "Võ Trạng Nguyên" (Model Comparison, Best Model Before Tuning)**
* **"Bế Quan Luyện Công" Cho "Võ Trạng Nguyên" (Hyperparameter Tuning)**
* **"Thần Khí Xuất Thế" (Final Best Model) và "Yếu Quyết Võ Công" (Feature Importance)**

### Chương 3: "Đọc Vị Quả Cầu" & Phân Loại "Chiến Binh" - Phân Tích Sâu và Tạo Chân Dung Khách Hàng

Khi đã có "thần khí" trong tay, chúng ta cần hiểu rõ sức mạnh của nó và dùng nó để "nhìn thấu" tâm can của từng nhóm khách hàng, từ đó đưa ra những chiến lược phù hợp cho sàn thương mại điện tử.

* **I. "Soi Gương Ma Thuật" - Hiểu Cách "Quả Cầu" Suy Nghĩ (SHAP Analysis):**
  * *Mục tiêu:* "Quả cầu tiên tri" không còn là một hộp đen bí ẩn nữa! SHAP giúp chúng ta hiểu rõ từng "luồng suy nghĩ" của nó.
  * *Luồng công việc:*
    ```mermaid
    graph TD
        A[Model Tốt Nhất Cuối Cùng] --> B[Lấy Mẫu Dữ Liệu X_val_scaled];
        A --> C{Model thuộc loại Tree-based};
        C -- Có --> D[Sử dụng SHAP TreeExplainer];
        C -- Không, có predict_proba --> E[Sử dụng SHAP KernelExplainer];
        E -- Cần dữ liệu nền --> D;
        D --> F[Tính toán SHAP Values];
        F --> G[Vẽ Biểu Đồ SHAP Summary];
        G --> H[Lưu Kết Quả Độ Quan Trọng SHAP];
    ```

* **II. "Điểm Binh Khách Hàng" - Phân Loại Khách Hàng Thông Minh (User Segmentation - K-Means Clustering):**
  * *Mục tiêu:* Không phải khách hàng nào cũng giống nhau. Chúng ta sẽ chia họ thành các "biệt đội" có cùng "chí hướng" và "phong cách".
  * *Luồng công việc:*
    ```mermaid
    graph TD
        A[Dữ Liệu Khách Hàng Tổng Hợp] --> B[Kết hợp Thông Tin Nhân Khẩu Học];
        B --> C[Tiền Xử Lý Dữ Liệu cho Clustering];
        C -- Dữ liệu đã Scale --> D{Tính Inertia và Silhouette Scores};
        D -- Cho các giá trị k khác nhau --> E[Vẽ Đồ Thị Elbow và Silhouette];
        E --> F{Chọn optimal_k theo K_SELECTION_METHOD};
        F -- optimal_k --> G[Chạy K-Means với optimal_k];
        G --> H[Gán Nhãn Cụm cho Khách Hàng];
        H --> I[Profiling Cụm Phân tích đặc điểm từng cụm];
        I --> J[Lưu Kết Quả Phân Cụm];
    ```

* **III. "Phong Tước Hiệu" Cho Các "Biệt Đội" (Persona Assignment):** Dựa trên đặc điểm của từng "biệt đội", chúng ta đặt cho họ những "biệt danh" thể hiện rõ bản chất (ví dụ: "Đại Gia Mua Sắm", "Thợ Săn Khuyến Mãi", "Khách Hàng Tiềm Năng Ngủ Đông").

* **IV. "Cẩm Nang Thượng Sách" Cho Sàn TMĐT (Business Insights & Recommendations):** Từ những gì "quả cầu" tiết lộ và các "biệt đội" được hình thành, chúng ta sẽ viết nên những "kế sách" giúp sàn TMĐT tăng doanh thu, giữ chân khách hàng.

* **V. "Báo Cáo Tổng Lực Lượng" và "Kế Hoạch Mở Rộng Bờ Cõi" (Final Summary & Next Steps).**

