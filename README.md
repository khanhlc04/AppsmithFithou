# Appsmith - FITHOU
### Phần mềm làm việc online

Trong bối cảnh xã hội hiện đại, việc quản lý công việc hiệu quả và khoa học là yếu tố quan trọng quyết định năng suất và sự thành công của các cá nhân cũng như tổ chức. Với sự phát triển mạnh mẽ của công nghệ thông tin, các ứng dụng quản lý công việc đã trở thành công cụ không thể thiếu trong việc hỗ trợ người dùng theo dõi, sắp xếp và tối ưu hóa quy trình làm việc.

Từ góc độ của người dùng, quản lý công việc gặp phải nhiều khó khăn trong việc tổ chức thông tin, ghi nhớ và nhắc nhở các nhiệm vụ quan trọng. Trong quản lý tiến độ công việc của các thành viên trong dự án, những thách thức phổ biến bao gồm thiếu sự phối hợp và giao tiếp hiệu quả giữa các thành viên. Ngoài ra, việc theo dõi hiệu suất của từng cá nhân cũng là một nhiệm vụ phức tạp. Đối với quản lý tiến độ chung của dự án, việc duy trì tầm nhìn tổng thể về tiến độ, phát hiện kịp thời các trở ngại và đảm bảo mọi thành viên đều nhận thức rõ mục tiêu chung là vô cùng quan trọn

Phần mềm mong muốn xây dựng các chức năng chính gồm quản lý dự án, phân công công việc, theo dõi tiến độ, giao tiếp cộng tác, báo cáo thống kê công việc giúp người dùng dễ dàng theo dõi và đảm bảo tiến độ công việc.
Qua đó, đồ án mong muốn đóng góp vào việc phát triển các giải pháp công nghệ để nâng cao hiệu suất và tiện ích của việc quản lý công việc, đồng thời thúc đẩy sự phát triển của công nghệ thông tin và ứng dụng trong cuộc sống hàng ngày.

## 🔎 Danh Mục

- [Appsmith - FITHOU](#appsmith---fithou)
    - [Phần mềm làm việc online](#phần-mềm-làm-việc-online)
  - [🔎 Danh Mục](#-danh-mục)
  - [Chức Năng Chính](#chức-năng-chính)
  - [👩‍💻 Tổng Quan Hệ Thống](#-tổng-quan-hệ-thống)
  - [Cấu trúc dự án](#cấu-trúc-dự-án)
  - [Cài Đặt](#cài-đặt)
  - [🙌 Đóng góp cho dự án](#-đóng-góp-cho-dự-án)
  - [📝 License](#-license)



## Chức Năng Chính

Project mong muốn tập trung vào xây dựng các chức năng chính như sau:

-   📋 Tạo và phân công nhiệm vụ (Tasks & Assignments). 
-   📝 Lên lịch và theo dõi tiến độ. 
-   🛎 Thông báo và nhắc nhở. 
-   📃 Quản lý tài liệu dự án.

## 👩‍💻 Tổng Quan Hệ Thống

Backend của nền tảng Appsmith hoạt động như sau:

-   [Spring Framework](https://spring.io/projects/spring-framework): Phát triển các dịch vụ và xử lý logic nghiệp vụ.
-   [MongoDB](https://www.mongodb.com/): Lưu trữ cấu hình, dữ liệu ứng dụng và các metadata liên quan đến widget.
-   [Redis](https://redis.io/): Quản lý cache nhằm tăng tốc độ xử lý và phản hồi.
-   [REST API](https://www.ibm.com/topics/rest-apis): Giao tiếp giữa frontend và backend. 
-   [GraphQL](https://graphql.org/): Để tích hợp với các dịch vụ khác.

<img loading="lazy" src="./assets/img/Xác thực người dùng.png " alt="Architecture" width="100%" height=600>


## Cấu trúc dự án
- Branch **master**: (default)
  -   [application](./application) - Chứa file json ứng dụng để tải ứng dụng nên nền tảng Appsmith
  -   [appsmith](./appsmith) - Chứa mã nguồn của nền tảng 
  -   [assest](./assets) - Chứa hình ảnh.
  -   [Docs](./docs) - Tài liệu về dự án.
-  Branch **main**: chứa mã nguồn tài nguyên của application

##  Cài Đặt
- [Hướng dẫn sử dụng](./docs/README.md)
- Seft-host: 
  -   [Hướng dẫn cài đặt client](./docs/CaiDatClient.md) 
  -   [Hướng dẫn cài đặt server](./docs/CaiDatSerVer.md) 

## 🙌 Đóng góp cho dự án

Mọi đóng góp của các bạn đều được trân trọng, đừng ngần ngại gửi pull request cho dự án.

## 📝 License

This project is licensed under the terms of the [Apache-2.0](LICENSE) license.
