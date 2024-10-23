# 2.3 Cài đặt và cấu hình Additional Domain Controller

### Mục đích
Bài này nhằm cài đặt thêm một máy server để dự phòng. Khi máy chủ chính bị tấn công, bạn vẫn còn dữ liệu trên máy thứ hai.

## Các bước thực hiện

### Bước 1: Cài đặt máy server mới
**Cài đặt thêm một máy server mới theo hướng dẫn ở bài 1.**

### Bước 2: Cấu hình mạng
- Cấu hình máy chủ mới theo bảng sau và đặt về cùng vmnet0 với WinServer đã cài trước đó.
- **Tắt tường lửa** như đã làm trong các bài trước.

![Cấu hình mạng](./b2p2images/1.png)

### Bước 3: Kiểm tra kết nối
**Thử ping để kiểm tra kết nối trước khi tiếp tục các bước tiếp theo.**

## Nâng cấp WinServer2 thành Domain Controller

1. Mở **Server Manager** và chọn **Add roles and features**.
2. Tại cửa sổ "Select server roles", chọn **Active Directory Domain Services**.
3. Tiếp tục nhấn Next qua các bước sau:

![Bước 1](./b2p2images/2.png)
![Bước 2](./b2p2images/3.png)
![Bước 3](./b2p2images/4.png)

4. Tích chọn **Active Directory Domain Services** và add features như đã làm ở server1. Nhấn Next.

![Chọn Active Directory](./b2p2images/5.png)

5. Tiếp tục nhấn Next qua các bước tiếp theo:

![Bước 5](./b2p2images/6.png)
![Bước 6](./b2p2images/7.png)

6. Nhấn **Install** để bắt đầu cài đặt.

![Cài đặt](./b2p2images/8.png)

7. Sau khi cài đặt hoàn tất, đóng cửa sổ.

![Hoàn tất cài đặt](./b2p2images/9.png)

**Lưu ý: Đặt mật khẩu cho administrator như đã làm ở server1.**

### Kích hoạt Domain Controller

1. Trong Server Manager, chọn **Promote this server to a domain controller**.

![Kích hoạt Domain Controller](./b2p2images/10.png)

2. Chọn **Add a domain controller to an existing domain**. Nhập tên domain của bạn.

![Thêm Domain Controller](./b2p2images/11.png)

3. Nhấn "Change" và nhập thông tin đăng nhập. Mật khẩu là **123456a@**. Nhấn OK, sau đó Next.

![Nhập thông tin đăng nhập](./b2p2images/12.png)

4. Nhập lại mật khẩu **123456a@** và nhấn Next.

![Xác nhận mật khẩu](./b2p2images/13.png)

5. Tiếp tục nhấn Next qua các bước tiếp theo:

![Bước 5](./b2p2images/14.png)
![Bước 6](./b2p2images/15.png)
![Bước 7](./b2p2images/16.png)
![Bước 8](./b2p2images/17.png)

6. Nhấn **Install** để bắt đầu cài đặt.

![Cài đặt](./b2p2images/18.png)

7. Sau khi cài đặt hoàn tất, máy sẽ tự động khởi động lại.

![Khởi động lại](./b2p2images/19.png)

8. Đăng nhập lại và kiểm tra như đã làm với server1.

![Kiểm tra cài đặt](./b2p2images/20.png)

## Tạo user mới và kiểm tra đồng bộ

1. Mở **Windows Administrative Tools**.

![Windows Administrative Tools](./b2p2images/21.png)

2. Chọn **Active Directory Users and Computers**.

![Active Directory Users and Computers](./b2p2images/22.png)

3. Trong domain, tìm mục Users, nhấp chuột phải và chọn New > User.

![Tạo user mới](./b2p2images/23.png)

4. Nhập thông tin user mới và nhấn Next.

![Nhập thông tin user](./b2p2images/24.png)

5. Đặt mật khẩu cho user, bỏ tích các tùy chọn như hình và nhấn Next.

![Đặt mật khẩu](./b2p2images/25.png)

6. Nhấn Finish để hoàn tất.

![Hoàn tất tạo user](./b2p2images/26.png)

7. Kiểm tra trên server1 để xác nhận user mới đã được đồng bộ.

![Kiểm tra đồng bộ](./b2p2images/27.png)
