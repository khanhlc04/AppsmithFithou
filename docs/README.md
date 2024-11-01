# Hướng Dẫn Sử Dụng Ứng Dụng 

Chào mừng bạn đến với hướng dẫn sử dụng ứng dụng của chúng tôi, ứng dụng chúng tôi sử dụng công nghệ Appsmith kết nối với Baserow! Ứng dụng này cho phép bạn quản lý tài khoản, dự án và công việc của doanh nghiệp của bạn một cách dễ dàng thông qua giao diện Appsmith và sử dụng dữ liệu từ Baserow.

## Mục lục

1. [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
2. [Bước 1: Import file JSON vào Appsmith](#bước-1-import-file-json-vào-appsmith)
3. [Bước 2: Thiết lập dữ liệu trong Baserow bằng file CSV](#bước-2-thiết-lập-dữ-liệu-trong-baserow-bằng-file-csv)
4. [Bước 3: Kết nối Appsmith với Baserow qua API](#bước-3-kết-nối-appsmith-với-baserow-qua-api)
5. [Bước 4: Thay đổi ID bảng](#bước-4-thay-đổi-id-bảng)

---

### Yêu cầu hệ thống

- Tài Khoản [Appsmith](https://appsmith.com/) đã được đăng ký và có không gian sẵn sàng sử dụng.
- Tài khoản [Baserow](https://baserow.io/) đã đăng ký và có không gian làm việc sẵn sàng sử dụng.
- File `appsmith_template.json` và các file CSV để import vào Baserow.

---

### Bước 1: Import file JSON vào Appsmith

1. Mở Appsmith và đăng nhập vào tài khoản của bạn.
2. Ở trang Dashboard, chọn **Create New** > **Import Application**.
3. Chọn file `AppsmithFithou.json` chúng tôi để ở thư mục `application` để upload vào Appsmith.
4. Sau khi import thành công, ứng dụng của bạn sẽ xuất hiện trong danh sách ứng dụng và sẵn sàng để sử dụng.

---

### Bước 2: Thiết lập dữ liệu trong Baserow bằng file CSV

1. Đăng nhập vào tài khoản Baserow của bạn.
2. Tạo một cơ sở dữ liệu mới trong Baserow (hoặc chọn một cơ sở dữ liệu hiện có).
3. Trong cơ sở dữ liệu, tạo một bảng mới bằng cách import dữ liệu từ file CSV:
   - Chọn **Import Table**.
   - Chọn file CSV chúng tôi để ở thư mục application và làm theo hướng dẫn để import dữ liệu vào Baserow.
4. Lặp lại quá trình này cho từng file CSV để hoàn tất việc import dữ liệu.

---

### Bước 3: Kết nối Appsmith với Baserow qua API

1. Trong Appsmith, sau khi bạn import file json của chúng tôi vào, hệ thống sẽ hiển thị cảnh báo lỗi và bạn sẽ phải setup cho nó
2. Truy cập **Settings** trên Baserow, chọn **API Token** để tạo API token (nếu bạn chưa có) và Sao chép API token này.
3. Cấu hình **URL**: Sử dụng URL gốc của Baserow là `https://api.baserow.io/api/`
4. **Authentication Type**: Chọn **API Key**
5. **Key**: Điền **Authorization**
6. **Value**: Dán **Token** của bạn vào đây
7. **Header Prefix**: Điền **Token** 
8. Sau khi hoàn tất, lưu kết nối và trở về màn hình chính

---

### Bước 4: Thay đổi ID bảng
1. Di chuyển tới mục js
2. Vào file **tableID**
3. Thay đổi các id bảng tương ứng của bạn 
4. Làm tương tự như vậy ở các trang còn lại
5. Kiểm tra xem Appsmith đã kết nối với Baserow thành công chưa.

