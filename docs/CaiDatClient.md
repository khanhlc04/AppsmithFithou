# Hướng dẫn cài đặt Client trên Ubuntu
## Chuẩn bị trước khi cài đặt:
Trước khi tiến hành cài đặt, máy của bạn cần có những thứ sau:
 
1. `Docker`. Nếu chưa có, truy cập [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)
1. `mkcert`. Để xem chi tiết, truy cập: [https://github.com/FiloSottile/mkcert#installation](https://github.com/FiloSottile/mkcert#installation)
1. `nginx`
1. Đã clone repo về máy của bạn
1. Đã cài đặt `yarn`(3.5.1) toàn cục 
1. <b>Tạo chứng chỉ local HTTPS</b>

    1.  Chạy câu lệnh sau từ thư mục gốc của dự án
        ```bash
        cd app/client/docker && mkcert -install && mkcert "*.appsmith.com" && cd ../../..
        ```
        Câu lệnh này sẽ tạo ra 2 file ở thư mục `docker/`
        - `_wildcard.appsmith.com-key.pem`
        - `_wildcard.appsmith.com.pem`
    1. Thêm domain vào `/etc/hosts`
        ```bash
        echo "127.0.0.1 dev.appsmith.com" | sudo tee -a /etc/hosts
        ```
    
        Note:
        -   Kiểm tra đã thêm thành công hay chưa
        ``` 
        cat /etc/hosts | grep appsmith
        ```
1. Chạy câu lệnh:   `cp .env.example .env`
1. Chạy Backend Server: [Hướng dẫn cài đặt Server](CaiDatSerVer.md)
1. Sau khi đã có Server, chạy lệnh sau để khởi động nginx kết nối các yêu cầu từ frontend tới backend server
    ```
    sudo ./start-https.sh
    ```

## Xây dựng và chạy code
1. Chạy `yarn install`

    Chú ý: 
    - Trên Ubuntu Linux, hãy chạy lệnh sau trước khi tới bước 2:
        ```bash
        echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p 
        ```
1. Chạy `yarn start`
    - 🎉 Bây giờ client sẽ chạy trên https://dev.appsmith.com.
    - <b>URL trên không có cổng 3000</b>

### Khởi động Realtime Service
1. Từ thư mục gốc của dự án, di chuyển tới thư mục `rts`
    ```
    cd app/client/packages/rts
    ```
1. Sao chép file môi trường cho `rts`
    ```
    cp .env.example .env
    ```
1. Khởi động RTS
    ```
    ./start-server.sh
    ```
<b>Nếu không khởi động RTS thì một số chức năng sẽ không thể thực hiện được.</b>