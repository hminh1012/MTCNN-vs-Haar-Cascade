
# Jupyter Notebook: CNN, MTCNN vs. Haar Cascade Face Detection
*(Analysis of Jupyter Notebook: CNN, MTCNN vs. Haar Cascade Face Detection)*

## 🇻🇳 Tiếng Việt

### **Mục đích chính**

Notebook này tập trung vào việc xây dựng một quy trình **nhận dạng khuôn mặt (Face Recognition)** bằng cách sử dụng bộ dữ liệu **Yale Face Database**. Trọng tâm của file là tiền xử lý dữ liệu, cụ thể là sử dụng thuật toán **MTCNN (Multi-task Cascaded Convolutional Networks)** để phát hiện, cắt và chuẩn hóa hình ảnh khuôn mặt. Dữ liệu sau khi xử lý sẽ sẵn sàng để huấn luyện một mô hình **Mạng Nơ-ron Tích chập (CNN)** cho nhiệm vụ nhận dạng.

### **Nội dung chi tiết**

#### **1. Chuẩn bị môi trường và dữ liệu**

* **Thư viện sử dụng:**
    * `numpy`: Thao tác với mảng và ma trận.
    * `cv2` (OpenCV): Thư viện xử lý thị giác máy tính.
    * `matplotlib.pyplot` & `PIL`: Hiển thị và xử lý hình ảnh.
    * `os` & `shutil`: Tương tác với hệ thống file.
    * `split-folders`: Tiện ích giúp phân chia bộ dữ liệu.
    * `mtcnn`: Thư viện chứa mô hình MTCNN đã được huấn luyện sẵn.

* **Bộ dữ liệu:** Sử dụng **"Yale Face Database"**, một bộ dữ liệu kinh điển chứa hình ảnh của nhiều người với các biểu cảm khác nhau.

#### **2. Tiền xử lý dữ liệu**

* **Tổ chức lại dữ liệu:**
    1.  Các file ảnh được đổi tên để có đuôi tệp `.jpg` thống nhất.
    2.  Dữ liệu được sắp xếp vào các thư mục con, mỗi thư mục tương ứng với một người (subject).

* **Phân chia bộ dữ liệu:** Dữ liệu được chia tự động thành 3 tập theo tỉ lệ:
    * **`train` (80%):** Dữ liệu dùng để huấn luyện mô hình.
    * **`val` (10%):** Dữ liệu dùng để tinh chỉnh mô hình.
    * **`test` (10%):** Dữ liệu dùng để kiểm tra hiệu suất cuối cùng.

#### **3. Phát hiện khuôn mặt với MTCNN**

* **Thuật toán MTCNN:** Là một mô hình học sâu tiên tiến, sử dụng chuỗi các mạng CNN để phát hiện khuôn mặt và các đặc điểm của nó với độ chính xác cao.
* **Hàm `detect_face`:**
    1.  Đọc file ảnh đầu vào.
    2.  Dùng detector MTCNN để tìm khuôn mặt.
    3.  Cắt (crop) vùng ảnh chứa khuôn mặt.
    4.  Thay đổi kích thước ảnh khuôn mặt về kích thước chuẩn là **160x160 pixels**.

### **Tóm tắt quy trình**

1.  **Khởi tạo:** Tải và chuẩn bị bộ dữ liệu.
2.  **Phân chia:** Chia dữ liệu thành 3 tập: `train`, `validation`, và `test`.
3.  **Phát hiện và trích xuất:** Dùng **MTCNN** để tìm, cắt và chuẩn hóa các khuôn mặt.
4.  **Hoàn thành:** Xuất ra các bộ dữ liệu đã được xử lý, sẵn sàng cho bước huấn luyện mô hình nhận dạng.

---

## 🇬🇧 English

### **Main Purpose**

This notebook focuses on building a **Face Recognition** pipeline using the **Yale Face Database**. The core of the file is data preprocessing, specifically using the **MTCNN (Multi-task Cascaded Convolutional Networks)** algorithm to detect, crop, and normalize face images. The processed data is then ready for training a **Convolutional Neural Network (CNN)** model for the recognition task.

### **Detailed Content**

#### **1. Environment and Data Setup**

* **Libraries Used:**
    * `numpy`: For array and matrix operations.
    * `cv2` (OpenCV): A computer vision library.
    * `matplotlib.pyplot` & `PIL`: For displaying and handling images.
    * `os` & `shutil`: For interacting with the file system.
    * `split-folders`: A utility to help split the dataset.
    * `mtcnn`: A library containing the pre-trained MTCNN model.

* **Dataset:** Uses the **"Yale Face Database"**, a classic dataset containing images of multiple subjects with various expressions.

#### **2. Data Preprocessing**

* **Data Reorganization:**
    1.  Image files are renamed to have a consistent `.jpg` extension.
    2.  The data is sorted into subdirectories, with each directory corresponding to one subject.

* **Dataset Splitting:** The data is automatically split into 3 sets with the following ratio:
    * **`train` (80%):** Data used to train the model.
    * **`val` (10%):** Data used for model validation and tuning.
    * **`test` (10%):** Data used for final performance evaluation.

#### **3. Face Detection with MTCNN**

* **MTCNN Algorithm:** An advanced deep learning model that uses a cascade of CNNs to detect faces and their landmarks with high accuracy.
* **`detect_face` Function:**
    1.  Reads an input image file.
    2.  Uses the MTCNN detector to find a face.
    3.  Crops the region of the image containing the face.
    4.  Resizes the cropped face image to a standard size of **160x160 pixels**.

### **Process Summary**

1.  **Initialization:** Load and prepare the dataset.
2.  **Splitting:** Divide the data into `train`, `validation`, and `test` sets.
3.  **Detection & Extraction:** Use **MTCNN** to find, crop, and normalize faces.
4.  **Completion:** Output the processed datasets, ready for the recognition model training step.
