# Báo cáo thực hành Docker
## Các bước thực hành
1. Cài Docker Engine, VNC Viewer trên máy chủ (host)
2. Tạo một thư mục trống, tạo file compose.yaml. Đây là file mà `docker-compose` làm việc. Nếu như muốn tạo một custom image, ta sẽ thêm một Dockerfile, đây là file mà Docker Build làm việc. Ở đây ta sẽ dùng image Ubuntu chính thức từ Docker Hub.
3. Trong file compose.yaml, thêm nội dung như file compose.yaml trong repo.
4. Build và chạy container bằng câu lệnh sau: `docker compose up -d`
5. Sau đó, ta sẽ truy cập vào bash shell của container này thông qua câu lệnh `docker exec -it <container_name> bash`
6. Ta cài Xfce bằng câu lệnh sau: `apt-get install xfce4-session xfce4-goodies`
7. Ta cài thêm màn hình ảo Xvfb: `apt-get install xvfb`
8. Ta tiến hành cài VNC Server vào container thông qua các bước:
  6.1. `apt update`: cập nhật danh sách package
  6.2. Dùng câu lệnh wget để tải VNC Server phù hợp với container, ở đây ta dùng TigerVNC
  6.3. Tạo file mật khẩu cho VNC Server bằng tiện ích `vncpasswd`, đặt tên là passwd
  6.4. Khởi chạy service TigerVNC Server bằng câu lệnh: `x0vncserver -rfbport=5903 -PasswordFile=passwd`
9. Ta cài thêm Xinit: `apt-get install xinit
10. Thông qua VNC Client (ở đây ta dùng RealVNC Client), kết nối với VNC Server thông qua cổng đã tùy chỉnh trong `compose.yaml`.
## Minh chứng kết quả thực hành
![image](https://github.com/revoluzionario/software-architecture-docker/assets/94961228/adc1aadb-d0b2-440d-b23d-b487c3e5c8ba)
