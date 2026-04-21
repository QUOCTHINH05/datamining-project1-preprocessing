# Khai thác dữ liệu và ứng dụng - Đồ án 1

## Quy trình tiền xử lý dữ liệu

### Tổng quan dự án

Dự án này thực hiện các kỹ thuật tiền xử lý dữ liệu toàn diện cho nhiều loại dữ liệu khác nhau:

- **Phần 1**: Tiền xử lý dữ liệu ảnh
- **Phần 2**: Tiền xử lý dữ liệu bảng
- **Phần 4**: Tiền xử lý dữ liệu chuỗi thời gian

Mỗi phần bao gồm cài đặt kỹ thuật tiền xử lý, phân tích ablation và kiểm định thống kê để củng cố lập luận.

---

### Thành viên nhóm

| STT | Họ tên               | MSSV     | Vai trò                                                                   |
| --- | -------------------- | -------- | ------------------------------------------------------------------------- |
| 1   | Cao Tiến Thành       | 23120088 | Thực hiện EDA và tiền xử lý bảng                                          |
| 2   | Đỗ Quốc Thịnh        | 23120089 | Thực hiện tiền xử lý bảng; soạn thảo PDF; kiểm tra chất lượng code |
| 3   | Cao Thanh Bình       | 23120216 | Thực hiện tiền xử lý chuỗi thời gian                                      |
| 4   | Nguyễn Văn Chiến     | 23120219 | Thực hiện tiền xử lý chuỗi thời gian                                     |
| 5   | Đặng Nguyễn Thái Đạt | 23120227 | Thực hiện EDA và tiền xử lý ảnh                                           |

---

### Mô tả tập dữ liệu

#### Phần 1: Dữ liệu ảnh

- **Tập dữ liệu**: CIFAR-10 (subset - data_batch_1)
- **Mô tả**: Tập dữ liệu ảnh màu 32×32 pixels với 10 lớp đối tượng: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck
- **Kích thước**: 10.000 ảnh (từ data_batch_1), 10 lớp
- **Nguồn**: https://www.cs.toronto.edu/~kriz/cifar.html

#### Phần 2: Dữ liệu bảng

- **Tập dữ liệu**: Adult Income Dataset (Census Income Dataset)
- **Mô tả**:Tập dữ liệu dạng bảng với 15 thuộc tính gồm có 6 thuộc tính số (age, fnlwgt, education-num, capital-gain, capital-loss, hour-per-week) và 8 thuộc tính phân loại (workclass, education, marital-status, occupation, relationship, race, sex, native-country), và 1 biến mục tiêu là income (>50k, <=50k). Yêu cầu thường gặp là phân loại thu nhập của một người có vượt qua 50.000$ 1 năm hay không dựa trên các đặc trưng đầu vào.
- **Kích thước**: 48842 dòng với 14 đặc trưng và 1 đặc trưng phân loại (income)
- **Missing value**: Tập dữ liệu có missing value trên thuộc tính ``workclass`` với 5.73%, ``occupation`` với 5.75% và ``native-country`` với 1.75%.
- **Nguồn**: [UCI-AdultIncome](https://archive.ics.uci.edu/dataset/2/adult)

#### Phần 4: Dữ liệu chuỗi thời gian

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
|     |-- image-data/
|     |       |-- raw/            # Dữ liệu gốc
|     |       |-- processed/      # Dữ liệu sau tiền xử lý
|     |-- tabular-data/
|     |       |-- raw/           
|     |       |-- processed/
|     |-- temporal-data/
|            |-- raw/         
|            |-- processed/
|-- notebooks/
|   |-- 01_EDA_image.ipynb                  # Phân tích thống kê ảnh
|   |-- 02_preprocessing_image.ipynb        # Tiền xử lý ảnh
|   |-- 03_EDA_tabular.ipynb                # Phân tích thống kê bảng
|   |-- 04_preprocessing_tabular.ipynb      # Tiền xử lý bảng
|   |-- 06_temporal_preprocessing.ipynb     # Tiền xử lý chuỗi thời gian 
|-- docs/
    |-- Report.pdf               # Báo cáo PDF
    |-- Report.txt               # Chứa đường dẫn đến trang Overleaf soạn thảo Latex cho Report.pdf
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
   - Phần 4: `06_temporal_preprocessing.ipynb`

---

### Phân công công việc

| Công việc                                                   | Thành viên           | Mô tả                                                                             |
| ----------------------------------------------------------- | -------------------- | --------------------------------------------------------------------------------- |
| Phần 1: EDA ảnh                                             | Đặng Nguyễn Thái Đạt | Phân tích thống kê, mất cân bằng lớp, pHash                                       |
| Phần 1: Tiền xử lý ảnh                                      | Đặng Nguyễn Thái Đạt | Resize, không gian màu, chuẩn hóa, augmentation                                   |
| Phần 2: EDA bảng                                            | Cao Tiến Thành        | Kiểm định phân phối, tương quan, phân tích dữ liệu thiếu             |
| Phần 2: Tiền xử lý bảng                                     | Đỗ Quốc Thịnh            | Xử lý giá trị thiếu bằng điền khuyết, phát hiện ngoại lai, chuẩn hóa có kiểm định, mã hóa biến phân loại |
| Phần 2: Tiền xử lý bảng                                     | Cao Tiến Thành            | Lựa chọn và giảm chiều đặc trưng, phát hiện xử lý mất cân bằng lớp |
| Phần 4: Tiền xử lý chuỗi thời gian                          | Cao Thanh Bình       | Phân tích ban đầu trước khi tiền xử lý, Kiểm định tính dừng, Trích xuất đặc trưng thời gian, Xây dựng ma trận đặc trưng cho dự báo.                                                                                 |
| Phần 4: Tiền xử lý chuỗi thời gian                          | Nguyễn Văn Chiến       | Xử lý khoảng trống và nội suy so sánh, Phân rã chuỗi thời gian,Phát hiện dị thường trong chuỗi thời gian, [Nâng cao] Phân tích nhân quả Granger (Granger Causality).                                                                                 |
| Viết báo cáo                                                | Cả 4 bạn        | Tổng hợp báo cáo PDF                                                              |
| Review code                                                 | Đỗ Quốc Thịnh, Cao Tiến Thành                    | Kiểm tra chất lượng và tài liệu                                                   |

---

### Tài nguyên ngoài

- **Link dữ liệu**:
- **Tài liệu tham khảo**:
- **Tài liệu hướng dẫn**:

---

### Giấy phép

Dự án này chỉ dành cho mục đích học thuật.
