# DAZONE 2025 Vòng 2.2: Bé Cùng AI Dự Đoán Bạn Nào Sẽ Quay Lại Chơi & Chia Nhóm Bạn Bè

**Mục tiêu của trò chơi này là gì?**
Tưởng tượng chúng ta có một cửa hàng đồ chơi. Chúng ta muốn biết bạn nhỏ nào đã mua đồ chơi rồi sẽ quay lại mua nữa. AI (giống như một bạn rô-bốt siêu thông minh) sẽ giúp chúng ta đoán xem bạn nào quay lại. Sau đó, chúng ta sẽ chia các bạn nhỏ thành từng nhóm khác nhau để có thể tặng quà hoặc nói chuyện với từng nhóm theo cách mà các bạn ấy thích nhất! Để làm được điều này, chúng ta cần dọn dẹp sổ sách (làm sạch dữ liệu), nghĩ ra cách ghi chép thông minh hơn (xây dựng đặc trưng), dạy cho bạn AI cách đoán (mô hình hóa), hỏi bạn AI xem tại sao bạn ấy lại đoán như vậy (diễn giải bằng SHAP), và cuối cùng là chia các bạn thành từng nhóm (gom cụm).

**Ai đã tạo ra trò chơi AI này?** AI Assistant
**Ngày hoàn thành:** 2025-06-02 (Đã cập nhật thêm nhiều điều thú vị!)

## Những Điều Thú Vị Mà Script Này Có Thể Làm:

* **Dạy AI Đoán Giỏi:** Huấn luyện và xem xét nhiều bạn AI khác nhau để xem bạn nào đoán giỏi nhất việc bạn nhỏ có quay lại cửa hàng không.
* **Chia Nhóm Bạn Bè:** Dùng một phép thuật gọi là K-Means để tự động chia các bạn nhỏ thành từng nhóm riêng biệt dựa trên những điểm giống nhau.
* **Đặt Tên Cho Nhóm (Chân dung Thông minh):** Tự động đặt cho mỗi nhóm một cái tên thật hay (giống như biệt danh) để chúng ta dễ hình dung về các bạn trong nhóm đó.
* **Tạo Ra Thông Tin Mới Siêu Đẳng (Xây dựng Đặc trưng Nâng cao):**
    * Xem xét kỹ số điện thoại và nhà mạng của bố mẹ các bạn xem có gì đặc biệt không.
    * Kết hợp các thông tin lại với nhau, ví dụ như bạn nhỏ ở độ tuổi nào thì hay mua đồ chơi gì.
    * Tính toán xem các bạn có thường xuyên ghé cửa hàng không.
* **Hỏi Tỏ Mọi Chuyện Với AI (Diễn giải Mô hình bằng SHAP):** Dùng một công cụ đặc biệt tên là SHAP để hiểu tại sao bạn AI lại đưa ra dự đoán như vậy, xem thông tin nào là quan trọng nhất.
* **Chế Độ Chơi Nhanh và Chơi Kỹ:**
    * `DEVELOPMENT_MODE` (Chơi thử): Chạy nhanh để xem thử ý tưởng có hay không, chỉ lấy một ít bạn nhỏ ra để thử thôi.
    * `PRODUCTION_MODE` (Chơi thật - có 2 mức độ): Phân tích tất cả các bạn nhỏ luôn, có thể chọn chơi nhanh (Tier 1) hoặc chơi thật kỹ (Tier 2) để có kết quả tốt nhất.
* **Ghi Chép Cẩn Thận:** Mọi việc bạn AI làm đều được ghi lại vào một cuốn sổ (tệp log) để chúng ta xem lại.
* **Báo Cáo Đầy Đủ:** Tạo ra nhiều hình ảnh đẹp, bảng biểu để tổng kết lại những gì chúng ta khám phá được.

## Những Lỗi Đã Được Sửa Gần Đây:

* **Lỗi SHAP (Hỏi AI):** Đã sửa để công cụ SHAP hoạt động trơn tru hơn, hiểu được cả những cách AI suy nghĩ phức tạp.
* **Lỗi Gán Tên Nhóm:** Sửa cách tính toán để việc đặt tên cho các nhóm bạn bè (gán chân dung) được chính xác và ổn định hơn, dù cho thông tin có hơi lộn xộn chút.
* **Lỗi Hiển Thị Tuổi:** Đã sửa cách xử lý thông tin tuổi, để những bạn không rõ tuổi sẽ không bị coi nhầm là 0 tuổi, giúp biểu đồ tuổi đẹp và đúng hơn.

## Ngôi Nhà Của Các Tệp (Cấu trúc Thư mục):

Tưởng tượng đây là một ngôi nhà lớn, và các tệp được xếp vào các phòng khác nhau:

.
├── ten_script_cua_ban.py             # Đây là cuốn sách hướng dẫn chính (script)
├── cleaning_results/
│   └── cleaned_data/               # PHÒNG CHỨA DỮ LIỆU SẠCH SẼ (Đầu vào)
│       ├── competition_train_features.csv
│       ├── ... (nhiều sổ ghi chép khác về các bạn)
└── round_2.2/                      # PHÒNG CHỨA KẾT QUẢ (Đầu ra)
├── round_2.2_execution_log.txt # Cuốn nhật ký ghi lại mọi việc AI làm
├── ideal_customer_profile.jpg  # Hình ảnh về nhóm bạn lý tưởng
├── round_2_2_analysis_results.png # Bảng tổng kết lớn với nhiều hình ảnh
└── ... (nhiều báo cáo và kết quả khác)

*(Lưu ý: Tên các thư mục trực quan hóa đã được cập nhật trong code để dễ quản lý hơn, ví dụ: `0_data_cleaning_reports`, `1_exploratory_data_analysis/1a_demographics`, v.v...)*

## Những Thứ Cần Có Để Chạy Script (Điều kiện Tiên quyết & Thư viện):

Giống như muốn xây nhà Lego, bạn AI cần có đủ các mảnh ghép (thư viện Python):

* pandas, numpy (để sắp xếp và tính toán dữ liệu)
* matplotlib, seaborn (để vẽ biểu đồ đẹp)
* scikit-learn (bộ công cụ chính để dạy AI)
* imbalanced-learn (giúp AI học tốt hơn khi số lượng các nhóm bạn không đều nhau)
* xgboost, lightgbm (hai bạn AI phụ trợ siêu mạnh)
* shap (công cụ đặc biệt để hiểu AI nghĩ gì - không bắt buộc nhưng nên có)

Bạn có thể nhờ người lớn cài đặt giúp bằng câu lệnh:
`pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost lightgbm shap`

## Cách Điều Khiển Bạn AI (Cấu hình):

Ở đầu cuốn sách hướng dẫn (script), có hai công tắc để bạn điều khiển bạn AI:

1.  **`DEVELOPMENT_MODE`** (Công tắc Chơi Nháp):
    * Bật (`True`): AI sẽ chạy thử nhanh với một ít dữ liệu thôi, để xem ý tưởng có ổn không.
    * Tắt (`False`): AI sẽ làm việc nghiêm túc với tất cả dữ liệu.

2.  **`PRODUCTION_TIER`** (Mức độ Chơi Thật - khi Chơi Nháp tắt):
    * **Mức 1 (Tier 1)**: AI sẽ cố gắng làm xong việc trong vòng 1 tiếng, làm nhanh nhưng vẫn đảm bảo chất lượng.
    * **Mức 2 (Tier 2)**: AI sẽ làm việc kỹ hơn, có thể mất khoảng 2 tiếng, để có kết quả tốt nhất có thể.

## Cách Bắt Đầu Trò Chơi Với AI (Chạy Script):

1.  Để các sổ ghi chép về các bạn (tệp CSV đã làm sạch) vào đúng phòng `cleaning_results/cleaned_data/`.
2.  Chọn chế độ Chơi Nháp hay Chơi Thật bằng cách chỉnh công tắc ở đầu script.
3.  Nhờ người lớn gõ lệnh này vào máy tính:
    ```bash
    python ten_script_cua_ban.py
    ```
    (Nhớ thay `ten_script_cua_ban.py` bằng tên thật của cuốn sách hướng dẫn nhé).

## Các Cuốn Sổ Ghi Chép AI Cần (Tệp Dữ liệu Đầu vào):

Bạn AI cần những cuốn sổ này để làm việc (đã được dọn dẹp sạch sẽ):
* `competition_train_features.csv` (Sổ chính để AI học)
* `competition_test_features.csv` (Sổ để AI kiểm tra bài)
* `user_log_user_behavior_summary.csv` (Sổ ghi lại hành vi chung của các bạn)
* `cleaned_user_info.csv` (Sổ thông tin cá nhân của các bạn)
* Và một vài cuốn sổ khác như được liệt kê trong script.

## Các Bước Bạn AI Làm Việc (Quy trình Làm việc):

1.  **Chuẩn bị:** Đọc hướng dẫn, chọn chế độ làm việc.
2.  **Đọc Sổ Sách:** Xem qua tất cả các sổ ghi chép.
3.  **Dọn Dẹp Sổ Sách:** Làm cho sổ sách thật sạch sẽ, không có lỗi.
4.  **Ghi Chép Thông Minh:** Tạo ra những thông tin mới hữu ích từ sổ sách cũ.
5.  **Chia Sổ Để Dạy và Kiểm Tra:** Chia một phần sổ để dạy AI, một phần để kiểm tra xem AI học giỏi chưa. Mã hóa những chữ khó hiểu thành số để AI đọc được.
6.  **Chọn Thông Tin Quan Trọng:** Lọc ra những thông tin cần thiết nhất để dạy AI.
7.  **Dạy AI Đoán:**
    * Giúp AI học công bằng hơn nếu số bạn trong các nhóm không đều nhau (dùng SMOTE).
    * Cho nhiều bạn AI khác nhau cùng học và thi tài.
    * Tinh chỉnh các bạn AI để các bạn ấy đoán giỏi hơn nữa.
8.  **Hỏi AI "Vì Sao?":** Dùng SHAP để hiểu tại sao AI lại đoán như vậy.
9.  **Chia Nhóm Bạn Bè:**
    * Chuẩn bị thông tin để chia nhóm.
    * Dùng phép thuật K-Means để chia nhóm và tìm ra số nhóm hợp lý nhất.
    * Tìm hiểu xem mỗi nhóm bạn có đặc điểm gì và đặt tên cho các nhóm đó.
10. **Vẽ Tranh Kể Chuyện:** Vẽ nhiều biểu đồ đẹp để kể lại câu chuyện về các bạn nhỏ.
11. **Cất Giữ Thành Quả:** Lưu lại tất cả nhật ký, tranh vẽ, báo cáo vào đúng phòng.
12. **Lời Khuyên Từ AI:** Đưa ra những lời khuyên hữu ích cho cửa hàng đồ chơi.

## Các Bạn AI Giúp Sức & Phép Thuật Được Dùng:

### Tại Sao Lại Chọn Những Bạn AI Này?

Chúng ta nhờ nhiều bạn AI khác nhau giúp sức vì mỗi bạn có một thế mạnh riêng, giống như mỗi bạn nhỏ giỏi một trò chơi khác nhau vậy!

* **Logistic Regression (Bạn Cân Bằng):** Giống như một cái cân đơn giản. Bạn ấy giúp chúng ta xem xét một cách công bằng xem một bạn nhỏ có khả năng quay lại hay không. Bạn này dễ hiểu và là điểm khởi đầu tốt.
* **Random Forest (Hội Đồng Cây Thông Thái):** Tưởng tượng chúng ta hỏi ý kiến của cả một rừng cây thông thái. Mỗi cây sẽ đưa ra một ý kiến ("bạn này sẽ quay lại" hoặc "bạn này không"). Sau đó, cả rừng cây sẽ biểu quyết xem ý kiến nào được nhiều phiếu nhất. Cách này rất mạnh mẽ vì nhiều cái đầu luôn tốt hơn một!
* **XGBoost & LightGBM (Hai Bạn Rô-bốt Siêu Tốc):** Đây là hai bạn rô-bốt cực kỳ thông minh và học rất nhanh. Các bạn ấy liên tục sửa lỗi của mình để ngày càng đoán giỏi hơn. XGBoost thì rất cẩn thận, còn LightGBM thì siêu nhanh, đặc biệt khi có rất nhiều bạn nhỏ cần phân tích.
* **Extra Trees (Những Cái Cây Nghĩ Khác Biệt):** Cũng giống như Rừng Ngẫu nhiên, nhưng những cái cây này còn "nghịch ngợm" hơn một chút khi suy nghĩ, tạo ra những ý tưởng mới lạ. Đôi khi điều này lại giúp tìm ra cách đoán hay hơn.

**Tại sao lại cần nhiều bạn AI như vậy?** Để chúng ta thử nhiều cách khác nhau, từ dễ đến khó, xem cách nào đoán giỏi nhất và tìm ra được những điều bí mật thú vị nhất về các bạn nhỏ!

### SHAP (Bạn Giải Thích Thông Thái)

* **SHAP là gì?** Tưởng tượng khi cả đội thắng một trận đấu bóng đá. SHAP giống như một bạn bình luận viên rất giỏi, bạn ấy sẽ chỉ ra được cầu thủ nào (đặc trưng nào) đã chuyền bóng hay, cầu thủ nào đã sút giỏi, góp công lớn nhất vào bàn thắng (dự đoán đúng). SHAP cho mỗi đặc trưng một "điểm đóng góp".
* **Mục đích của SHAP trong script này là gì?**
    * **Tìm Ngôi Sao Sáng:** Giúp chúng ta biết thông tin nào (tuổi, giới tính, đồ chơi hay mua...) là quan trọng nhất khiến AI đoán một bạn nhỏ sẽ quay lại.
    * **Hiểu Rõ AI Hơn:** Giúp chúng ta hiểu tại sao AI lại đưa ra quyết định như vậy, chứ không phải AI đoán mò.
    * **Tin Tưởng AI:** Khi hiểu rồi, chúng ta sẽ tin tưởng bạn AI hơn.
    * Script này dùng `TreeExplainer` (Bạn giải thích chuyên về cây) cho các bạn AI dạng cây và `KernelExplainer` (Bạn giải thích đa năng) cho các bạn AI khác.

## Từ Điển Cho Bé (Giải thích các từ khó):

* **AUC-ROC:** Một loại điểm thi xem bạn AI phân biệt bạn nào "có" và bạn nào "không" giỏi đến đâu. Điểm càng cao (gần 1 nhất) thì bạn AI càng siêu.
* **F1-Score:** Điểm này cho biết bạn AI có đoán trúng nhiều bạn "có" mà không bỏ sót bạn nào không. Rất quan trọng khi số bạn "có" ít hơn hẳn số bạn "không".
* **Log Loss:** Nếu AI đoán sai mà lại rất tự tin là mình đúng, AI sẽ bị "phạt" nặng. Điểm này càng nhỏ thì AI càng ngoan.
* **Brier Score:** Xem những dự đoán "có lẽ" của AI có gần với sự thật không. Càng nhỏ càng tốt.
* **SMOTE:** Nếu trong lớp học có ít bạn nữ hơn bạn nam, SMOTE sẽ "nhân bản" thêm vài bạn nữ "ảo" y như thật để số lượng cân bằng hơn, giúp AI học công bằng hơn.
* **K-Means Clustering (Chia Nhóm K-Means):** Giống như trò chơi chia kẹo vào các rổ. Sao cho kẹo trong cùng một rổ thì giống nhau (cùng màu, cùng vị), và khác với kẹo ở rổ khác.
* **Silhouette Score (Điểm Chia Nhóm Đẹp):** Xem các rổ kẹo đã được chia có đẹp không. Kẹo trong rổ có hợp nhau không, và có khác kẹo ở rổ bên cạnh không? Điểm càng cao thì chia càng đẹp.
* **Inertia (Độ Chụm Lại - cho K-Means):** Xem các viên kẹo trong mỗi rổ có được xếp gần nhau, chụm lại một chỗ không. Số này càng nhỏ thì các viên kẹo trong rổ càng gần nhau.
* **Hyperparameter Tuning (Chỉnh Nút Thông Minh):** Giống như chỉnh các nút điều khiển trên một món đồ chơi rô-bốt để nó hoạt động tốt nhất, thông minh nhất.
* **RandomizedSearchCV (Thử Nút Ngẫu Nhiên):** Thay vì thử vặn hết tất cả các nút, chúng ta chỉ thử vặn một vài nút ngẫu nhiên xem cách nào tốt nhất.
* **Label Encoding (Dán Nhãn Số):** Đổi tên các đồ vật (ví dụ: "gấu bông", "xe hơi") thành các con số (0, 1, 2) để bạn AI dễ hiểu hơn.
* **Feature Engineering (Sáng Tạo Thông Tin Mới):** Dùng sự thông minh của mình để nghĩ ra những thông tin mới từ những gì đã có. Ví dụ, từ ngày sinh, mình có thể tính ra tuổi. Việc này giúp AI đoán giỏi hơn.
* **Class Imbalance (Lớp Học Không Đều):** Tưởng tượng trong lớp có 20 bạn nữ nhưng chỉ có 2 bạn nam. Đó là lớp học không đều!
* **Ensemble Methods (Biệt Đội Siêu Anh Hùng):** Thay vì để một siêu anh hùng giải cứu thế giới, chúng ta tập hợp cả một biệt đội! Mỗi người giỏi một kiểu, cùng nhau sẽ mạnh hơn. Các bạn AI như Random Forest, XGBoost là những biệt đội như vậy.

## Các Thành Quả AI Tạo Ra (Kết quả Đầu ra):

Tất cả các báo cáo, tranh vẽ của AI được cất trong phòng `round_2.2` (và các phòng nhỏ hơn bên trong `cleaning_results/visualization/`):

* **`round_2.2_execution_log.txt`**: Cuốn nhật ký chi tiết bạn AI đã làm những gì.
* **`ideal_customer_profile.jpg`**: Tranh vẽ chân dung nhóm bạn lý tưởng (thích mua hàng nhất).
* **`round_2_2_analysis_results.png`**: Một bức tranh lớn tổng hợp nhiều hình ảnh quan trọng khác.
* **`model_comparison.csv`**: Bảng điểm thi của các bạn AI.
* **`feature_importance_rf_initial.csv`**: Bảng xếp hạng xem thông tin nào quan trọng với bạn AI Random Forest (lúc đầu).
* **`combined_feature_importance.csv`**: (Nếu SHAP chạy) Bảng xếp hạng kết hợp độ quan trọng từ Random Forest và SHAP.
* **`shap_feature_importance.csv`**: (Nếu SHAP chạy) Bảng xếp hạng độ quan trọng chỉ từ SHAP.
* **`cluster_profiles.txt`**: Mô tả chi tiết về từng nhóm bạn đã được chia.
* **`enhanced_persona_analysis.txt`**: Phân tích sâu hơn về tên và đặc điểm của các nhóm bạn.
* **`selected_features.txt`**: Danh sách những thông tin quan trọng nhất mà AI đã dùng để học.
* Và nhiều biểu đồ, báo cáo khác trong các thư mục con như `0_data_cleaning_reports`, `1_exploratory_data_analysis`, v.v...

## Tóm Tắt Các Bước Khám Phá Chính (Ví dụ từ một lần "Chơi Thật"):

* AI đã giúp làm cân bằng số lượng các bạn trong các nhóm học khác nhau (dùng SMOTE).
* Bạn AI Random Forest thường đoán khá giỏi (ví dụ, điểm AUC-ROC khoảng 0.6392).
* AI đã dùng kính lúp SHAP để tìm ra những thông tin quan trọng nhất giúp đoán đúng, như thông tin về nhà mạng hoặc điểm tin cậy của người dùng.
* AI đã chia các bạn thành các nhóm khác nhau (ví dụ: nhóm "Bạn Thân Hay Ghé" và nhóm "Bạn Có Vẻ Sắp Nghỉ Chơi").
* Dựa vào đó, AI đề xuất cách nói chuyện và tặng quà riêng cho từng nhóm.

## Những Điều Cần Chú Ý (Gỡ lỗi & Lưu ý):

* Nhớ cài đủ các mảnh ghép (thư viện Python) cho bạn AI nhé!
* Nếu AI không tìm thấy sổ sách (dữ liệu), hãy kiểm tra xem bạn đã để đúng phòng `cleaning_results/cleaned_data/` chưa.
* Nên cài thêm kính lúp SHAP để hiểu rõ AI hơn.
* Thời gian AI làm việc sẽ khác nhau tùy bạn chọn chế độ Chơi Nháp hay Chơi Thật.
