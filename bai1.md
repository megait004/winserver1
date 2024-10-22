# Hướng dẫn cài đặt và thực hành với Windows Server

Xin chào tất cả các bạn! Trong repo này, mình sẽ hướng dẫn các bạn cài đặt Windows Server và thực hành với nó.

## Bài 1: Cài đặt Windows Server 2016 và Windows 10, làm quen với cách ping qua lại giữa 2 máy

Trong chương này, các bạn sẽ làm quen với:
- Cách cài đặt Windows
- Một số thao tác cấu hình cơ bản

### Yêu cầu:
- Có 1 máy ảo
- Có file ISO của Windows Server và Windows 10 (mình sẽ upload file vào repo này cho các bạn download nhé)

### Hướng dẫn cài đặt Windows Server và Windows 10

#### Bước 1: Mở VMware
Sau khi cài đặt VMware xong, các bạn mở lên. Giao diện sẽ như thế này:

![Giao diện VMware](./bai1images/vmware.png)

1. Ấn chọn vào **Create a New Virtual Machine** để tạo ra một máy ảo mới để cài Windows Server.
2. Hiển thị ra mục này, các bạn chọn **Custom** và ấn **Next**.
   ![Hiển thị](./bai1images/vm1.png)
3. Tiếp tục chọn **Next**.
   ![Hiển thị](./bai1images/vm2.png)
4. Ở bước này, hãy chọn **Installer disc image file (iso)**. Bạn cần tải trước hai file ISO của Windows Server và Windows 10 để chọn vào nhé. Lưu chúng vào chỗ dễ nhớ.
   - Mình sẽ cài Windows Server trước. Tiếp theo, chọn file ISO của Windows Server (ở đây mình đã cài từ trước nên nó hiện sẵn), rồi ấn **Next**.
   ![Hiển thị](./bai1images/vm3.png)
5. Ở mục này, hãy nhập mật khẩu: `123456a@` cho tất cả các máy, ô bên dưới là xác nhận lại mật khẩu. Điền lại mật khẩu phía trên là xong nhé.
   ![Hiển thị](./bai1images/vm4.png)
6. Nhấn **Yes** khi có thông báo.
   ![Hiển thị](./bai1images/vm5.png)
7. Ở đây có hai ô cần điền:
   - Ô đầu là điền tên máy.
   - Ô có chữ **Location** là vị trí lưu trữ máy ảo. Chọn vào ô bên dưới để lưu vào ổ có nhiều dung lượng (ấn vào **Browse** để chọn ổ).
   ![Hiển thị](./bai1images/vm6.png)
8. Tích chọn **BIOS**. Sau đó ấn **Next**.
   ![Hiển thị](./bai1images/vm7.png)
9. Nếu máy bạn khỏe thì chọn cao lên, còn không cứ để mặc định nhé. Rồi ấn **Next** tiếp.
   ![Hiển thị](./bai1images/vm8.png)
10. Để mặc định rồi ấn **Next**.
    ![Hiển thị](./bai1images/vm9.png)
11. Tiếp tục để mặc định rồi ấn **Next**.
    ![Hiển thị](./bai1images/vm10.png)
12. Nhấn **Next**.
    ![Hiển thị](./bai1images/vm11.png)
13. Chọn **SCSI** và nhấn **Next**.
    ![Hiển thị](./bai1images/vm12.png)
14. Để mặc định và ấn **Next**.
    ![Hiển thị](./bai1images/vm13.png)
15. Chọn ô tròn ở giữa và nhấn **Next**.
    ![Hiển thị](./bai1images/vm14.png)
16. Để mặc định rồi nhấn **Next**.
    ![Hiển thị](./bai1images/vm15.png)
17. Nhấn **Finish**.
    ![Hiển thị](./bai1images/vm16.png)
18. Ngồi đợi máy cài (bạn nào bị lỗi là do thiếu dung lượng hoặc máy yếu).
    ![Hiển thị](./bai1images/vm17.png)
19. Sau khi cài xong máy, nếu xuất hiện thông báo này thì x bỏ hết đi là xong nhé.
    ![Hiển thị](./bai1images/vm18.png)
20. Phần quản trị sẽ hiện ra như này.
    ![Hiển thị](./bai1images/vm19.png)

## Phần 2: Cài máy Windows 10

Tiếp theo, ấn vào mục **Home** và chọn **Create a New Virtual Machine**.
![Hiển thị](./bai1images/vm20.png)

Các bước tương tự như cài Windows Server nhé. Đến bước này, các bạn chọn file ISO Windows 10 đã tải trước đó.
![Hiển thị](./bai1images/vm21.png)

Bước này cũng là đặt tên và chọn vị trí lưu (lưu ý là phải lưu vào chỗ đặt cùng file ISO để tránh lỗi).
![Hiển thị](./bai1images/vm22.png)

Chọn tiếp **BIOS** rồi nhấn **Next**.
![Hiển thị](./bai1images/vm23.png)

Nếu máy khỏe, chọn cao lên cho mượt rồi ấn **Next**.
![Hiển thị](./bai1images/vm24.png)

Tiếp theo, ấn **Next**.
![Hiển thị](./bai1images/vm25.png)

Để mặc định rồi ấn **Next**.
![Hiển thị](./bai1images/vm26.png)

Nhấn **Next** liên tục.
![Hiển thị](./bai1images/vm27.png)

Chọn **SCSI** rồi nhấn **Next**.
![Hiển thị](./bai1images/vm28.png)

Tiếp tục nhấn **Next**.
![Hiển thị](./bai1images/vm29.png)

Chọn ô tròn ở giữa và nhấn **Next**.
![Hiển thị](./bai1images/vm30.png)

Bước này hãy lưu lại cùng 1 chỗ với file ISO.
![Hiển thị](./bai1images/vm31.png)

Nhấn **Finish** và đợi nó cài.

Khi đến bước này, nhấn **Next**.
![Hiển thị](./bai1images/vm32.png)

Nhấn **Install Now**.
![Hiển thị](./bai1images/vm33.png)

Chọn **Full Software** rồi nhấn **Next**.
![Hiển thị](./bai1images/vm34.png)

Tích vào ô **Accept** rồi nhấn **Next**.
![Hiển thị](./bai1images/vm35.png)

Chọn ô **Custom**.
![Hiển thị](./bai1images/vm36.png)

Nó sẽ hiển thị ra như này. Sau đó nhấn vào **New** chỗ mũi tên mình chỉ.
![Hiển thị](./bai1images/vm37.png)

Ấn **Apply**.
![Hiển thị](./bai1images/vm38.png)

Nhấn **OK**.
![Hiển thị](./bai1images/vm39.png)

Chọn như trong hình rồi nhấn **Next**. Đợi nó cài.
![Hiển thị](./bai1images/vm40.png)

Khi đến bước này, nhấn **Yes**.
![Hiển thị](./bai1images/vm41.png)

Bước này cũng chọn cái đầu và **Yes**. Nên để bàn phím tiếng Anh nhé.
![Hiển thị](./bai1images/vm42.png)

Tiếp theo, chọn **Skip**.
![Hiển thị](./bai1images/vm43.png)

Đến bước này, chọn **I don’t have internet connection** để tránh việc đăng nhập mất thời gian.
![Hiển thị](./bai1images/vm44.png)

Chọn ô bên trái để tránh setup nhiều.
![Hiển thị](./bai1images/vm45.png)

Sau đó, đặt tên cho máy của mình, rồi **Next**.
![Hiển thị](./bai1images/vm46.png)

Đặt mật khẩu máy (nhớ là mật khẩu mọi máy đều là `123456a@`).
![Hiển thị](./bai1images/vm47.png)

Xác nhận lại password.
![Hiển thị](./bai1images/vm48.png)

Ở bước này, nó hỏi câu hỏi bảo mật, các bạn cứ chọn 3 câu tùy ý rồi điền là được, không quan trọng.
![Hiển thị](./bai1images/vm49.png)

Và cả hai Windows Server và Windows 10 đã cài xong nhé!

## Phần 3: Hướng dẫn ping qua lại giữa 2 máy

Đây là bảng IP để kiểm tra. Thầy cho IP, các bạn cũng làm tương tự.
![Hiển thị](./bai1images/ip1.png)

### Cấu hình máy Server

1. Vào máy Server trước.
2. Vào **Control Panel** > **Network and Internet**.
   ![Hiển thị](./bai1images/ip2.png)
3. Chọn **Network and Sharing Center**.
   ![Hiển thị](./bai1images/ip3.png)
4. Chọn **Ethernet0** > **Properties**.
5. Bỏ chọn **TCP/IPv6**.
6. Click đúp vào **TCP/IPv4**.
   ![Hiển thị](./bai1images/ip4.png)
7. Chọn **Use the following IP address** và điền thông tin như hình:
   ![Hiển thị](./bai1images/ip6.png)
8. Nhấn **OK** để hoàn tất.
   ![Hiển thị](./bai1images/ip8.png)

### Cấu hình máy Windows 10

1. Vào máy Windows 10 và làm tương tự như máy Server.
2. Vào **Control Panel** > **Network and Internet**.
3. Chọn **Network and Sharing Center**.
4. Chọn **Ethernet0** > **Properties**.
5. Bỏ chọn **TCP/IPv6** và click đúp vào **TCP/IPv4**.
6. Nhập địa chỉ IP tương tự như máy Server và nhấn **OK**.

### Tắt Tường Lửa

1. Để có thể ping được, bạn cần tắt tường lửa cho cả 2 máy.
2. Vào **Control Panel** > **System and Security**.
   ![Hiển thị](./bai1images/ip9.png)
3. Chọn **Windows Firewall** > **Turn Windows Firewall on or off**.
   ![Hiển thị](./bai1images/ip11.png)
4. Tích chọn để tắt tường lửa cho cả 2 máy rồi ấn **OK**.

### Kiểm tra kết nối

1. Vào phần Settings của từng máy, kiểm tra cấu hình VMnet của Adapter.
2. Chọn **Custom** và đảm bảo cả 2 máy sử dụng cùng một VMnet.
3. Thực hiện ping từ máy Server đến máy Windows 10 bằng cách mở **cmd** lên và gõ lệnh ping theo địa chỉ IP của máy Windows 10:
   ![Hiển thị](./bai1images/ip15.png)

### Lệnh kiểm tra cơ bản

- `hostname`: Xem tên máy.
- `ipconfig /all`: Xem thông tin IP của máy.
- `ping`: Kiểm tra kết nối internet.

Nếu cần đổi tên máy Server, làm như sau:
1. Vào **Settings** > **System** > **About** và đổi tên máy.
   ![Hiển thị](./bai1images/ip18.png)

2. Khởi động lại máy để cập nhật tên.

---

Hy vọng hướng dẫn này giúp ích cho các bạn trong việc cài đặt và thực hành với Windows Server! Nếu có thắc mắc nào, đừng ngần ngại hỏi nhé!
