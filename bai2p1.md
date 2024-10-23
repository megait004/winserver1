# 2.1. Nâng cấp máy chủ Windows Server 2012 lên Domain Controller và Join Domain

**Chú ý**: Trước khi làm bài này, hãy xóa hết các card mạng của máy `server1` từ bài 1. Sau đó thêm lại card mạng như đã học ở bài 1.

## Xoá NIC Teaming
1. Vào **Server Manager**, chọn **All Servers**, nhấn chuột phải và chọn **Configure NIC Teaming**.
   ![Hiển thị](./b2p1images/1.png)
2. Click chuột phải và chọn **Delete**.
   ![Hiển thị](./b2p1images/2.png)
3. Tiếp theo, chọn phần **Settings** của máy `server1`.
   ![Hiển thị](./b2p1images/3.png)
4. Xoá các card mạng của máy, nhấn **Remove** và sau đó nhấn **OK**.
   ![Hiển thị](./b2p1images/4.png)

## Thêm lại card mạng
- Đảm bảo cả hai máy sử dụng cùng một VMnet (ví dụ: **VMnet0**).
   ![Hiển thị](./b2p1images/5.png)

## Cấu hình IP cho máy `server1` và máy Win10
- Bảng IP của mình:
   ![Hiển thị](./b2p1images/6.png)
- Cấu hình IP cho máy `server1`:
   ![Hiển thị](./b2p1images/7.png)
- Cấu hình IP cho máy Win10:
   ![Hiển thị](./b2p1images/8.png)

**Chú ý**: Ping thử từ Win10 đến IP của `server1` để đảm bảo mạng hoạt động trước khi thực hiện các bước tiếp theo.

## Cài đặt dịch vụ Active Directory Domain Services trên `server1`
1. Trên máy `server1`, vào **Server Manager**, nhấn vào **Manage** trên thanh công cụ và chọn **Add Roles and Features**.
   ![Hiển thị](./b2p1images/9.png)
2. Nhấn **Next** qua các bước.
   ![Hiển thị](./b2p1images/10.png)
   ![Hiển thị](./b2p1images/11.png)
   ![Hiển thị](./b2p1images/12.png)
3. Chọn **Active Directory Domain Services**.
   ![Hiển thị](./b2p1images/13.png)
4. Khi cửa sổ **Add Roles and Features Wizard** hiện ra, chọn **Add Features**.
   ![Hiển thị](./b2p1images/14.png)
5. Nhấn **Next** qua các bước còn lại.
   ![Hiển thị](./b2p1images/15.png)
   ![Hiển thị](./b2p1images/16.png)
   ![Hiển thị](./b2p1images/17.png)
6. Tại bước này, tích chọn **Restart the destination server automatically if required** và nhấn **Install**.
   ![Hiển thị](./b2p1images/18.png)
7. Sau khi cài xong, nhấn **Close**.
   ![Hiển thị](./b2p1images/19.png)
## Đặt mật khẩu cho tài khoản Administrator
1. Đặt mật khẩu cho tài khoản **Administrator** trên `server1` để tránh lỗi cài đặt.
2. Nhấn **Ctrl + Alt + Delete** để vào màn hình đăng nhập, chọn **Switch User** và đăng nhập vào máy ảo với tài khoản **Administrator**.
   ![Hiển thị](./b2p1images/20.png)
3. Khi yêu cầu thay đổi mật khẩu, nhấn **OK** và nhập mật khẩu mới.
   ![Hiển thị](./b2p1images/21.png)
   ![Hiển thị](./b2p1images/22.png)
4. Các bạn nhập mật khẩu và xác nhận mật khẩu như hình, rồi nhấn nút mũi tên.
   ![Hiển thị](./b2p1images/24.png)
5. Nó sẽ hiện thông báo, nhấn **OK**.
   ![Hiển thị](./b2p1images/25.png)
6. Sau đó, nhấn **Sign In** để đăng nhập lại vào tài khoản **Administrator**.
   ![Hiển thị](./b2p1images/26.png)

## Promote máy `server1` thành Domain Controller
1. Sau khi đăng nhập lại, mở **Server Manager**, nhấn vào biểu tượng tam giác cảnh báo và chọn **Promote this server to a domain controller**.
   ![Hiển thị](./b2p1images/27.png)
2. Chọn **Add a new forest** và đặt tên miền mới theo yêu cầu.
   ![Hiển thị](./b2p1images/28.png)
3. Nhập mật khẩu cho Domain Controller (Ví dụ: `123456a@`) và nhấn **Next**.
   ![Hiển thị](./b2p1images/29.png)
4. Nhấn **Next** qua các bước còn lại.
   ![Hiển thị](./b2p1images/30.png)
   ![Hiển thị](./b2p1images/31.png)
   ![Hiển thị](./b2p1images/32.png)
   ![Hiển thị](./b2p1images/33.png)
5. Đến bước cuối, nhấn **Install** để bắt đầu quá trình cài đặt. Máy sẽ tự khởi động lại sau khi hoàn tất.
   ![Hiển thị](./b2p1images/34.png)

**Chú ý**: Nếu không nhấn **Install** được, có thể là bạn chưa cài mật khẩu cho **Administrator**. Kiểm tra lại các bước đặt mật khẩu ở trên.
6. Sau khi máy khởi động lại, đăng nhập lại với tài khoản **Administrator** và mật khẩu đã đặt trước đó.
   ![Hiển thị](./b2p1images/36.png)
7. Kiểm tra domain đã được thêm thành công hay chưa bằng cách vào **Cài đặt** -> chọn **System** -> chọn **About** -> chọn **System Info**.
   ![Hiển thị](./b2p1images/37.png)
8. Nếu thông tin domain hiện ra như hình dưới là thành công.
   ![Hiển thị](./b2p1images/38.png)
9. Tiếp tục sửa lại card mạng theo yêu cầu.
   ![Hiển thị](./b2p1images/39.png)

## Join Domain
1. Vào máy Win10, ping lại IP của máy `server1` để kiểm tra kết nối. Nếu thành công, tiến hành join domain như sau:
2. Vào **Settings**, chọn **System**, sau đó chọn **About**, rồi chọn **Rename this PC (Advanced)**.
   ![Hiển thị](./b2p1images/40.png)
3. Nhấn **Change**, tích vào ô **Domain**, và nhập tên domain đã tạo trước đó, sau đó nhấn **OK**.
   ![Hiển thị](./b2p1images/41.png)
4. Nhập tài khoản và mật khẩu để join domain.
   ![Hiển thị](./b2p1images/42.png)
5. Khi thấy thông báo thành công, nhấn **OK**, đóng tất cả các cửa sổ và nhấn **Restart Now** để hoàn tất.
   ![Hiển thị](./b2p1images/43.png)
6. Sau khi khởi động lại, Win10 sẽ thuộc domain vừa join.
   ![Hiển thị](./b2p1images/44.png)