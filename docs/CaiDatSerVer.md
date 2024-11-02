# Hướng dẫn cài đặt Server trên Ubuntu
## Chuẩn bị trước khi cài đặt:
Trước khi tiến hành cài đặt backend server, máy của bạn cần phải có những thứ sau:

1. Java - OpenJDK 17
1. Maven - Version 3+ (Thích hợp nhất là 3.6)
1. NodeJS (20.11.1)
1. MongoDB database 
1. Redis
1. IDE - IntelliJ IDEA là thích hợp nhất

### Thiết lập MongoDB local
* Chạy câu lệnh sau để khởi động MongoDB với Docker
    ```
    docker run -d -p 127.0.0.1:27017:27017 --name appsmith-mongodb --hostname=localhost -e MONGO_INITDB_DATABASE=appsmith -v /path/to/store/data:/data/db mongo --replSet rs0
    ```
* Thay `/path/to/store/data` bằng đường dẫn hợp lệ trên máy của bạn. Đây sẽ là nơi lưu trữ dữ liệu qua các lần chạy
* Bây giờ MongoDB đang chạy trên `mongodb://localhost:27017/appsmith`
    ### Kích hoạt replica set cho mongo
    1. Kết nối tới MongoDB với Mongo Shell. Sử dụng câu lệnh sau:
        ``` 
        mongosh 
        ```
    1. Chạy câu lệnh sau trong Mongo Shell:
        ```
        rs.initiate({"_id": "rs0", "members" : [{"_id":0 , "host": "localhost:27017" }]})
        ```
### Thiết lập Redis local 
* Khởi động Redis với Docker 
    ```
    docker run -d -p 127.0.0.1:6379:6379 --name appsmith-redis redis
    ```
* Bây giờ Redis chạy trên `redis://localhost:6379`

<br />
<b>Sau khi đã cài đặt những thứ cần thiết, hãy bắt đầu xây dựng code</b>

### Xây dựng và chạy code
1. Di chuyển tới thư mục server
    ```bash
    cd app/server
    ```
1. Chạy câu lệnh sau
    ```console
    mvn clean compile
    ```
    * Câu lệnh trên sẽ tạo ra các class cần thiết để  IDE có thể  biên dịch code. Nếu không có bước này IDE sẽ báo lỗi và không thể biên dịch được code
1. Thiết lập file Environment
    Tạo bản sao của `envs/dev.env.example`

    ```console
    cp envs/dev.env.example .env
    ```
    * Câu lệnh trên sẽ tạo ra file .env trong `app/server`. Tất cả các lệnh script sẽ lấy môi trường được cấu hình trong file này
1. Chắc chắn rằng các biến môi trường `APPSMITH_DB_URL` và `APPSMITH_REDIS_URI` trong file `.env` đang trỏ tới MongoDB và Redis đang chạy trên máy của bạn
1. Cập nhật tên của replica set trong chuỗi kết nối mongo trong file `.env` với giá trị trùng với [thiết lập mongo ở trên](#thiết-lập-mongodb-local)
1. Chạy lệnh sau để tạo JAR cho server:
    ```console
    ./build.sh -Dmaven.test.skip
    ```
    * Câu lệnh trên sẽ tạo ra thư mục dist chứa JAR đã đóng gói với nhiều JAR cho các plugin khác nhau
    * Nếu dung lượng của docker còn trống nhỏ hơn 2GB đoạn mã có thể gặp lỗi sau:
        ```console
        Check failed: Docker environment should have more than 2GB free disk space.
        ```
    * Cách giải quyết:
        - Giải phóng dung lượng 
        - Thay đổi đường dẫn gốc của docker
    * #### Môi trường Linux/Ubuntu
        - Trong môi trường Linux, docker cần quyền root để chạy, câu lệnh `./build.sh` cũng cần quyền root để có thể chạy được
        - Trong môi trường Linux, đoạn lệnh có thể không đọc được file `.env`, bạn có thể chạy câu lệnh như sau:
            ```console
            sudo APPSMITH_DB_URL="mongodb://localhost:27017/appsmith" APPSMITH_REDIS_URL="redis://127.0.0.1:6379" APPSMITH_MAIL_ENABLED=false APPSMITH_ENCRYPTION_PASSWORD=abcd APPSMITH_ENCRYPTION_SALT=abcd ./build.sh
            ```
1. Khởi động server
    ```console
    ./scripts/start-dev-server.sh
    ```
    * Mặc định, server sẽ chạy trên cổng 8080
    * Có thể kiểm tra trạng thái bằng cách truy cập: [http://localhost:8080/api/v1/users/me](http://localhost:8080/api/v1/users/me)
