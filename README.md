# Human Parsing Pipeline

Dự án này thực hiện phân tích ảnh người (human parsing) từ video đầu vào, xử lý thành các ảnh phân vùng (segmentation), và trích xuất đặc trưng để đưa vào mô hình học máy.

## Cấu trúc pipeline

1. **Xử lý dữ liệu raw**
   - **Notebook**: `video2parsing.ipynb`
   - **Chức năng**: 
     - Chuyển đổi video thành chuỗi ảnh định dạng PNG.
     - Thực hiện phân đoạn người (human parsing) trên từng ảnh.
   - **Đầu vào**: Video `.mp4`
   - **Đầu ra**: Ảnh PNG đã được phân đoạn.

2. **Xử lý đầu vào cho mô hình**
   - **Notebook**: `img2pkl.ipynb`
   - **Chức năng**: 
     - Chuyển ảnh phân đoạn thành định dạng `.pkl` để dùng cho mô hình.
   - **Đầu vào**: Ảnh segmentation PNG
   - **Đầu ra**: File `.pkl` chứa đặc trưng ảnh.

3. **Chạy mô hình kiểm thử**
   - **Notebook**: `test_model.ipynb`
   - **Chức năng**: 
     - Tải mô hình đã huấn luyện.
     - Dự đoán hoặc đánh giá hiệu suất dựa trên dữ liệu `.pkl`.
   - **Đầu vào**: File `.pkl`
   - **Đầu ra**: Kết quả dự đoán / đánh giá.
