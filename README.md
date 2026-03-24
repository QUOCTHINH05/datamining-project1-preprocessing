# Khai thác dữ liệu và ứng dụng - Đồ án 1

## Quy trình tiền xử lý dữ liệu

### Tổng quan dự án

Dự án này thực hiện các kỹ thuật tiền xử lý dữ liệu toàn diện cho nhiều loại dữ liệu khác nhau:

- **Phần 1**: Tiền xử lý dữ liệu ảnh
- **Phần 2**: Tiền xử lý dữ liệu bảng
- **Phần 3**: Tiền xử lý dữ liệu văn bản (tùy chọn)
- **Phần 4**: Tiền xử lý dữ liệu chuỗi thời gian (tùy chọn)

Mỗi phần bao gồm cài đặt kỹ thuật tiền xử lý, phân tích ablation và kiểm định thống kê để củng cố lập luận.

---

### Thành viên nhóm

| STT | Họ tên               | MSSV     | Vai trò                                                                   |
| --- | -------------------- | -------- | ------------------------------------------------------------------------- |
| 1   | Cao Tiến Thành       | 23120088 | Thực hiện EDA và tiền xử lý bảng                                          |
| 2   | Đỗ Quốc Thịnh        | 23120089 | Thực hiện EDA và tiền xử lý bảng; soạn thảo PDF; kiểm tra chất lượng code |
| 3   | Cao Thanh Bình       | 23120216 | Thực hiện tiền xử lý văn bản / Thực hiện tiền xử lý chuỗi thời gian       |
| 4   | Nguyễn Văn Chiến     | 23120219 | Thực hiện tiền xử lý văn bản / Thực hiện tiền xử lý chuỗi thời gian       |
| 5   | Đặng Nguyễn Thái Đạt | 23120227 | Thực hiện EDA và tiền xử lý ảnh                                           |

---

### Mô tả tập dữ liệu

#### Phần 1: Dữ liệu ảnh

- **Tập dữ liệu**:
- **Mô tả**:
- **Kích thước**:
- **Nguồn**:

#### Phần 2: Dữ liệu bảng

- **Tập dữ liệu**:
- **Mô tả**:
- **Kích thước**:
- **Nguồn**:

#### Phần 3: Dữ liệu văn bản (nếu chọn)

- **Tập dữ liệu**:
- **Mô tả**:
- **Kích thước**:
- **Nguồn**:

#### Phần 4: Dữ liệu chuỗi thời gian (nếu chọn)

- **Tập dữ liệu**:
- **Mô tả**:
- **Kích thước**:
- **Nguồn**:

---

### Cấu trúc dự án

```
Group_05/
|-- README.md                    # File này (Tổng quan, hướng dẫn chạy, link tài nguyên)
|-- requirements.txt             # Version cụ thể của toàn bộ thư viện
|-- data/
|   |-- raw/                     # Dữ liệu gốc (hoặc link Google Drive)
|   |-- processed/               # Dữ liệu sau tiền xử lý
|-- notebooks/
|   |-- 01_EDA_image.ipynb       # Phân tích thống kê ảnh
|   |-- 02_preprocessing_image.ipynb  # Tiền xử lý ảnh
|   |-- 03_EDA_tabular.ipynb     # Phân tích thống kê bảng
|   |-- 04_preprocessing_tabular.ipynb # Tiền xử lý bảng
|   |-- 05_text_preprocessing.ipynb    # Tiền xử lý văn bản (Phần 3)
|   |-- 06_temporal_preprocessing.ipynb # Tiền xử lý chuỗi thời gian (Phần 4)
|-- docs/
    |-- Report.pdf               # Báo cáo PDF
```

---

### Cài đặt môi trường

1. **Tạo môi trường ảo** (khuyến nghị):
   
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

2. **Cài đặt các thư viện**:
   
   ```bash
   pip install -r requirements.txt
   ```

3. **Khởi động Jupyter Lab**:
   
   ```bash
   jupyter lab
   ```

4. **Chạy notebook**: Mở và chạy notebook theo thứ tự:
   
   - Phần 1: `01_EDA_image.ipynb` → `02_preprocessing_image.ipynb`
   - Phần 2: `03_EDA_tabular.ipynb` → `04_preprocessing_tabular.ipynb`
   - Phần 3: `05_text_preprocessing.ipynb`
   - Phần 4: `06_temporal_preprocessing.ipynb`

---

### Phân công công việc

| Công việc                                                   | Thành viên           | Mô tả                                                                             |
| ----------------------------------------------------------- | -------------------- | --------------------------------------------------------------------------------- |
| Phần 1: EDA ảnh                                             | Đặng Nguyễn Thái Đạt | Phân tích thống kê, mất cân bằng lớp, pHash                                       |
| Phần 1: Tiền xử lý ảnh                                      | Đặng Nguyễn Thái Đạt | Resize, không gian màu, chuẩn hóa, augmentation                                   |
| Phần 2: EDA bảng                                            | X                    | Kiểm định phân phối, tương quan, phân tích dữ liệu thiếu                          |
| Phần 2: Tiền xử lý bảng                                     | X                    | Điền khuyết, phát hiện ngoại lai, chuẩn hóa, mã hóa, chọn và giảm chiều đặc trưng |
| Phần 3 / 4: Tiền xử lý văn bản / Tiền xử lý chuỗi thời gian | X                    | X                                                                                 |
| Viết báo cáo                                                | Đỗ Quốc Thịnh        | Tổng hợp báo cáo PDF                                                              |
| Review code                                                 | X                    | Kiểm tra chất lượng và tài liệu                                                   |

---

### Tài nguyên ngoài

- **Link dữ liệu**:
- **Tài liệu tham khảo**:
- **Tài liệu hướng dẫn**:

---

### Giấy phép

Dự án này chỉ dành cho mục đích học thuật.