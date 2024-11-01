# Appsmith - FITHOU
### Phần mềm làm việc online

Ứng dụng hỗ trợ quản lý công việc và dự án giúp các nhóm và cá nhân tổ chức công việc hiệu quả, theo dõi tiến độ và tăng cường sự hợp tác. 

Mục tiêu là phát triển một ứng dụng tăng hiệu suất công việc, giám sát tiến độ, chất lượng dự án, tăng cường tính minh bạch và trách nhiệm. 

Dự án được thực hiện trong cuộc thi [Mã nguồn mở - giải thuật lập trình - Vòng sơ loại cấp khoa Olympic Tin Học 2024](https://www.facebook.com/photo/?fbid=1070411584788970&set=a.258988462597957). Dự án theo giấy phép theo giấy phép [Âpache-2.0](https://github.com/honganhss/AppsmithFit/blob/main/LICENSE) bởi đội tác giả FFC-Beta.

Để biết thêm chi tiết về cuộc thi, bạn có thể xem tại [đây](https://www.facebook.com/photo/?fbid=1070411584788970&set=a.258988462597957).

Link thuyết trình Canva tại cuộc thi [link]()

Slide bài thuyết trình tại cuộc thi dưới dạng PDF có thể được truy cập tại đây: [Slide]()

## 🔎 Danh Mục

- [Appsmith - FITHOU](#appsmith---fithou)
    - [Phần mềm làm việc online](#phần-mềm-làm-việc-online)
  - [🔎 Danh Mục](#-danh-mục)
  - [Giới Thiệu](#giới-thiệu)
  - [Chức Năng Chính](#chức-năng-chính)
  - [👩‍💻 Tổng Quan Hệ Thống](#-tổng-quan-hệ-thống)
  - [Cấu trúc thư mục](#cấu-trúc-thư-mục)
  - [Hướng Dẫn Cài Đặt](#hướng-dẫn-cài-đặt)
  - [🙌 Đóng góp cho dự án](#-đóng-góp-cho-dự-án)
  - [Liên hệ](#liên-hệ)
  - [📝 License](#-license)

## Giới Thiệu
 
- Ứng dụng Quản lý Công việc là công cụ hỗ trợ quản lý toàn diện dành cho các cá nhân và nhóm làm việc. Ứng dụng này cho phép người dùng tổ chức, theo dõi và giám sát các nhiệm vụ và dự án một cách hiệu quả. Với tính năng tạo nhiệm vụ, phân công, đặt hạn, theo dõi tiến độ và nhận thông báo, ứng dụng giúp đảm bảo rằng các công việc được thực hiện đúng thời hạn và với hiệu suất tối ưu.

- Được cập nhật và nâng cấp thường xuyên, ứng dụng Quản lý Công việc giúp người dùng luôn có cái nhìn tổng quan về toàn bộ dự án, từ chi tiết công việc đến nguồn lực cần thiết. Bên cạnh đó, các báo cáo và thống kê trực quan giúp nhà quản lý đưa ra quyết định nhanh chóng, cải thiện khả năng hợp tác và thúc đẩy tính trách nhiệm của từng thành viên trong nhóm. Đây là công cụ lý tưởng để tăng cường năng suất, sự hợp tác và đạt được mục tiêu dự án một cách hiệu quả nhất.

## Chức Năng Chính

Project tập trung vào các chức năng chính như sau:

-   📋 Tạo và phân công nhiệm vụ (Tasks & Assignments). 
-   📝 Lên lịch và theo dõi tiến độ. 
-   🛎 Thông báo và nhắc nhở. 
-   📃 Quản lý tài liệu dự án.

## 👩‍💻 Tổng Quan Hệ Thống

Backend của hệ thống được thiết kế theo kiến trúc microservices, với các công nghệ sử dụng như sau:

-   [Spring Framework](https://spring.io/projects/spring-framework): Phát triển các dịch vụ và xử lý logic nghiệp vụ.
-   [MongoDB](https://www.mongodb.com/): Lưu trữ cấu hình, dữ liệu ứng dụng và các metadata liên quan đến widget.
-   [Redis](https://redis.io/): Quản lý cache nhằm tăng tốc độ xử lý và phản hồi.
-   [REST API](https://www.ibm.com/topics/rest-apis): Giao tiếp giữa frontend và backend. 
-   [GraphQL](https://graphql.org/): Để tích hợp với các dịch vụ khác.

<img loading="lazy" src="./assets/img/Xác thực người dùng.png " alt="Architecture" width="100%" height=600>


## Cấu trúc thư mục

-   [Crawler](./law-crawler) - Crawl vào CSDL từ nguồn pháp điển Việt Nam.
-   [Backend](./backend) - Chứa các mô hình, services, kiến trúc của hệ thống.
-   [Web](./web) - Giao diện người dùng.
-   [Documents](./docs/) - Tài liệu về dự án.

## Hướng Dẫn Cài Đặt


## 🙌 Đóng góp cho dự án

Mọi đóng góp của các bạn đều được trân trọng, đừng ngần ngại gửi pull request cho dự án.

## Liên hệ

-   Nguyễn Hồng Ánh: honganh068204@gmail.com
-   Lê cát Khánh: 
-   Tống Tâm Xuân 

## 📝 License

This project is licensed under the terms of the [Apache-2.0](LICENSE) license.
