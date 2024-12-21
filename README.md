# README: Dự đoán Chỉ số Suy giảm nghiêm trọng (SII)

## Mục đích
Notebook này được thiết kế để dự đoán **SII (Chỉ số suy giảm nghiêm trọng)**, một thước đo tiêu chuẩn để đánh giá **Sử dụng Internet có vấn đề (PIU)**, dựa trên hai loại dữ liệu:
1. **Dữ liệu bảng (tabular)**: Gồm 3.960 bản ghi của trẻ em và thanh thiếu niên với 81 cột (không bao gồm cột ID).
2. **Dữ liệu chuỗi thời gian (time series)**: Bao gồm 996 tệp định dạng Parquet.

## Các công cụ và thư viện sử dụng
- **Python Libraries**: pandas, numpy, sklearn, matplotlib, seaborn, plotly, lightgbm, xgboost, catboost, keras, torch, eli5, và nhiều thư viện khác.
- **Mục tiêu chính**:
  - Chuẩn hóa và tiền xử lý dữ liệu.
  - Xây dựng mô hình học máy (LightGBM, XGBoost, CatBoost) và học sâu.
  - Đánh giá và tối ưu hóa các mô hình thông qua các kỹ thuật như Cross-Validation và StratifiedKFold.

## Nội dung chính
### 1. **Nhập các thư viện và thiết lập ban đầu**
- Import các thư viện cần thiết cho việc xử lý dữ liệu, trực quan hóa, và xây dựng mô hình.
- Tắt các cảnh báo không cần thiết để tăng tính rõ ràng cho Notebook.

### 2. **Khám phá và tiền xử lý dữ liệu**
- Tải và phân tích cấu trúc dữ liệu.
- Xử lý thiếu dữ liệu thông qua `SimpleImputer`, `KNNImputer`.
- Chuẩn hóa các đặc trưng với `StandardScaler`.

### 3. **Xây dựng và huấn luyện mô hình**
- Mô hình được triển khai bao gồm:
  - **Regressors**: LightGBM, XGBoost, CatBoost, Random Forest, Gradient Boosting.
  - **Voting Regressor** để kết hợp các mô hình mạnh nhất.
  - **Autoencoder** và **Torch Neural Networks** cho phân tích học sâu.
- Sử dụng các công cụ đánh giá hiệu năng như:
  - **Cohen Kappa Score**.
  - Cross-Validation.
  - Permutation Importance từ `eli5`.

### 4. **Trực quan hóa**
- Sử dụng Plotly, Matplotlib, và Seaborn để tạo biểu đồ trực quan về dữ liệu và hiệu suất mô hình.

### 5. **Tối ưu hóa**
- Sử dụng `scipy.optimize.minimize` để tối ưu hóa các thông số.
- Triển khai các phương pháp ensemble để cải thiện dự đoán.

## Hướng dẫn sử dụng
1. Cài đặt các thư viện phụ thuộc (xem danh sách trong phần `Các công cụ và thư viện sử dụng`).
2. Chạy lần lượt từng ô (cell) trong Notebook.
3. Điều chỉnh tham số mô hình hoặc thử nghiệm các mô hình khác trong các bước huấn luyện.

## Đầu ra
- Kết quả dự đoán SII cho các bộ dữ liệu thử nghiệm.
- Các biểu đồ trực quan giúp phân tích dữ liệu và mô hình.
