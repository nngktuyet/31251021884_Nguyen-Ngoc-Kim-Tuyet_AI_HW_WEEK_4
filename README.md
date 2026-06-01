# Face Recognition Project

## 1. Giới thiệu

Đây là project nhận diện khuôn mặt sử dụng mô hình **Convolutional Neural Network (CNN)**.

Project dùng ảnh khuôn mặt được chia theo từng thư mục class, mỗi class tương ứng với một người. Mục tiêu là train model để khi đưa vào một ảnh khuôn mặt mới, hệ thống có thể dự đoán ảnh đó thuộc về người nào.

---

## 2. File chính trong project

File chính:

```text
AI_HW_FaceDetect.ipynb
```

Trong đó:

* `AI_HW_FaceDetect.ipynb`: notebook dùng để train mô hình CNN nhận diện khuôn mặt, test dự đoán ảnh mới và lưu model thành file `.h5`.
* `facedetect.h5`: file model được tạo ra sau khi train xong.

---

## 3. Cài đặt môi trường

Mở Terminal trong thư mục project:

```bash
cd /Users/nguyenngockimtuyet/AI_HW
```

Cài các thư viện cần thiết:

```bash
python3 -m pip install tensorflow keras opencv-python numpy matplotlib
```

Nếu dùng Windows:

```bash
pip install tensorflow keras opencv-python numpy matplotlib
```
---

## 4. Cách train model

Mở file notebook:

```text
AI_HW_FaceDetect.ipynb
```

Sau đó chạy lần lượt các cell từ trên xuống dưới.

Notebook sẽ:

```text
1. Import thư viện.
2. Đọc dữ liệu từ folder 60_ANH.
3. Resize ảnh về 200x200.
4. Tạo dữ liệu train bằng ImageDataGenerator.
5. Xây dựng mô hình CNN.
6. Compile model với optimizer Adam.
7. Train model.
8. Test dự đoán ảnh mới.
9. Lưu model thành facedetect.h5.
```

---

## 5. Cách test ảnh mới

Trong notebook, thay đường dẫn ảnh cần test tại biến `path`.

Ví dụ:

```python
path = "/Users/nguyenngockimtuyet/AI_HW/example.jpeg"
```

Sau đó chạy cell dự đoán.

Ảnh sẽ được xử lý theo pipeline:

```text
Đọc ảnh
→ Resize về 200x200
→ Chuẩn hóa pixel về khoảng 0-1
→ Đưa vào model
→ Lấy class có xác suất cao nhất
→ In ra tên người
```

---

## 6. Lưu ý khi chạy

* Folder dataset `60_ANH` phải nằm đúng đường dẫn được khai báo trong notebook.
* Mỗi người nên có nhiều ảnh với nhiều góc chụp khác nhau để model học tốt hơn.
* Ảnh test nên rõ mặt, đủ sáng và không bị che quá nhiều.
* Nếu thêm người mới vào dataset, cần train lại model.
* Nếu đổi số lượng class, cần chỉnh lại số neuron ở lớp Dense cuối cho khớp với số class.
* Nên dùng ảnh train và ảnh test khác nhau để đánh giá model công bằng hơn.
