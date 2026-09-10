# Human Parsing Pipeline

Dự án thực hiện **Human Parsing** từ video đầu vào, chuyển đổi video thành các ảnh phân vùng người (segmentation), sau đó trích xuất và chuyển đổi đặc trưng để phục vụ quá trình huấn luyện và kiểm thử mô hình học máy.

## Cấu trúc pipeline

### 1. Xử lý dữ liệu raw

* **Notebook:** `video2parsing.ipynb`
* **Chức năng:**

  * Chuyển đổi video đầu vào thành chuỗi ảnh định dạng PNG.
  * Thực hiện Human Parsing trên từng khung hình.
* **Đầu vào:** Video `.mp4`
* **Đầu ra:** Các ảnh PNG đã được phân vùng.

### 2. Xử lý đầu vào cho mô hình

* **Notebook:** `img2pkl.ipynb`
* **Chức năng:**

  * Xử lý các ảnh segmentation.
  * Trích xuất đặc trưng và lưu dưới dạng `.pkl`.
* **Đầu vào:** Ảnh segmentation PNG
* **Đầu ra:** File `.pkl` chứa đặc trưng phục vụ mô hình.

### 3. Chạy mô hình kiểm thử

* **Notebook:** `test_model.ipynb`
* **Chức năng:**

  * Tải mô hình đã được huấn luyện.
  * Thực hiện dự đoán trên dữ liệu đầu vào.
  * Đánh giá hiệu suất của mô hình.
* **Đầu vào:** File `.pkl`
* **Đầu ra:** Kết quả dự đoán và các chỉ số đánh giá.

## Kết quả

### Kết quả Human Parsing

<p align="center">
  <img src="./result.png" width="800">
</p>

### Model Metrics

| Rank-1 | Rank-5 | Rank-10 | mAP | mINP |
| :------: | :------: | :------: | :------: | :------: |
|  76.18 |  89.09 |  92.49 |  68.10 |  49.54 |
